---
title: The ‘final’ Frontier in Java
author: Adi R
type: post
date: 2012-09-01T16:30:51+00:00
url: /2012/09/the-final-frontier-in-java/
heroStyle: "basic"
tags:
  - Java
  - Programming

---

## Introduction

<p align="justify">
  Although this post came about primarily to help my son learn Java, it still amazes me how many professional developers do not understand this basic premise in Java (Programming Language) even after working with it for Years. I am yet to find any Java book that opens with Big Chapter on this very critical topic, instead they mention it in a few hardly intelligible sentences. Meanwhile Java continues to gain momentum as most popular language, primarily because of how easy it seems to use! Let me be the first to tell you that Yes, it is Easy, provided you fully grasp the concepts outlined below.
</p>

<p align="justify">
  Quick primer before diving into Java &#8211; most operating systems organize memory for a running program as Heap and Stack. These are just designations for areas of memory allocated to your program, but the way they are utilized differs slightly as we&#8217;ll see below. And if you don&#8217;t know what Object is, for our purposes it&#8217;s just a little set of data organized together.
</p>

## Pointers

<p align="justify">
  There is fundamental difference in Java between Object variables and Primitive variables. The latter is those built-in types we all grew to love from most languages, like int, long and float. They are actually very high performance as well because they are quickly allocated on the Stack and CPU operates on them via Native commands.
</p>

<p align="justify">
  Meanwhile Objects in Java are just <strong><em>Pointers</em></strong>! Let me demonstrate with this simple example:
</p>

{{< highlight java >}}
public static void main(String[] args) 
{
    int a = 1;
    int b = a;
    a=3;
    
    System.out.println("A: "+a+" B: "+b);
    
    ArrayList aLst = new ArrayList();
    ArrayList bLst = aLst;      
    aLst.add("I Live in List");
    
    System.out.println(" A List Size: "+aLst.size()+
                       " B List Size: "+bLst.size());
}
{{< /highlight >}}

<p align="justify">
  Although lines 3-5 look conceptually similar to lines 9-12, the output is very different:
</p>

{{< alert "bug" >}}
A: 3 B: 1<br>
A List Size: 1 B List Size: 1
{{< /alert >}}

<p align="justify">
  With Primitives we see that assigning <strong>a</strong> into <strong>b</strong> truly made a copy, so that when we put 3 into <strong>a</strong> later, nothing happened to <strong>b</strong>. <img style="background-image: none; border-right-width: 0px; margin: 5px 0px 5px 10px; padding-left: 0px; padding-right: 0px; display: inline; float: right; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="Two_Java_Pointers_at_ArrayList_Object" border="0" alt="Two_Java_Pointers_at_ArrayList_Object" align="right" src="https://i0.wp.com/www.adir1.com/uploads/2012/09/Two_Java_Pointers_at_ArrayList_Object.jpg?resize=300%2C112" width="300" height="112" data-recalc-dims="1" />Meanwhile, assigning <strong>aLst</strong> into <strong>bLst</strong> seems to act differently, as modifying <strong>aLst</strong> makes something magically appear in <strong>bLst</strong>!
</p>

## Objects

<p align="justify">
  Although our most respected <a href="http://en.wikipedia.org/wiki/James_Gosling" target="_blank">Java Designer Mr. Gosling</a> tried to hide the pointers complexity away from average developer, it still shows through sometimes, especially when calling Methods and passing Objects around:
</p>


{{< highlight java >}}
public static void callMeMaybe(ArrayList third, int howOften) 
{
  howOften = 1;
  third.clear();
  third.add("+1 800-555-1212");
}

public static void main(String[] args) 
{
  int a = 800;
  ArrayList first = new ArrayList();
  ArrayList second = first;
  first.add("Unlisted Number");

  callMeMaybe(second, a);

  System.out.println("Our List: "+first);
  System.out.println("A: " + a);
}
{{< /highlight >}}

And here is the output, hopefully what you expected by now:

{{< alert "bug" >}}
Our List: [+1 800-555-1212]<br>
A: 800
{{< /alert >}}

## What Is Happening?

<p align="justify">
  <br />What has happened to our <strong>Unlisted Number</strong>? And if the evil <strong>callMeMaybe</strong> method was able to eliminate it, why did we not extract the essential <strong>howOften</strong> to call information from that same method?<a class="thickbox" href="https://i2.wp.com/www.adir1.com/uploads/2012/09/Three_Java_Pointers_at_an_Object.jpg.jpg"><img style="background-image: none; border-right-width: 0px; margin: 5px 0px 5px 10px; padding-left: 0px; padding-right: 0px; display: inline; float: right; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="Three_Java_Pointers_at_an_Object.jpg" border="0" alt="Three_Java_Pointers_at_an_Object.jpg" align="right" src="https://i1.wp.com/www.adir1.com/uploads/2012/09/Three_Java_Pointers_at_an_Object.jpg_thumb.jpg?resize=339%2C182" width="339" height="182" data-recalc-dims="1" /></a>
</p>

<p align="justify">
  The basic way to understand the difference is to simply remember the Primitives versus Objects distinction. The more complete explanation is that Objects live in the Heap, while pointers to objects (such as <strong>first</strong>, <strong>second</strong> and <strong>third</strong> in our example) live along with Primitives, in the Stack. Each time our program enters a method, new variables (sometimes with copies of values from existing variables) get created on the Stack, and once method is finished, they are released. But even though once <strong>callMeMaybe</strong> method finishes our <strong>third</strong> variable gone into the great beyond (along with <strong>howOften</strong> variable), the object it was pointing to lives on in the Heap, and still available for <strong>first </strong>to see.
</p>

## Finally

Having understood this we are finally ready to discuss Java’s ‘**final’** keyword<img style="border-bottom-style: none; border-left-style: none; border-top-style: none; border-right-style: none" class="wlEmoticon wlEmoticon-winkingsmile" alt="Winking smile" src="https://i2.wp.com/www.adir1.com/uploads/2012/09/wlEmoticon-winkingsmile.png" data-recalc-dims="1" /> 

Simply put, when this keyword is placed on variable definition, you can only give this variable one value in it’s lifetime. A more complete explanation about the use of final keyword can be found on <a href="http://en.wikipedia.org/wiki/Final_(Java)" target="_blank">Wikipedia</a>. My personal recommendation is that you avoid using this keyword, except when defining some truly Constant value in all upper case, like so:

{{< highlight java >}}
public static final int REQUIRED_SLEEP_FOR_HEALTH = 8;
{{< /highlight >}}

<p align="justify">
  <br />And especially avoid using it when declaring Object referencing variables, since it does <strong>Not </strong>do what you would expect. As a simple example, if we were to define <strong>third</strong> variable in example above as <strong>final</strong>, it would have no impact on our program behavior or output!
</p>

<p align="justify">
  While there are few other cases where <strong>final</strong> should be used, remember that <a href="http://www.ibm.com/developerworks/java/library/j-jtp1029/index.html" target="_blank">Optimization is Not one of them</a>.
</p>

<p align="justify">
  Good Luck!
</p>

{{< alert "image" >}}
**Featured Art:** by [Karl Pawlowicz on Unsplash](https://unsplash.com/photos/QUHuwyNgSA0)
{{< /alert >}}
