---
title: "(Bad) Coding Vibes"
description: "Here I outline a strategy to Win at the Vibe Coding Game! This latest phenomena is exciting, but how do we ensure thousands or millions of generated lines of code are accurate and performant?"
author: Adi Rabinovich
type: post
heroStyle: "background"
showTableOfContents: true
draft: true
date: 2026-05-25T03:33:33-03:00
url: /2026/bad-coding-vibes/
tags:
  - Programming
  - Software Architecture
  - AI
  - Agents
  - Cloud
  - Vibe Coding
---

## Overview

Lately, everybody seems to be talking about Vibe Coding—letting the AI rapidly generate code based on a general direction or "vibe". It is very transformative and exciting, but we are facing a major scalability crisis! As AI systems generate more code, the human attention needed for review grows **exponentially**. When you have thousands or millions of generated lines of code, the probability of subtle bugs and architectural mistakes becomes completely unacceptable. We need a new strategy to Win this game!

> [!WARNING] The Vibe Coding Paradox
> More AI-generated code = More lines to review + Higher bug probability + Exponential overhead. Without structure, Vibe Coding becomes unmaintainable at scale.

Here I propose a **Layered Decomposition Strategy** to turn the scalability problem on its head: instead of generating monolithic code and hoping it works, we can decompose the problem into discrete layers, define reusable components, and let the AI focus on implementation *within those boundaries*. The result is **dramatically less total code**, higher quality, and predictable testing!

## The Problem: Exponential Review Burden

### The Math of Scale

{{< mermaid >}}
graph LR
    A["AI Generates<br/>10K Lines"] --> B["Human Reviews<br/>10K Lines"]
    B --> C["Bugs Found"]
    C --> D["Rework Needed"]
    
    E["AI Generates<br/>1M Lines"] --> F["Human Reviews<br/>1M Lines<br/>(10x Effort)"]
    F --> G["Bugs Found<br/>(More Likely)"]
    G --> H["Rework Needed<br/>(Exponential Complexity)"]
    
    style A fill:#90EE90
    style E fill:#FFB6C1
    style B fill:#FFE4B5
    style F fill:#FF6347
{{< /mermaid >}}

When we generate code with AI without any proper structure (which is what most people do today):

1. **Lines of code grow linearly** with features (100 features = 10K lines)
2. **Review effort grows with lines** (human must understand context for every single line)
3. **Bug probability increases** with code complexity (more interactions = more edge cases)
4. **Interdependencies multiply** (each layer talks to every other layer)

The result? Code that works perfectly in isolation completely fails during integration. Critical bugs love to hide in the gaps between AI-generated modules!

{{< alert >}}
**My Key Insight**: The problem isn't AI code quality itself—it's that *unstructured code generation* creates exponential complexity for us humans, regardless of how good each piece looks on its own.
{{< /alert >}}


## The Solution: Layered Decomposition with Reusable Components

Instead of asking AI to generate a complete system, we need to restructure how we think about the problem:

1. **Decompose vertically** into distinct layers (Presentation, Business Logic, Data Access, etc.)
2. **Within each layer, decompose horizontally** into reusable components
3. **Define specs explicitly** before vibe coding—libraries we'll use, interfaces we'll need
4. **Use AI to break down problems iteratively**, always pushing for higher abstraction and code reuse
5. **Test aggressively at layer boundaries**, not just at the final edges

### The Layered Architecture Model

{{< mermaid >}}
graph TB
    subgraph "Presentation Layer"
        UI["UI Components<br/>(Reusable Widgets)"]
    end
    
    subgraph "API/Contract Layer"
        API["REST/GraphQL APIs<br/>(Defined Contracts)"]
    end
    
    subgraph "Business Logic Layer"
        BL["Domain Models<br/>(Business Rules)"]
        SVC["Services<br/>(Use Existing Libs)"]
    end
    
    subgraph "Data Layer"
        ORM["ORM/Query Layer<br/>(Existing Framework)"]
        DB["Database Schema<br/>(Normalized Design)"]
    end
    
    subgraph "Cross-Cutting"
        UTIL["Utilities<br/>(Logging, Auth, etc.)"]
    end
    
    UI --> API
    API --> BL
    BL --> SVC
    SVC --> ORM
    ORM --> DB
    UTIL -.-> BL
    UTIL -.-> SVC
    UTIL -.-> ORM
    
    style UI fill:#B0E0E6
    style API fill:#B0E0E6
    style BL fill:#FFD700
    style SVC fill:#FFD700
    style ORM fill:#FFB6C1
    style DB fill:#FFB6C1
    style UTIL fill:#E6E6FA
{{< /mermaid >}}


## The Strategy: Four Pillars

### 1. **Layer First, Code Second**

Before writing a single line of code, map out your layers:

{{< accordion >}}
  {{< accordionItem title="Typical Product Layers" >}}

- **Presentation**: UI components, state management, styling
- **API Contract**: REST endpoints, GraphQL schema, request/response shapes
- **Business Logic**: Domain models, validations, workflows
- **Persistence**: Database queries, migrations, caching
- **Infrastructure**: Deployment, monitoring, configuration
- **Utilities**: Shared functions, error handling, logging

  {{< /accordionItem >}}

  {{< accordionItem title="For Each Layer, Ask:" >}}

1. Does an existing library solve 70%+ of this layer's needs?
2. If yes, can we extend it with minimal custom code?
3. If no, what reusable spec should we define first?
4. What interfaces do I need between this layer and others?

  {{< /accordionItem >}}
{{< /accordion >}}

**My Action Plan**: For every project, create a layer definition document. Have the AI help you with this breakdown.

### 2. **Specify Components Before Coding**

For each layer without an existing solution, we must define:

- **Input/Output contract** (what comes in, what goes out)
- **Key functions/methods** needed
- **Error cases** to handle
- **Performance requirements**
- **Testability boundaries** (what should be mockable)

> [!INFO] Example: Business Logic Layer Spec
> ```yaml
> Layer: Business Logic - User Management
> Components:
>   - UserService:
>       Methods:
>         - createUser(email, password) → User | ValidationError
>         - authenticateUser(email, password) → AuthToken | AuthError
>         - getUser(id) → User | NotFoundError
>       Dependencies:
>         - PasswordHasher (use bcrypt library)
>         - UserRepository (interface to persist layer)
>       Testing: All methods mockable, no DB calls in unit tests
> ```

Now ask the AI: "Implement UserService with these specs." Believe me, these constraints make the generated code:
- More predictable
- Easier to test (mocking dependencies is key)
- Simpler to review
- Reusable in other projects

### 3. **Ruthlessly Pursue Reusability Within Layers**

This is where AI becomes a true multiplier:

#### Bad Approach

```
AI generates:
- getUser() in UserController
- getUser() in AdminController  
- getUser() in ReportController
- getUser() in NotificationController
(4 similar functions, 4x the code, 4x the bugs)
```

#### Good Approach

```
Define once:
- UserService.getUser(id) in Business Logic Layer

Use everywhere:
- UserController calls UserService.getUser()
- AdminController calls UserService.getUser()
- ReportController calls UserService.getUser()
- NotificationController calls UserService.getUser()
(1 function, massive code reduction, single point of fix)
```

**My Favorite Technique**: After AI generates code for a layer, ask it:
> "Review what you just wrote. Identify 3 functions that appear in similar form elsewhere. How can we extract and reuse them? How can we parametrize this further?"

### 4. **Test at Layer Boundaries, Not Edges**

With layered architecture, testing becomes highly strategic (and much more fun!):

{{< mermaid >}}
graph TD
    subgraph "Unit Tests"
        UT["Test each layer in isolation<br/>with mocks for dependencies"]
    end
    
    subgraph "Integration Tests"
        IT["Test layer boundaries<br/>Verify contracts are honored"]
    end
    
    subgraph "System Tests"
        ST["Test full workflows<br/>End-to-end scenarios"]
    end
    
    subgraph "Traditional Approach"
        OLD["Test everything everywhere<br/>High cost, low signal"]
    end
    
    UT -->|Catches logic bugs| IT
    IT -->|Catches interface bugs| ST
    ST -->|Catches workflow bugs| END["High Confidence"]
    
    OLD -->|Expensive| LOW["Low Confidence<br/>High Maintenance"]
    
    style UT fill:#90EE90
    style IT fill:#FFD700
    style ST fill:#FFB6C1
    style END fill:#90EE90
    style LOW fill:#FF6347
{{< /mermaid >}}

**The simple math of layered testing**:
- 100 unit tests (10 per layer) + 20 integration tests = ~120 tests, giving us high coverage
- The alternative? 1000 end-to-end tests for the same coverage, 10x slower, and a complete nightmare to debug!


## Practical Workflow: The Iterative Decomposition Loop

{{< mermaid >}}
graph LR
    A["Define Feature<br/>Set High-Level Goals"] -->|"Break into Layers"| B["Map Layers<br/>Required Components"]
    B -->|"For each gap:"| C["Ask AI:<br/>Design Specs<br/>for Component"]
    C -->|"Get AI to<br/>generalize:"| D["Extract Reusable<br/>Abstractions"]
    D -->|"Iterate:"| E["Vibe Code<br/>Implementation"]
    E -->|"Test & Verify"| F["Verify Contract<br/>Adherence"]
    F -->|"Next Feature?"| A
    
    style A fill:#FFE4B5
    style B fill:#B0E0E6
    style C fill:#FFD700
    style D fill:#90EE90
    style E fill:#FFB6C1
    style F fill:#FFE4B5
{{< /mermaid >}}

### Step-by-Step Example

**Goal**: Build a payment processing system

```
1. DECOMPOSE into layers:
   ├─ Payment API Layer (REST contracts)
   ├─ Payment Business Logic (Calculate fees, validate amounts)
   ├─ Payment Gateway Integration (Use Stripe library)
   ├─ Transaction Persistence (Use SQLAlchemy ORM)
   └─ Error Handling & Logging (Reusable utilities)

2. FOR EACH LAYER, DEFINE SPECS:
   ├─ What's the interface?
   ├─ What libraries exist? (Use them!)
   ├─ What do we build? (Only the gap)
   └─ What are the test boundaries?

3. ASK AI TO DESIGN REUSABLE COMPONENTS:
   ├─ Can we parametrize payment validation?
   ├─ Can we create a generic TransactionService?
   ├─ Can we extract a RetryPolicy abstraction?

4. VIBE CODE THE IMPLEMENTATION:
   ├─ "Implement PaymentService using these specs"
   ├─ "Generate unit tests for edge cases"
   └─ "Create integration tests for layer boundaries"

5. RESULT:
   ├─ ~2K lines total (vs 10K for monolithic)
   ├─ Each layer testable independently
   ├─ Components reusable in other projects
   └─ Human review focused on architecture, not boilerplate
```


## The Cascade Effect: How This Scales

> [!SUCCESS] The Multiplier Effect
> **With naive Vibe Coding**:
> - 10 features = 10K lines = 10K lines to review + integration chaos
> - 20 features = 20K lines = 20K lines to review + exponential integration bugs
> - 100 features = 100K lines = **unmaintainable**
> 
> **With Layered Decomposition**:
> - Define 6 reusable layers (2K lines of scaffolding)
> - Feature 1 = 500 lines + 100 test lines
> - Feature 2 = 400 lines (reuses utilities from Feature 1)
> - Feature 3 = 300 lines (reuses more abstractions)
> - ...
> - 10 features = 3K lines (not 10K) + minimal integration risk
> - 100 features = ~15K lines (not 100K) + rock-solid interfaces
> 
> **Per-feature code reduction**: 50-80%  
> **Bug probability**: Decreased exponentially  
> **Human review effort**: Decreased 10x


## Common Pitfalls & How to Avoid Them

{{< accordion mode="open" card="true" >}}
  {{< accordionItem title="Pitfall: Over-engineering" >}}

**Problem**: Creating too many layers or components too early.

**Solution**: Start with 4-5 core layers. Add more only when you have 3+ features that need a new layer.

  {{< /accordionItem >}}

  {{< accordionItem title="Pitfall: Library Bloat" >}}

**Problem**: Using a library that's 70% of what you need but forces adoption of 30% you don't.

**Solution**: If a library forces architecture decisions, prefer building a minimal spec and coding it. Reassess quarterly.

  {{< /accordionItem >}}

  {{< accordionItem title="Pitfall: Weak Contracts" >}}

**Problem**: Layers talk to each other via implicit contracts that change constantly.

**Solution**: Define contracts explicitly. Use generated API docs, TypeScript interfaces, or protocol buffers. Make breaking changes obvious.

  {{< /accordionItem >}}

  {{< accordionItem title="Pitfall: Testing Theater" >}}

**Problem**: Writing tests that don't catch real bugs because layers aren't properly isolated.

**Solution**: Test contracts between layers explicitly. A passing test should mean "this layer works correctly in context", not just "this code runs".

  {{< /accordionItem >}}
{{< /accordion >}}


## Your Action Plan: Winning at Vibe Coding

{{< accordion >}}
  {{< accordionItem title="Week 1: Decompose" >}}

1. Pick your next project
2. Spend 2-3 hours mapping layers and components
3. Identify which layers use existing libraries (70% solution)
4. Write specs for layers where you'll build custom code
5. Have AI help review the design—ask it to suggest abstractions

  {{< /accordionItem >}}

  {{< accordionItem title="Week 2-3: Define Interfaces" >}}

1. For each custom layer, define the API (method signatures, error types)
2. Create type definitions (TypeScript, Python type hints, Rust traits)
3. Write a 1-page spec per layer describing how it fits with others
4. Generate API documentation automatically

  {{< /accordionItem >}}

  {{< accordionItem title="Week 4: Vibe Code with Structure" >}}

1. For each layer, ask AI: "Implement this spec, maximize reusability"
2. Iterate: "Can you factor this further? Extract reusable functions?"
3. Test at layer boundaries
4. Measure: total lines of code, bugs found, review time

  {{< /accordionItem >}}

  {{< accordionItem title="Ongoing: Iterate & Generalize" >}}

1. After each feature, ask: "What abstractions can we extract for next time?"
2. Keep a library of reusable specs and components
3. Build a project template based on your layer definitions
4. Make it easy for future projects to reuse what you've built

  {{< /accordionItem >}}
{{< /accordion >}}


## Conclusion: Vibe Coding Done Right

Personally, I don't think Vibe Coding is fundamentally flawed—it's just missing **proper structure**. By decomposing our products into clean layers, defining reusable components, and using the AI to help push toward abstraction and generalization, you can have your cake and eat it too:

- **Rapid development** through AI code generation ✓
- **High code quality** through deliberate architecture ✓
- **Reduced review burden** through reusable, well-tested components ✓
- **Scalability** that actually scales ✓

The key here is simple: Stop asking the AI to generate complete systems out of thin air. Start asking it to **design layers, extract abstractions, and implement specs**. The result is exponentially less code, exponentially fewer bugs, and exponentially better software!

**Now go vibe-code responsibly.** 🚀


{{< alert "image" >}}
**Featured in-post image generated by DALL-E 3**
{{< /alert >}}
>> Prompt: Image for my blog post background, soft mild blue tones. endless mostly modern servers in a large open space surrounded by water and with waterfall in the distance. closer to the foreground on the right side there is one larger and older server, using magnetic tapes spinning on the front, with one server tape seemingly escaping and getting entangled.
