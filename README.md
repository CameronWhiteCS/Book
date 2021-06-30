# Programming I: Java From a Mathematical Perspective

*Cameron White*

*Special thanks to Kabir Khara for providing feedback that made this book possible*

## Preface

This is the section where you’re supposed to dedicate your book to some old friend of yours who passed away many years ago, or go on and on about how much time and effort was put into the writing, or give thanks to a bunch of random people no one’s ever heard of. And while I could do that with this section, no one really cares.

Instead, I’d like to briefly cover why this book exists in the first place and what it’s intended to do. I remember taking Programming I during my first semester at UF. It was a complete train wreck. Due to the amount of material that had to be covered, we were immediately going over obscure and arcane topics and related vocabulary on day one out of necessity. Most people without any prior experience were painfully lost, and to expect otherwise would have been lunacy. There is simply too much to cover in too little time. 

This book is intended to supplement in-class learning and assignments. It isn’t a complete text nor is it meant to be one. However, it is tailored for UF’s Programming I curriculum and includes a few useful topics not covered in class. I’ve tried to keep it as concise and free of nonsense as possible.

This book covers the how of programming, but not necessarily the why. Techniques are presented without an in-depth explanation of why someone would choose to use them. This is partially done for the sake of practicality and partially for the sake of brevity. Programming is a skill that must be learned in the same way something like playing an instrument or learning to paint are learned, albeit in a more left-brained way. The reasoning for different programming techniques and tools will become more clear as you gain more experience. 

Programming is best learned by doing rather than by reading. That’s not to say that reading and research don’t have their place. If that were the case, I wouldn’t have written this book. However, paper and ink will only take you so far. Be willing to experiment and don’t be afraid to break things. Unlike other disciplines such as chemistry or medical science, experimentation in CS carries significantly less risk. The worst that’ll happen is an error. 

This is the first edition. If anything is unclear, you can contact me directly at [cameron@cameronwhite.io](mailto:cameron@cameronwhite.io) and I’ll edit the book for people who may be using it later. The most recent edition of the book can be found on my GitHub: [github.com/CameronWhiteCS](https://github.com/CameronWhiteCS).

## Licensing

This book is licensed under the CC BY-NC-SA license, a kind of copyleft license. You are free to redistribute, remix, and build upon this work so long as the original attribution is maintained, modified and/or redistributed versions of this work are also licensed under the same license, and any derivative work(s) are used for non-commercial purposes. For more information, visit the CC BY-NC-SA page on the Creative Commons website. 

We are better off in a world where the gatekeeping of academic and scientific knowledge does not exist.

## Index
[Chapter I: Introduction to Java (Optional)](#chapter-i-introduction-to-java-optional)

[Chapter II: Arithmetic, Variables & Operators](#chapter-ii-arithmetic-variables--operators)

[Chapter III: Expressions & Order of Operations](#chapter-iii-expressions--order-of-operations)

[Chapter IV: Our First Working Program, Classes, Methods, & Method Overloading](#chapter-iv-our-first-working-program-classes-methods--method-overloading)

[Chapter V: public static void main(String[] args)](#chapter-v-public-static-void-mainstring-args)

[Chapter VI: Loops](#chapter-vi-loops)

[Chapter VII: Control Statements & Enumerated Types](#chapter-vii-control-statements--enumerated-types)

[Chapter VIII: The Foundations of OOP](#chapter-viii-the-foundations-of-oop)

[Chapter IX: Interfaces & Abstract Classes](#chapter-ix-interfaces--abstract-classes)

[Chapter X: Packages](#chapter-x-packages)

[Chapter XI: Data Structures](#chapter-xi-data-structures)

[Chapter XII: Exceptions](#chapter-xii-exceptions)

[Chapter XIII: Tips & Tricks](#chapter-xiii-tips--tricks)

## Chapter I: Introduction to Java (Optional)

The first programming language you’ll be expected to learn at UF while pursuing a computer science degree is Java. There will be many more you’ll eventually need: MatLab, JavaScript, C++, etc. Don’t worry about them for now. After you learn one language, the rest become far easier. 

But what separates Java from other programming languages? What makes it unique? Let’s look at a overview of the language. Java is:

* Object-oriented
* High-level
* Statically typed
* Semi-compiled

But what do these terms mean?

**Object-oriented** refers to Java’s predominant programming **paradigm**, or style. We won’t worry about the exact details of what that means right now, but to summarize, object-oriented languages attempt to model information by grouping together related data and combing it with **methods** that can manipulate or interact with the data in some way. The object-oriented paradigm is highly controversial: some people love it, and others think it was one of the biggest mistakes in software engineering.

**High-level** has different meanings depending on context. Older computer scientists would argue that anything more abstract than binary or assembly (assembly is basically glorified binary) is a high-level language. Younger programmers often tend to see languages like C and C++ as being **low-level** languages, though they were considered high-level when they were invented. Generally speaking though, high-level languages are more abstract and automate more processes for the programmer than low-level languages and make programming easier as a result.

Why would we ever want to use low-level languages? The short answer is sometimes we have to. High-level languages often come at the cost of performance and may not be suitable for intense calculations, building operating systems, or running a supercomputer. However, in situations where high-level languages can be used, they’re almost always preferred. 

**Statically typed** languages are very strict compared to weakly typed languages. We’ll see this in action soon, but the general idea is this: suppose we wanted to create a value ‘x’ and set it equal to 10. In a statically typed language like Java, we would need to tell the computer that we are creating an integer called x and that’s it’s equal to 10. _We have to explicitly tell the computer the **data type** of x_. In a weakly typed language like JavaScript or PHP, this type is determined automatically by the computer based on context. Here’s what that would look like in code:

Java: 

```java
int x = 10;
```

PHP:

```php
$x = 10
```

Java’s type system doesn’t apply to *just* variables, but the example given should illustrate the difference. Like almost everything in programming, this comes with trade offs, and a lot of it boils down to personal preference. I find statically typed languages easier to read, but some people find the repetition quite annoying, especially in situations where type of the data should be obvious. 

Statically typed languages can also sometimes get a performance boost when the computer doesn’t have to guess what type of data it’s dealing with, though this boost has gotten less meaningful over time with faster computers and more optimized languages. Finally, statically typed languages are considered “safer” because their strict typing system means it’s more difficult for a programmer to make mistakes.

**Compiled**, **semi-compiled**, and **interpreted** languages. This is probably the most complex topic covered in this introduction, and *you really don’t need to understand this section to understand Java*, but it’s nice to know for later in your computer science career. To understand the difference between these three types of languages, we need to think about how a computer actually processes instructions, and there are multiple ways this is accomplished.

Imagine you open a computer window that accepts instructions. You type into that window “print(5 * 5)” and you see “25” pop out on the screen. *In real time*, the computer interpreted your instruction and acted accordingly. The computer did no work in advance, and your simple program (calculating 5 * 5) was run by… another program, the window that you opened. This second program – the one that ran your own program – is known as an *interpreter*, and languages that operate using an interpreter are called *interpreted* languages. 

The best analogy is probably real-time translation with human languages where a language interpreter can hear someone speak and translate what they say as they talk. One caveat: interpreters aren’t limited to one instruction at a time as typed by a person with pauses in between. They can be used to execute entire pre-typed files as well, one instruction being executed after the other. If interpreters couldn’t do this, they would be far less useful. 

**Note**: How interpreters work behind the scenes is very complicated, and they don't always perform real-time translations. There is often some degree of preprocessing (or looking ahead)  

“But how does an interpreter work?” you may ask. After all, if an interpreter is a program, someone had to use code to create it at some point. So how did they create the interpreter? We have a bit of a chicken and egg problem here. 

We need to take a bit of a detour to understand what’s going on. Computers are physical devices that use electricity to store and manipulate information. I’m not very knowledgeable when it comes to physics. As far as I’m concerned, how computers accomplish this using electricity is magic. What’s important is the native language of computers is binary. All they know how to understand are streams of 1’s and 0’s represented by the presence or absence of electricity. All programming languages are, one way or another, converted into binary instructions so the computer can understand it in its “native tongue” so to speak. 

In the case of interpreted languages, our code is deconstructed by the interpreter and the product of that deconstruction eventually executes on the computer’s processor. But this adds an extra step. Couldn’t we just cut out the middleman and go straight from code to binary? The answer is yes, we can. Languages that do this are called **compiled** languages, and the programs that convert **source code** into machine code are called **compilers**. The process of converting source code to machine code is known as **compilation**. 

Why not always use compiled languages, then? Like everything in programming, there’s a trade off. Compiling a program can take a long time – up to several hours for the Linux kernel, Firefox, Chromium, and other large C programs. Additionally, compiled programs typically need to have their code compiled in advance, with the exception of just-in-time (JIT) compilation. This isn’t the case for an interpreted language since instructions are executed one at a time as they are fed to the interpreter. The benefit of compiled languages, though, is that their programs run significantly faster after the compilation process is finished. Virtually all applications where speed is highly important, like operating systems, are written in compiled languages like C and C++. 

The main takeaway here is that compiled languages do their "translation" in advance. It's more effort upfront, but it has its benefits. 

Ok, great, but this still doesn’t solve our chicken and egg problem. Compilers and interpreters are both kinds of programs presumably written in some kind of programming language, so how did we get them in the first place? The answer sends chills down my spine: **_there are people who have written compilers using assembly (glorified binary)_**. Doing something like that is a monumental but absolutely necessary task, because there’s simply no other option. The good news is that once we have a working compiler for a high-level language like C or Rust, we can make everything else (including interpreters and even other compilers) with our newly “unlocked” high-level language (for those interested in learning more, you may want to research the topic of [bootstrapping a compiler](https://en.wikipedia.org/wiki/Bootstrapping_(compilers)) 

Finally, let’s look at Java. It’s special. It uses a compiler, but the Java compiler doesn’t convert Java code into machine language. Instead, it converts it into something known as **Java byte code**. This Java byte code is then run by the **Java Virtual Machine (JVM)**. “This sounds like an interpreter, but with extra steps” I hear you say. And you’re right. The idea is similar (but not the same). The difference here is that we still get a performance boost by doing this compared to if Java was an interpreted language. The JVM is pretty fast, and many other languages such as Kotlin and Clojure now convert their code to Java byte code so it can run on the JVM. We won’t get into the exact reasons why, but by compiling byte code rather than machine code, our Java applications can be run on many different types of systems without changing our code in any way. This is known as **portability**.

### Why Learn Java?

The rationale for using Java comes down to a combination of business needs and technical details. Like most successful modern programming languages, Java is backed by a large corporation that ensures the language is up to date, secure, and working as intended. Apple has its Swift programming language, Microsoft has C# and TypeScript, and Java is one of Oracle’s products.

With powerful corporate entities behind these programming languages, developers (and other companies) can have a high degree of confidence that the software they build will work as intended and continue to work in the future. If developers encounter bugs with the programming language tools they rely on or the execution environments for these languages, the companies backing them have the resources to resolve them quickly. Can the same things be said about languages with less resources such as Ruby or the esoteric language known as [BrainFuck](https://en.wikipedia.org/wiki/Brainfuck)? 

Now on to the technical side of things. Java is an excellent candidate for making enterprise software where dozens or even hundreds of people are all working on a single, large code base. It’s often not the first choice when making a prototype, and it’s (fortunately) no longer seen as a first choice for web development. Java is also often rightfully criticized for being overly verbose: what could be accomplished in 50 lines of JavaScript might take 250 in Java. 

Despite this, Java has proven itself to be reliable and has been the world’s most popular programming language on more than one occasion, so it must be doing something right. 

### Conclusion

Let’s summarize:

* Java is an object-oriented language. This allows us to organize and reuse our code according to the object-oriented programming paradigm. 
* Java is a high-level language, meaning its easier to use than a lower-level language like assembly or C.
* Java is statically typed, meaning we have to be extremely specific about the kinds of information we’re programming with
* Java is semi-compiled, so it’s a relatively fast language and can be used on many different computer systems without changing our code. Java’s motto was at one point “Write once, run anywhere”. 
* Java shines as a tool for developing enterprise software due to its backing by Oracle and its technical features

## Chapter II: Arithmetic, Variables & Operators

Computer science is, as one of my favorite professors described it, a “cargo cult” of other scientific fields. It stands on the shoulders of math, electrical engineering, signal processing, information theory, and other seemingly unrelated disciplines. We would be remiss if we didn’t consider how these other fields are relevant to us.

There are other ways to think about programming, but thinking of it as a mathematical tool is the best approach early on. The analogy will fall off later when we get to more complex topics like inheritance and polymorphism, but it works well enough for now.

Much like in math, we can define **variables** and perform **operations** on those variables. Unlike in math, things are slightly more complicated, and there are more operations other than +, -, * and /. If you read Chapter I, you saw that Java is a statically typed language, meaning we have to define the _type_ of variables when we create them. But what types are we able to use? Here’s a chart outlining Java’s **primitive** data types (aptly named because of their simplicity):

| Keyword | Type | Size(bytes) | Minimum value | Maximum value |
|--|--|--|--|--|
| **byte** | integer number | 1 | -128 | 127 |
| **short** | integer number | 2 | -32,768 | 32,767 |
| **int** | integer number | 4 | -2,147,483,648 | 2,147,483,647 |
| **long** | integer number | 8 | -9,223,372,036,854,775,808 | 9,223,372,036,854,775,807 |
| **char** | Unicode character | 2 | 0 | 65535 |
| **float** | floating point number | 4 | 1.4 * 10^-45 | 3.4028235 * 10^38 |
| **double** | floating point number | 8 | 4.9 * 10^-324 | 1.7976931348623157 * 10^308 |
| **boolean** | True\false value | Undefined | N/A | N/A |

Ok, so we have multiple kinds of data, but the difference seems pretty trivial. Some types consume more computer memory (bytes) than others, but can store larger or smaller values as a result. Why not always use double or long since they can store the largest numbers? After all, a few bytes isn’t a big deal.

Whenever you’re dealing with thousands or hundreds of thousands or millions of numbers like in machine learning, those few bytes make a huge difference. However, if you’re using a few integers here and there to perform simple calculations where you could have used bytes, it really isn’t a big deal. You definitely won’t encounter encounter machine learning or massive data sets in Programming I, so you can safely use larger data types such as  integers, doubles, or whatever you please unless your assignment or professor tells you otherwise.

I would strongly recommend that people learning to program for the first time stick to handful of general-purpose data types simply because there are already so many other things to juggle. Worrying about whether or not your data can fit inside of the data type you choose to use adds needless complexity. Additionally, the smaller data types such as byte tend to be used very rarely in practice. int, double, and boolean are the most common by far.

Now, on to the specifics of some of the data types. One thing to consider when using doubles and floats is **precision**. You’ll learn about the why and how in Computer Organization, but doubles are more precise than floats. The more space a decimal number occupies in memory, the greater capacity for accuracy it has.

“Why does the boolean type have an undefined size?” That’s a good question, but the answer isn’t particularly satisfying. Oracle, the company behind Java, decided leave the question of how much space a boolean should occupy up to the people who make various versions of the Java Virtual Machine (JVM), the environment where Java code is executed. There is no single standard for its size.

Also, just an aside. If you’re familiar with them, strings _**are not**_ primitive data types. Java treats them kind of like primitives in terms of syntax, but they’re not the same thing. Strings are actually objects, which we’ll learn about later.
### Operators

| Operator name | Operator symbol | Number of inputs | Number of outputs | Output type |
|--|--|--|--|--|
| **Assignment** | = | 2 (binary) | 0 | N/A |
| **Addition** | + | 2 (binary) | 1 | numeric/varies |
| **Subtraction** | - | 2 (binary) | 1 | numeric/varies |
| **Multiplication** | * | 2 (binary) | 1 | numeric/varies |
| **Division** | / | 2 (binary) | 1 | numeric/varies |
| **Addition assignment** | += | 2 (binary) | 0 | N/A |
| **Subtraction assignment** | -= | 2 (binary) | 0 | N/A |
| **Multiplication assignment** | *= | 2 (binary) | 0 | N/A |
| **Division assignment** | /= | 2 (binary) | 0 | N/A |
| **Modulus assignment** | %= | 2 (binary) | 0 | N/A |
| **Increment** | ++ | 1 (unary) | 1 | numeric/varies |
| **Decrement** | -- | 1 (unary) | 1 | numeric/varies |
| **Greater than** | > | 2 (binary) | 1 | boolean |
| **Greater than or equal to** | >= | 2 (binary) | 1 | boolean |
| **Less than** | < | 2 (binary) | 1 | boolean |
| **Less than or equal to** | <= | 2 (binary) | 1 | boolean |
| **Equals** | == | 2 (binary) | 1 | boolean |
| **Not Equals** | != | 2 (binary) | 1 | boolean |
| **Logical AND** | && | 2 (binary) | 1 | boolean |
| **Logical OR** | \|\| | 2 (binary) | 1 | boolean |
| **Negation (Logical NOT)** | ! | 1 (unary) | 1 | boolean |
| **Ternary operator** | ? | 3 (ternary) | 1 | varies |

The information presented in the table is somewhat abstract. Let’s try and give some concrete examples of how we could actually use this information in a program. In the following sections, you will find an example of every operation and every data type. Code following two slashes is **commented** (ignored by Java) and I’ve highlighted it in green.

### Assignment Operator & Basic Math Functions

When it comes to creating variables in a program, there is some special vocabulary you should be aware of. In the code int x; , we say that x has been **declared**, but not **initialized**. **Initialization** is the process of giving an undefined variable a value for the first time (x = 5; would be an example in our case). **Assignment** refers to giving a variable a value, _even if_ it already has one. _Initialization is a specific type of assignment_. In the code comments below, there are examples of each.

**Note**: All numeric values including chars have a default value of 0 (or 0.0 for floating point number) and booleans default to false. Objects (including Strings) have a default value of null. Both objects and null will be covered later.

```java
double pi; //Variable **declaration** without assigning a value

pi = 3.415926; //Variable **initialization**

int radius = 2; //Declaration and initialization at the same time

double area = radius * radius * pi;

area = 0; // **Assignment**

int r = 20 % 7; //The % symbol (modulus operator) gives us the remainder of a division. 20 / 7 = 2 remainder 6. Therefore, r = 6.

int x = 3 + 2;

int y = 3 – 2;

int z = x / 2; //The result is 2, despite x being equal to 5. See explanation below.

double divisionResult = 5D / 2D; //The “D” after 5 and 2 signify that they are doubles. In this case, the result is actually 2.5 since we aren’t using truncated division. Non-decimal numbers without a D or F are interpreted as some kind of integer number. Additionally, “L” signifies a long (kind of whole number as seen in previous chart). D, F, and L can be upper- or lower-case.

divisionResult = divisionResult - 1F;  //Subtraction and variable **assignment**.
```

In Java, all _integer_ division (though not decimal division) is **truncated**, meaning the decimal part of the result of our division operation is simply ignored. If we needed to get the remainder of our division operation, we would need to use the modulus (%) operator. **Note**: modulus doesn’t return the numbers after the decimal point, but rather the _**remainder**_ of a division operation.


### Alternate Assignment Operators

+= , -=, *=, /=, and %= are all just shorthand operators. Java would be a complete language without them, but they’re nice to have. If we wanted to say x = x * 5, we can instead say x *= 5. Or if we wanted to say y = y / 5, we could instead use y /= 5. We can even do x %= 5. There are pretty self-explanatory.

### Increment & Decrement

Increment and decrement do what you would expect them to do. They take a single numeric value (not just integer numbers) and increase it or decrease it by one. Take a look at the following example:

```java
int x = 5;

x++; //x is now equal to 6

++x; //x is now equal to 7

x--; //x is now equal to 6

--x; //x is now equal to 5
```

What’s the difference between putting the – or ++ before the variable as opposed to after? To answer that, we need to look at another example:

```java
int x = 5;
int y = x++;  //y = 5 and x = 6. y is assigned the value of x and _then_ the value of x is increased by one.
int z = ++x; //z = 7 and x = 7. x is increased by one and _then_  z is assigned the value of x.
```

The difference is subtle, but expect a trick question on a quiz or an exam about this.

One interesting thing to note about the increment and decrement operators is that they actually modify the number they act on unlike most of the other operators. This is because they are simply short hand for the following expression: x = x + 1 (or x += 1).

### Mathematical Comparisons

Java allows us to compare numbers using the > (greater than), < (less than), >= (greater than or equal to), and <= (less than or equal to) operators. Here are some examples:

```java

boolean b1 = 5 > 5; //b1 = false

boolean b2 = 5 >= 5; //b2 = true

boolean b3 = 5 < 6; //b3 = true

boolean b4 = 1 >= 0; //b4 = true
```

### Logical Operators

Logical operators are operators that operate on and return boolean values. Here are some examples:

### Negation

Negation takes whatever you put into it and gives you the opposite.

```java
boolean var1 = true;

boolean var2 = !var1; //Since var1 was true, var2 is now false.
```

### Equals

The equality operator checks if two values are equal.

```java
int x = 5;
int y = 5;
boolean someBool = (x == y);  //someBool = true, since x and y are the same value. Parenthesis not needed, but makes it more clear what's going on
```

### Not equals

The not equals operator also acts on two booleans, but gives you the opposite of what equality would give you.

```java
int x = 5;
int y = 5;
boolean someBool = (x != y);  //someBool = false.
```  

### Logical AND

Logical AND can be modeled by the following **truth table**:

| input 1 | input 2 | output |
|--|--|--|
| **True** | **True** | **True** |
| **True** | *False* | *False* |
| *False* | **True** | *False* |
| *False* | *False* | *False* | 

Logical AND only gives us a value of true when **both** of the inputs we give it are also true. Here’s a code example:

```java
boolean b1 = true;

boolean b2 = true;

boolean b3 = false;

boolean b4 = false;

boolean result1 = b1 && b2 //result1 = true

boolean result2 = b1 && b3 //result2 = false

boolean result3 = b3 && b4 //result3 = false

```

### Logical OR

The logical OR function produces a value of true if _**either**_ of the things we put into it are true. Here’s it’s truth table:

| input 1 | input 2 | output |
|--|--|--|
| **True** | **True** | **True** |
| **True** | *False* | **True** |
| *False* | **True** | **True** |
| *False* | *False* | *False* | 

And some more examples:

```java
boolean b1 = true;
boolean b2 = true;
boolean b3 = false;
boolean b4 = false;
boolean result1 = b1 || b2 //result1 = true
boolean result2 = b1  || b3 //result2 = true
boolean result3 = b3  || b1//result3 = true
boolean result4 = b3 || b4 //result4 = false
```

### Ternary Operator

The Ternary operator is just weird. You need to type out a lot more to get it to work, and it’s less clear what it’s doing the first time you see it. The format for the ternary operator goes something like this:

```java
datatype variableName = someBoolean ? possibility1 : possibility2; 
```

Let’s use a more concrete example:

```java
boolean someBool = true;
int x = someBool ? 5 : 6;
```

If someBool is true, x will be 5. If someBool is false, x will be 6. I’d go more in depth explaining what’s going on, but in this case the example should make it obvious enough.

### Warning: Integer Overflow/Underflow

Now that we’ve seen how to manipulate data in Java, there’s something you should be weary of. Remember how different data types have different maximum and minimum sizes? Well, what happens if we have a byte with a value of 127 (it’s maximum) and add 1 to it? We would get -128. This is known as **integer overflow**. If we had a byte with a value of -128, subtracted 1, and got 127, that would be an instance of **integer underflow**. Both integer overflow and underflow are the source of many difficult to solve bugs and unexpected crashes. Be careful and watch out for this.

### Characters & Strings

The other data types were easy. The only other curve ball compared to traditional math is the boolean, except it’s as simple as true and false. Strings are slightly more complicated. While they **_aren’t primitive data types_**, Java kind of treats them like primitives in some ways. A **string** is an **array** of characters (char data type) used to represent text. Ok, so what’s an array? And earlier I said that the char data type represents a Unicode character, what is that?

Let’s start with arrays. We’ll cover how to use them later in the book, but an **array** is simply a list, or perhaps a container, with a set number of slots or entries. Arrays store **_sequential_** data. If we have an array of 100 ints, we have 400 bytes of sequential memory (since ints are 4 bytes each) that the computer reserves and recognizes as a list of integers. We will come back to how this ties into strings shortly.

Now, let’s explore the char data type further. It’s the black sheep of the primitive data types. Depending on context, a char can either be a number or a text character. Additionally, its minimum value is 0, unlike the other integer data types which can go far into the negatives. With that being said, suppose we had a system where we mapped certain numbers to certain characters in order to represent them. Maybe a could be represented by 1, A by 2, b by 3, B by 4, and so on.

As it turns out, there is a scientific standard that does exactly this. It’s called **Unicode**, and it’s an extension of an older standard called **ASCII** (American Standard Code for Information Interchange). In the Unicode **encoding** system, one character of text is represented by a particular combination of no more than 16 bits (2 bytes). With some clever bit-level manipulation, the Unicode standard is able to support over 1 million unique characters, including emojis.

With all of this in mind, it should be easy to see how we can combine arrays (effectively lists) of characters with the Unicode system to represent text. A sequence of numbers is interpreted as text according to a particular mapping. But that’s what’s going on behind the scenes. How do we actually create a String? It’s easy:

```java
String hello = “Hello, world!”; //Strings need to have an upper-case S as they are not primitives
```

characters, which I didn’t show earlier, are quite similar. The only difference is that you have to use single quotes:

```java
char c = ‘A’;
```

You can also do this, but please don’t... Unless you really know what you're doing!

```java
char c = 65; //65 happens to to be uppercase A.
```

You can use the + symbol to combine strings and even add numbers, booleans, and characters to strings. This isn’t addition, it’s actually called **concatenation**. Some languages like PHP use a different symbol for concatenation, but many like Java and JavaScript simply reuse the + sign. This generally doesn’t lead to too much confusion because you’ll typically have enough context as to what’s going on.

```java
String s = “Hello, ”;
String name = “Cameron”;
String concat = s + name; //We would get “Hello, Cameron”
String s2 = “The number is: ”;
int num = 5;
String concat2 = s2 + 5;  //We get: “The number is: 5”
String s3 = “The boolean is: ”;
boolean b = false;
String concat3 = s3 + b; //We get: “The boolean is: false”
```

### Chapter II Closing Remarks

That’s it. That’s all of the primitives that Java supports and almost all of the operators . There are _technically_ more operators, but they’re beyond the scope of Programming I, so don’t worry about them.

I would recommend that you memorize the size (in bytes) of each data type. It’s also useful to remember that **one byte is equal to 8 bits**. If you want to memorize the maximum and minimum values of each of the integer types, there’s a formula that makes it really easy:

```Maximum value = 2^(n-1) – 1```

```Minimum value = -(2^(n-1))```

Where n is the number of **bits**, not bytes, of the data type in question. Try it out with the number of bits for byte, short, int, and long and see if it matches up. The only exception is char, whose minimum is 0 and whose maximum is 16^2.  
  
The reasoning behind these formulas has to do with something you’ll learn in CDA3101 (Introduction to Computer Organization). I would also provide an explanation for the minimum and maximums for floats and doubles, but the formula is more complicated and would require explaining the IEEE 754 floating point number standard, something you’ll also learn in CDA3101.

## Chapter III: Expressions & Order of Operations

At some point or another, you’ve been in a math class and seen a question like this: “Evaluate the following **expression**: (5 * 5) / (1 * 1.1) + 6.2”. That’s a bit of a simple question, but it raises a question: what **_is_** an expression in more abstract terms? Simply put, an expression is a combination of mathematical operations that **evaluates** to a single, final value.

Much like in math, we can create expressions in programming. The added benefit is that we can manipulate **_any_** kind of data we can represent in a computer, not just numbers. So, let’s create some expressions that evaluate  to various data types to illustrate the point. While the parenthesis aren’t strictly necessary, I’ve used them to enclose the expressions so it’s clear what part is considered the expression and what part isn’t.

```java
boolean result = (true && true || false && true);  //We’ll cover whether result is true or false in the order of operations section
int x = (5 * 4 + 3 – 2); //21
int y = ((5 > 6) || 20 % 5 == 0) ? 0 : 1; // This one’s a doozy!
String s = (“Hel” + (“lo” + “, wo”) + “rld!”); //the “lo” + “, wo” section is executed first, because of order of operations, though it has no impact on the end result.
```

For mathematical expressions, the traditional PEMDAS order of operations holds true, with one exception: Java doesn’t support exponentiation as an operator. So, we’re left with PMDAS instead. But what about the logical operators not seen in regular math? They too have their own, brand new order of operations. If you want a complete list, take a look at [this page](http://www.cs.bilkent.edu.tr/~guvenir/courses/CS101/op_precedence.html) by Bilknet University in Turkey. There will be some you don’t recognize and that we don’t cover in this book, but it’s a complete list nonetheless. The most significant takeaway for right now is that AND has a higher priority than OR. So, our expression from earlier evaluates to true, because AND takes priority:

```java
boolean result = (true && true || false && true);

//is the same as
boolean result = (true || false)

//Which is the same as
boolean result = true;
```

That’s one of the trickiest ones, but there are other pitfalls as well. I encourage you to take a look at the page from Bilknet to see what priority all of the logical operators you’ve seen so far have. However, if your code relies on Java’s rather unintuitive order of operations, you may want to change it so it relies on parenthesis instead. You want your code to be clear and easy to read, not something arcane and indecipherable.

One final thing. In your code, anywhere where you use a variable, _you can replace that variable with an expression that evaluates to the same type_ **_no matter how complex it is_**_._ As an example, we could say x = 10, or we could say x = 2 * 5. This feature is very powerful.

## Chapter IV: Our First Working Program, Classes, Methods, & Method Overloading

In order to continue exploring programming through the lens of math, we need to first make a rather convoluted detour. I would show you how to make mathematical functions in Java as that would be the logical next step after variables and data types, except Java does not have functions. It has something called **methods**. Methods are _similar_ to functions and can perform everything that functions can, but they aren’t the same thing. Additionally, we cannot have a method unless we also have something called a **class**.

This is where things get very tricky. I suppose the best place to start is to show you the simplest possible Java program, as it uses both a method and a class. Until now, I’ve only showed code **snippets**. If you put them into a .java file and tried to compile and run it, it wouldn’t work. So, let’s examine the simplest possible program that will work. If you were to save this code in a file called HelloWorld.java, you could then compile the code, run it, and you would see “Hello, world!” on your screen.

```java
class HelloWorld {  
    public static void main(String[] args){  
        System.out.println(“Hello, world!”);  
    }  
}
```
If this is the first time you’ve seen this, you’re probably very confused. And you should be. There are a lot of moving parts here for something as simple as printing “Hello, world!” to a computer terminal. There’s also a lot of brand new syntax not seen in the previous sections where we were simply defining and modifying variables.

To get to the point where we can understand the above code, we need to take a step back and understand the concept of a class. Then we can learn about methods. Finally, after we tie up some loose ends in the next chapter, we can completely understand everything going on in the above program.

The one thing you should know about the above code is that anything we put inside of the second pair of curly braces is going to execute when our program starts. We’ll cover the logistics of why and how this happens later, just know that the inside of that second set of braces acts at the entry point of our program, and that the snippets from previous sections will function as intended when inside the braces. We’ll be exploiting this new knowledge in the following sections.

### Classes

The concept of a **class**, short for classification, is extremely abstract. A class is effectively a description (or model) of a person, place, thing, or idea. A class describes one of these things through the use of data. For example, suppose we wanted a model that could _describe_ a UF student. We would do it like this:

```java
class Student {
    String name = “Default name”; //This is how we assign default values  
    int age;  
    String ufid;  
    int numberOfClasses = 3; //Another default
    int creditHours;
    int graduationYear;  
    double flexBucks;
}
```

Note: Like we mentioned earlier in chapter II, numeric values default to 0, booleans to false, and objects (including strings) to a special value null.

Yes, we could go further, but for our purposes such a simple model is enough. It’s also worth noting that classes are typically stored **_in their own unique files_**. You should always do this when creating a new class unless your professor tells you not to for the purpose of an assignment. In the real world, no one would be caught dead cramming multiple classes into a single file. The good news is that it’s as simple as it sounds. You can simply take the above **class definition**, stick it into a text file called Student.java, and that’s the end of the story. It should be noted that the name of the file and the name of the class in the code should be identical. If we create a class with class Animal { … }, we should also save it as Animal.java – same spelling with the same case (Java is case sensitive).

For now and for the sake of simplicity, save all of your .java files in the same folder. We’ll cover better organization practices (and what code we need to use to get those practices to work) later on. For the time being, your code won’t work if your files are in different folders.

Ok, great. We have this hypothetical model of a UF student. What can we do with it? Remember earlier how we learned that we could run any code inside that second set of curly braces? Let’s take the earlier example and modify it slightly:

```java
class HelloWorld {  
    public static void main(String[] args){  
        Student student1 = new Student();
        student1.name = “Greg”;
        student1.age = 21;
        student1.ufid = “0000-0000”;  
        student1.numberOfClasses = 4;
        student1.creditHours = 110;
        student1.graduationYear = 2020;
        student1.flexBucks = 20D;  
    }  
}
```

What on earth did we just do in the above code? Well, using the Student class, we made a student **object** named student1. We use classes to create objects, also known as **instances** of that class.  They’re called _instances_ because we can create many students with a single Student class:

```java
class HelloWorld {  
    public static void main(String[] args){
    Student student1 = new Student();
        student1.name = “Greg”;
        student1.age = 21;
        student1.ufid = “0000-0000”;  
        student1.numberOfClasses = 4;
        student1.creditHours = 110;
        student1.graduationYear = 2020;
        student1.flexBucks = 20D;
		
        Student student2 = new Student();
        student2.name = “Molly”;
        student2.age = 20;
        student2.ufid = “0000-0001”;  
        student2.numberOfClasses = 2;
        student2.creditHours = 7;
        student2.graduationYear = 2050;
        student2.flexBucks = 0.5D;
		
        System.out.println(student1.name); //Prints: “Greg” to the screen
        System.out.println(student2.name); //Prints: “Molly” to the screen
    }  
}
```
Another way to think of a class is that it’s a “factory” that produces objects, or perhaps that a class is a blueprint used to create objects.

  

The syntax isn’t particularly complicated compared to when we were creating and assigning regular variables before. The only odd bit is Student student1 = new Student(). Why does the uppercase _Student_ appear twice? Why the opening and closing parenthesis? As much as I hate to keep saying it, we’ll cover that later. We’re already on a big enough tangent as is. For now, just know that the provided syntax is the basis for creating objects from classes.

**Note**: the only reason we could say student1.name = “Greg” is because we put “String name;” inside of the Student class. If we tried doing student1.randomVariable = “Random”, we would get an error, because randomVariable isn’t a **field** of the Student class. Name, age, uifd, and all the other variables we listed inside of the Student class are considered to be its **fields**. Some programming languages (such as JavaScript) allow for adding fields to objects on the fly. Java does not permit this.

Okay, cool. We made two students. Each student object has _its own_ _separate_ variables associated with it that are known as  **_fields_**. If we change the name or ufid of student1, this has no effect on student2. But how is this useful? All we’ve done here is use a more complex way of storing simple data.If this was all classes could do, they would be pretty worthless outside of acting as a way to organize data.  Classes only become truly useful when we combine them with methods. So, let’s move on to the next section and learn about methods.

### Methods

Let’s save we have our Student class from before:

```java
class Student {
    String name = “Default name”;  
    int age;  
    String ufid;  
    int numberOfClasses = 3;
    int creditHours;
    int graduationYear;  
    double flexBucks;
}
```

What if we wanted to add a way to be able to calculate if a student was going to graduate at the end of this semester? Assuming creditHours refers to the number of credit hours previously earned and each class the student is currently taking awards 3 credits, that would be a simple calculation:

```java
boolean willGraduate = student1.creditHours + student1.NumberOfClasses * 3 >= 120;
//Remember, according to the order of operations, multiplication and addition take priority over >=
```
This is a perfectly adequate way of performing this calculation, but there are a few problems. For starters, it’s a lot to type out, especially if we need to perform the same calculation again and again. And what if the number of credit hours needed to graduate in the state of Florida or at UF changed at some point? We’d potentially need to update our code in many places, which is a pain and a huge waste of time.

This is precisely where **methods** come in. I’ll create one that is able to calculate willGraduate, then explain what’s going on:

```java
class Student {

    String name = “Default name”;  
    int age;  
    String ufid;  
    int numberOfClasses = 3;
    int creditHours;
    int graduationYear;  
    double flexBucks;
	
    boolean willGraduate(){ //The method definition starts with the word “boolean”
        return student1.creditHours + student1.NumberOfClasses * 3 >= 120;  
    } //This second brace is the end of the method definition
	
}
```

Now if we ever wanted to calculate whether a particular student was going to graduate this semester, all we have to do is this:

```java
Student student1 = new Student();

student1.name = “Greg”;
student1.age = 21;
student1.ufid = “0000-0000”;  
student1.numberOfClasses = 4;
student1.creditHours = 110;
student1.graduationYear = 2020;
student1.flexBucks = 20D;

boolean willHeGraduate = student1.willGraduate();
System.out.println(willHeGraduate);
//Prints true, since greg would have 122 credit hours.
//If we had a second student object with only 60 credit hours, it would print false.
// The output of the method depends on which object we use to **call** it.
```

And just like that, we can reuse the same _**method**_ for any student without having to type out all that code from earlier over and over again. The other benefit is that if we ever need to update how the calculation works, we can do so by editing only a single method rather than updating code all across our program. This approach is infinitely better than what we started with! But let’s not get ahead of ourselves. That’s a lot of new syntax, so let’s evaluate it piece by piece.

Much like when we create variables, we have to declare what type a method is as well. In the above method, we wrote boolean willGraduate(). What are those parenthesis doing there? As I’ve said before, I promise we’ll get there soon™. Let’s instead focus on the word boolean at the front. In this case, boolean is what is known as the method’s **return type**. The _**return type**_ is what we get back from the calculation. Unsurprisingly, we used the word _return_ in our code to say “Hey, please send this value back to whoever **called** the willGraduate method”.

The brackets enclose what is known as the **method body** (so named because it’s the main portion of the method), and the willGraduate() part is known as the **method signature.**

It should be noted that the method body can perform many instructions, not just one. In this case, we were able to fit everything on a single line, but we could have done this instead:

```java
boolean willGraduate(){
    int finalHours = creditHours + numberOfClasses * 3;
    return finalHours >= 120;  
}
```

Yes, there are a lot of pieces here. But the general idea is still simple: we were able to add functionality to the Student class that lets us easily and quickly determine whether or not a given student will graduate this semester. The tricky part is understanding the syntax the first time you see it. Let’s review with a color-coded version:

```java
boolean willGraduate(){
    int finalHours = creditHours + numberOfClasses * 3;
    return finalHours >= 120;
}
```

The word **boolean** is the return type, ```willGraduate()``` is the method signature, and everything else is the method body. ```return finalHours >= 120;``` an example of a  **return statement**. _After the return statement is executed, our method will end and cannot execute any more code._

Hopefully it’s clear what’s going on, and hopefully you’re starting to see that what we’ve made is almost identical to a mathematical function. _P__rovided_ _two_ _inputs (creditHours and numberOfClasses)_ _, we get a single true/false output._

We made our willGraduate method interact with the fields of the student class, but we didn’t _have_ to. Methods have the option to operate on fields, but they can also operate on data we provide to them. To demonstrate this, let’s make a new class with 0 fields and only a single method:

```java
class Calculator {
    double f(double x){
        return x * x;
    }
}
```

Let’s also slightly modify our simplest possible program from earlier:

```java
class HelloWorld {  
    public static void main(String[] args){  
        Calculator calc = new Calculator();
        double result = calc.f(5D);
        System.out.println(result); //prints 25  
    }  
}
```

After an incredibly ridiculous tangent, we have just created the classic math equation y = x^2 or f(x) = x^2. We did this by creating a method named f just like we did before. However, this time, there are a couple of differences. Firstly, we added the **parameter** _x_ to our method signature. When we called f and got 25 as the result, we provided 5D as an **argument**. A parameter and an argument are not the same thing. The difference between a parameter and an argument is subtle, and I’m pretty sure most even the most cruel Programming I professors aren’t going to pull a gotcha question like that, but now you know: parameters are in the method signature, and arguments are what we provide when we call a method.

  

The second difference is that this method doesn’t operate on any fields, because the Calculator class has no fields. This is how methods are different from math functions: they can operate on both fields _**and**_ the arguments provided to them. In this example, the calculator class had no fields, but there’s nothing that prevents us from adding fields to it. If we wanted to give the Calculator class a field called pi with a default value equal to 3.1415926 and use it for other mathematical methods, that would be fine.

  

Let’s add another method to the calculator class as well as that hypothetical pi value. Let’s also add a method with two parameters:

```java
class Calculator {
    double pi = 3.1415926;
    
    double f(double x){
        return x * x;
    }
    
    double areaOfCircle(double radius){
        return pi * radius * radius;
    }
    
    double volumeOfCylinder(double radius, double height){
        return pi * radius * radius * height;
    }
    
}
```

When we have a method with multiple parameters, we separate them with commas. When we call a method with multiple parameters, the arguments are comma separated as well:

```java
class HelloWorld {  
    public static void main(String[] args){  
        Calculator calc = new Calculator();
        System.out.println(calc.f(5D)); //prints 25
        System.out.println(calc.areaOfCircle(5D)); //Roughly 78
        System.out.println(calc.volumeOfCylinder(5D, 10D));
        //Roughly 785. Note the comma seperated arguments  
    }  
}
```

### Constructors

There is a special kind of method known as the **constructor**, aptly named because they are used to construct objects (computer scientists aren’t known for their linguistic creativity). Let us modify the student class from the previous section. Some fields and methods have been omitted for the sake of brevity.

```java
class Student {

    String name = “Default name”;  
    int age;  
    String ufid;
    
    Student(String name, int age, String ufid){
        this.name = name;
        this.age = age;
        this.ufid = ufid;
    }
    
}
```

The constructor of this class is highlighted in blue. Constructors differ from typical methods in two ways: there is no return statement nor is there an (explicit) return type. The name of the constructor is identical to the name of the class.

We provide arguments to a constructor when we create a new object:

```java
Student greg = new Student(“Greg”, 21, “0000-0000”);
System.out.println(greg.name); //Unsurprisingly prints “Greg”
```

All classes have at least one constructor (more on multiple constructors in the next section). However, by default classes only have a single constructor with 0 arguments that does nothing when called. Any one of a class’s constructors can be used to create an object. When at least one constructor is manually created, the default empty constructor will no longer exist unless it is explicitly re-created.

Constructors can execute _**any**_ code, but ideally they should be used to assign values to a class’s properties. If you wanted to, you could use something like System.out.println inside of a constructor.

There is one more thing worth nothing in this section. In the above example, the reserved key word “this” is used inside the constructor. This may seem strange at first, but it serves a very important purpose. Inside the constructor, we are taking in arguments with the same names as the fields of our class. If we didn’t use the this key word, we would be doing something like “x = x”, a meaningless expression. Of course x is equal to x!

By using this.name = name, what we are saying is that the property called name is being assigned the value of the argument called name. In other words, the above constructor in blue is logically equivalent to the following one:

```java
Student(String student_name, int student_age, String student_ufid) {
    name = student_name;
    age = student_age;
    ufid = student_ufid;
}
```

For the sake of clarity, I often use this even where is not strictly necessary. Both approaches – using the same variable names in conjunction with this and using separate names altogether – are acceptable. Even if you choose not to use this, you should still be aware of what it does. A relatively common approach to avoid using this is prefixing argument names with an underscore:

```java
Student(String _name, int _age, String _ufid){
    name = _name;
    age = _age;
    ufid = _ufid;
}
```

It should be noted that the this key word should not be used to reference static variables. Doing so would make no sense. “this” refers to _**this current object.**_ Since static variables are not tied down to a particular object and instead belong to the class itself, this should never be used in a static context.

### Method Overloading & Default Values

Java has something called **method overloading** that allows us to have multiple definitions for a method so long as the method signature for each definition is different. Here’s an example:

```java
class Student {

    int hoursSlept;
    
    Student(int hoursSlept){
        this.hoursSlept = hoursSlept;
    }
    
    boolean willPassExam() {
        return hoursSlept >= 8;
    }
    
    boolean willPassExam(boolean isHungover) {
        return hoursSlept >= 8 && isHungover == false;
    }
    
}
```

We have two methods with the same name, but different signatures and different definitions. The same thing can be done with constructors as well:

```java
class Student {

    int hoursSlept;
    
    Student(){
        this.hoursSlept = 8;
    }
    
    Student(int hoursSlept){
        this.hoursSlept = hoursSlept;
    }
    
    boolean willPassExam() {
        return hoursSlept >= 8;
    }
    
    boolean willPassExam(boolean isHungover) {
        return hoursSlept >= 8 && isHungover == false;
    }
    
}
```

One of the more useful applications of method overloading is creating default values for parameters:

```java
class Student {

    //Primary definition
    boolean willPassExam(int hoursSlept, boolean isHungover){
        return hoursSlept >= 8 && isHungover == false;
    }

    //Overload #1
    boolean willPassExam(int hoursSlept){
        return willPassExam(hoursSlept, false);
    }

    //Overload #2
    boolean willPassExam(){
        return willPassExam(8, false);
    }

    //Overload #3
    boolean willPassExam(boolean isHungover){
        return willPassExam(8, isHungover);
    }

}
```

For more complex methods definitions, this is extremely useful. It allows us to avoid repeating code (one of the main goals of object oriented programming). We simply define the primary method a single time and can then reference it when we overload it. If we change the primary method definition, the overloaded methods are updated automatically as a consequence.

### Chapter IV Closing Remarks

Chapter IV was pretty dense. There’s a lot of new syntax, though the underlying ideas should be familiar. To summarize, we:
  
* Created classes, which can be used to store related information and even model real-world things
*   Added methods to those classes to manipulate the data they store
*   Added parameters to those methods in order to make them like math functions, but better
*   Created constructors to build objects more easily
*   Overloaded both methods and constructors to achieve code reuse
    
The examples given were simple. We created a Student class and included a method to calculate if a given student will graduate at the end of the current semester. We also created a simple calculator class that contained some basic mathematical operations.

These might seem like pretty trivial examples and they don’t necessarily explain _why_ we would want to create classes or methods. The rationale will make more sense as you gain more experience.

One of the big takeaways from this chapter should be that methods actually make classes worth having. Instead of using class simply to store related data, we can couple that data with what are effectively mathematical functions (though not quite). By combing related data with methods, we can use classes to organize our code in a way where related data and processes are all lumped together instead of cramming everything from our entire program into a single location. The latter approach gets very difficult to work with very quickly.

In Java, no code can exist outside a class, so we’re left with only methods as a consequence. However, there are languages such as JavaScript and Python that support both methods and functions! In JavaScript, for example, defining f(x) = x^2 is as simple as this:

```javascript
function f(x){
    return x * x;
}
console.log(f(5)); //prints 25 in JavaScript
```

The above snippet could be in an empty file entirely outside of a class, making it a function. Methods operate on fields and arguments provided to them while functions can only operate on arguments.

## Chapter V: public static void main(String[] args)

If you paid careful attention to the “Hello, world!” program from the last chapter, you may have noticed a few oddities. For one, it contains a method called main, but its return type is listed as “void”. Not only that, the word “public” appears in front of the return type as well as “static”. And what kind of a parameter is String[] args? This chapter is going to tie up a few loose ends. By the end, the hello world program should finally make sense. The only exception is the “public” key word which can’t yet be adequately explained with the contents of this book so far. It will be discussed in a later chapter.

The individual sections of this chapter have very little to do with one another, but they’re all important in their own right. I would recommend that you read them in order, but you don’t necessarily need to. If the direction of this chapter seems to be all over the place, that’s because it is.

### Void

Let’s start with the concept of void, since its the easiest. Unlike math functions, both programming functions and methods have the ability to produce no output whatsoever. If this is the case, the function or method has a **void** return type.

Why would we do this? Sometimes in programming, we want code that just _does_ something, not code that calculates something. In fact, we’ve already repeatedly used a void method. System.out.println is an example of one. It doesn’t perform any kind of calculation, it simply prints whatever we give it to the screen. For the sake of another example, suppose we wrote a multi-player game and we had code that kicked or banned a player from the server. That’s not really a calculation, that’s more of an action, so void would likely be a suitable return type for a kickPlayer(int playerID) method.

One property you should be aware of for void methods is that despite the fact that they return no data, we can still use return statement inside of them. We simply put “return;” with no value and the method will stop in its tracks. We will cover why this is useful later when we cover control statements.

“But wait!” you say. “Don’t we need an object to use a method? How can System.out.println be a method? Where’s the object?” That’s both a good question and an equally useful segway into our next topic: the static key word.

### Static

The static key word is what’s known as a **modifier**. Modifiers can change the behavior of classes, methods, or fields in some way. We’ll cover other modifiers in a later chapter, but for now, let’s focus on static.

```java
class Calculator {

    static double pi = 3.1415926;  
    
    static double circleArea(double r){  
        return pi * r * r;  
    }  
    
}
```

In the code above, we are effectively designating both pi and circleArea as _**belonging to the class itself**_, NOT a particular instance of a class (at least that’s how I like to think of what static does. Some tenured professor somewhere is probably typing an angry email right now about how wrong I am). This has a few implications:

*   Code inside of a static method **cannot** interact with non-static fields or non-static methods in the same class. The reverse isn’t true, though.  Non-static methods _**can**_ access static methods and variables.
*   We do not need to create an instance of Calculator in order to reference pi or call the circleArea method. We can instead reference the class itself.

Let’s see what this means in practice:

```java
class HelloWorld {

    public static void main(String[] args){
        double result = Calculator.circleArea(5D);
        System.out.println(result);
    }

}
```

Because we marked the circleArea method as static, we don’t have to create a Calculator object to use it! But what would happen if pi wasn’t static?

```java
class Calculator {

    double pi = 3.1415926; //No longer static
    
    static double circleArea(double r){
        return pi * r * r;
    }
    
}
```

We would get an error. Why? Remember, each object that we make using a class gets its own copy of each **non-static** field in the class. That’s how we were able to have multiple student objects with different values. So, if we had 10 Calculator objects floating around, there would be 10 pi’s as well since we changed pi to no longer be static. So if there are 10 Calculators each with their own pi value and we want to reference pi in a **static context**, how do we know which pi to reference? After all, you could change the value of pi by doing something like this:

```java
Calculator calculator1 = new Calculator();
calculator1.pi = 0;
Calculator calculator2 = new Calculator();
```

The answer is we can’t know which pi we’d be referring to. That’s why it’s not possible to reference a non-static method or field from a static context. The reason we can’t reference non-static methods either is because non-static methods are able to use non-static fields for their calculations, which would result in the same problem.

We don’t have the same problem going in reverse, however. This would be perfectly valid code:

```java
class Calculator {
    static double pi = 3.1415926;
    
    //Non-static methods can reference static fields and methods
    double circleArea(double r){ 
         return pi * r * r;
    }
}
```

Since pi is static, there’s only one copy of it that exists, so our cirlceArea method doesn’t encounter the dilemma of not knowing which variable to reference.

### String[] args

We already learned about strings earlier on, so that shouldn’t be confusing. What is confusing is the whole [] deal. What is []?  
  
the [] in String[] args signifies that args is an array, which we already learned about on a conceptual level. To review, an array is basically a _fixed length_ list (or container) that holds a particular data type or type of object.

There are two ways to create an array:

```java
String[] array1 = new String[100]; //Create a new String array with 100 strings
int[] array2 = new int[50]; //int int array with 50 entries
Student[] array3 = new Student[25];
```

OR

```java
//We must specify all the elements in the array in advance
short[] array4 = {1, 1, 2, 3, 5, 8, 13, 21};
```

If we use the first technique, we have to manually assign each value one at a time like this:

```java
array1[0] = 1;
array1[1] = 1;
array1[2] = 2;
array1[3] = 3;
array1[4] = 5;
```

If we want to access the **element** at a given array **index**, we use the following notation:

```java
//prints the 5th (or 6th if you fancy, see explanation below) item in the array
System.out.println(array1[5]);
```

Warning! Arrays in Java are **0-indexed** arrays, meaning that to access the first element of the array we need to use array1[0]. This isn’t a Java quirk, though. The overwhelming majority of languages do this. A notable exception is MATLAB, which is used by these plebeians called “engineers”.

If you attempt to reference an element that doesn’t exist because it’s out of bounds for the array you’re using, you will get an error. Additionally, the elements in an array will default to either 0 for numbers/characters, false for booleans, or null for objects (including Strings) just like variables and class fields. Null is probably the _single biggest_ cause of errors and crashes in Java, so try to avoid null values when possible or handle them correctly (we will explain how to do this later).

Finally, we can find out the length of an array by accessing its length property:

```java
System.out.println(arr1.length); //Prints 100
```

**Note**: Despite the maximum index being 99, its length is 100.

### Putting it all together

Now that’s we’ve covered classes, objects, void return types, the static key word, and arrays, we can finally analyze our HelloWorld program piece by piece:

```java
class HelloWorld {
    public static void main(String[] args){
        System.out.println(“Hello, world!”);
    }
}
```

*   We have a class named HelloWorld, though the name is irrelevant in this case.
*   Inside of the HelloWorld class is a single, static method called “main”. This means that the main method basically belongs to the HelloWorld class itself rather than a particular HelloWorld object.
*   The main method is void, meaning that it _does_ something rather than calculate something.

Why does this matter? Well, all programs logically need a starting place. And in the case of Java programs, the Java Runtime Environment (JRE) demands that the programmer provide it with a very specifically crafted starting point. You can have many different starting points in one program that you use for different occasions, but when the time comes to run the application, the single “main” method you provide to the JRE at runtime needs to have the following characteristics:

*   It must be marked as public (again, we’ll cover this in a later chapter)
*   It must be static
*   it must have a void return type
*   It must be called “main”
*   It must take a single argument that is an array of Strings

These are pretty stringent requirements. The only thing it allows us to change is the name of the parameter. It’s typically “args” (short for arguments) as seen above, though it could be named anything.

The fact that it’s typically called args isn’t arbitrary. In fact, it’s possible to provide our program with these arguments when we launch it from a **command line interface (CLI)** such as the command prompt on Windows or a Bash terminal on MacOS/Linux. Here’s a simple program I wrote that prints the first three arguments provided to it when it starts:

```java
class Whiteboard {
    public static void main(String[] args) {
        System.out.println(args[0]);
        System.out.println(args[1]);
        System.out.println(args[2]);
    }
}
```

And here’s what I got on my computer when I ran it:

![](https://i.imgur.com/ETuQGWZ.png)

As you can see, I was able to provide the program with user input when the program started. The arguments I provided were separated by spaces, and the Java Runtime Environment converted them into something the Java Virtual Machine could use. However, being able to print some strings isn’t the most practical thing in the world. And not only that, if I had provided the program with less than 3 strings, there would have been an error. And what if I wanted to provide the program with a number, not a string? With techniques we’ll explore later, we’ll eventually be able to rectify these shortcomings and even convert the input we receive into other data types.

### Chapter V Closing Remarks

At first, the HelloWorld class looked rather ridiculous and confusing. Now, your knowledge of classes, methods, the void return type, and the static key word should provide the framework necessary to understand what’s going on. Now that all that’s been squared away, we can continue exploring programming through a mathematical lens.

The bit about accepting user input isn’t that important to understand right now, but I wanted to show it because that’s the only reason for the String[] args bit of code and illustrates why it exists. If you aren’t aware that Java can accept user input this way, String[] args seems rather arcane and illogical.

## Chapter VI: Loops

### For Loops

If you haven’t already, you will eventually see the following symbol in a math class: **Σ**.  For the uninitiated, this is the letter sigma from the Greek alphabet. In math, it’s a way to compactly write the sum of a list of numbers. For example, if we wanted to express the sum 1 + 4 + 9 + 16 … + 100, we would write the following:

![](https://i.imgur.com/KSvqXrf.png)

The variable x at the bottom is a counting variable. We give it an initial value (1 in this case). We then evaluate x^2 for whatever x happens to be, add the result to our current sum, and then increment x by 1. We do this until x is equal to the value on top of the sigma (10). Here’s a table to illustrate what’s going on:

```f(x) = x^2```
| Iteration | Value of x | f(x) | Current sum |
|--|--|--|--|
| 0 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 |
| 2 | 2 | 4 | 5	 |
| 3 | 3 | 9 | 14 |
| 4 | 4 | 16 | 30 |
| 5 | 5 | 25 | 55 |
| 6 | 6 | 36 | 91 |
| 7 | 7 | 49 | 140 |
| 8 | 8 | 64 | 204 |
| 9 | 9 | 81 | 285 |
| 10 | 10 | 100 | 385 |

Therefore,

![](https://i.imgur.com/KSvqXrf.png)

 = 385

The same procedure can be used to evaluate the sum of any function, not just x^2, but we used it here due to its simplicity.

This is a slight tangent, yes, but I mention it since we’re exploring programming through the lens of math. And as it turns out, programming and math have quite a bit in common. If we wanted to express the same thing in code, we could do it like this:

```java
class Sigma {  
    public static void main(String[] args){  
    
        int total = 0;  
        
        for(int i = 1; i <= 10; i++){  
            total += (i * i);  
        }  
        
        /*Total is now 385.*/  
    }  
}
```

Like before, we have some new syntax to analyze. Let’s isolate the **for loop** and examine it more closely and examine it as an algorithm:

Step 0 (set up): total = 0
Step 1: i = 1
Step 2: If i is <= 10, continue to step 3. Otherwise, we’re finished.
Step 3: total = total + (i * i)
Step 4: add 1 to i
Step 5: Go back to step 2.

The idea behind a for loop should be clear. We’re not done here though. This is programming. We can do far more than simply calculate a few sums.

Remember earlier how we learned to use arrays? As luck would have it, for loops and arrays pair quite nicely together:

```java
int[] numbers = {1, 1, 2, 3, 5, 8, 13, 21, 34}; //Fibonacci sequence

for(int i = 0; i < numbers.length; i++){
    System.out.println(numbers[i]);
}
```

In this case, we weren’t using the for loop to perform any kind of calculation. We instead used it to print a list of numbers. Unlike in math, we aren’t limited to _just_ pure calculations. Note: We start the integer i at a value of 0 and allow it to go as high as numbers.length – 1. This is because we used < instead of <= in our for loop. This is a very important distinction and can be tricky when you’re first learning to use loops. Had we used <= instead, Java would have thrown an error. This is because the loop would have attempted to access numbers[10] which doesn’t exist since the highest index is 9. Remember, Java’s arrays are 0-based.

If you don’t fancy the above syntax, there is another option. For simply iterating through an array, you can use this alternative, more compact syntax to accomplish the same thing:

```java
int[] numbers = {1, 1, 2, 3, 5, 8, 13, 21};

for(int i: numbers){
    System.out.println(i);
}
```

The disadvantage of this syntax is that we no longer have a counting variable and we therefore no longer know the index of the element we are accessing. In some cases, this is a problem and we must rely on the other syntax that includes a counting variable.

### While loops

If you aren’t a fan of the for loop at all, I’ve got an alternative for you. The **while loop**:

```java
int i = 1;
int total = 0;
while(i <= 10){
    total = total + (i * i);
    i++;
}
```

The idea is almost the same, and the while loop is actually much simpler to understand albeit less compact. The syntax combined with the word “while” makes it incredibly obvious what’s going on. For as long as the expression in green returns true, the orange code will continue executing.

### Do-While Loops

What if you’re filled with teenage/early 20’s angst and want to rebel against both the for and while loop because you have a burning desire to express your alleged individuality through vapid displays of non-conformity? Well, I present to you the **do-while loop**:

```java
int i = 1;  
int total = 0;  
do {  
    total = total + (i * i);  
    i++;  
} while (i <= 10);
```

The unique thing about the do-while loop is that we’re guaranteed that the code inside of the do { … } block will execute _**at least**_ once. This is because the do{ … } block is executed first and _then_ we check the while( … )  condition to see whether or not we should continue to the next iteration. This is unlike the for and while loops where the condition is checked first.

I’ll be honest, no one uses the do-while loop. It’s perfect for hipsters. Your professor will want you to know it, but I can think of only a single occasion where I’ve ever used this thing, and I think most people fall into the same category.

Now that we have the basics of looping down, you may wonder: can we create an infinite loop? The answer is yes, of course we can, though I would strongly recommend against it. Infinite loops often occur by accident, though they are highly undesirable. Unintended infinite loops effectively cause your program to crash because nothing else can occur until your loop is finished. Additionally, infinite loops are going to be a massive drain on your computer’s hardware. If you run the following infinite loop, you should see a spike in your CPU usage and will likely hear your computer’s fans turn on to keep your CPU cool:

```java
while(true){  
    System.out.println(“Loopy!”);  
}
```
Again, I don’t recommend you try it, but you can.

Accidental infinite loops occur when we unintentionally create and unachievable end condition for a given loop. For example:

```java
for(int i = 0; i != 27; i += 2){  
    System.out.println(i);  
}
```

Because i started at a value of 0, it’s being increased by 2 each iteration, and 27 is an odd number, our loop will never end.

### Loop-De-Loops

Loops can go inside of loops, and this practice is actually quite common. But we need a _reason_ to have a loop in a loop, so let’s create an _array of arrays_ (yes, you read that correctly) to demonstrate:

```java
//A 100 x 100 2D array
int[][] array2D = new int[100][100];

//A 100 x 100 x 100 array
int[][][] array3D = new int[100][100][100];

// Things get slightly more complicated with this syntax,
// but it’s still just like when we defined arrays from before.
int[][] inlineArray2D = {  
    {0, 1, 2, 3, 4}, //inlineArray2D[0]  
    {5, 6, 7, 8, 9}, //inlineArray2D[1]  
    {10, 11, 12, 13, 14},  
    {15, 16, 17, 18, 19},  
    {20, 21, 22, 23, 24} //inlineArray2D[4]  
}; 
```

These are often labeled **multi-dimensional arrays**, but more accurately they are arrays of arrays. I’ve made this tangent because multi-dimensional arrays are useful, but more importantly so you can see a practical application for a loop of loops.

Now that we have some data, let’s use two for loops to print it out in order. We will be borrowing the <I, J, K> notation from vector math.

```java
for(int i = 0; i < inlineArray2D.length; i++){  
    for(int j = 0; j < inlineArray2D[i].length; j++){  
        System.out.println(inlineArray2D[i][j]);  
    }  
}
```

The above loop prints 0, 1, 2, 3, 4, 5, 6, 7 … But why? A computer executing the above code first encounters the outer loop (the one with i as a counting variable). The first iteration of that loop is then executed, and in our case that one iteration is simply equal to this:

```java
for(int j = 0; j < inlineArray2D[i].length; j++){  
    System.out.println(inlineArray2D[i][j]);  
}
```

We didn’t re-invent the wheel. The outer loop still only executes 5 times (the length of the the array) as we would expect. The inner loop executes 5 times _**per iteration**_ of the outer loop, meaning it executes for a total of 25 times.

It may be useful to examine this chart showing the values of i and j during each iteration of the _**inner**_ loop:

| Iteration | I | J | inlineArray2D\[i\]\[j\] |
|--|--|--|--|
|1 | 0 | 0 | 0 |
|2 | 0 | 1 | 1 |
|3 | 0 | 2 | 2 |
|4 | 0 | 3 | 3 |
|5 | 0 | 4 | 4 |
|6 | 1 | 0 | 5 |
|7 | 1 | 1 | 6 |
| 8 | 1 | 2 | 7 |
| 9 | 1 | 3 | 8 |
| 10 | 1 | 4 | 9 |
| 11 | 2 | 0 | 10 |
| ... | ... | ... | ... |

When we have **nested** loops, the counting variable of the innermost loop increases most quickly, and the outermost loop increases least quickly.

Here’s the same code from above, but converted into two nested while loops:

```java
int i = 0;
int j = 0;

while(i < inlineArray2D.length; i++){  
    while(j < inlineArray2D[i].length; j++){  
        System.out.println(inlineArray2D[i][j]);  
    }  
}
```

Alternatively, we can use our more compact syntax:

```java
for(int[] i: inlineArray2D){  
    for(int j: i){  
        System.out.println(i[j]);  
    }  
}
```

This can be one of the more difficult things in programming to fully understand the first time you see it. Carefully look over the examples and try it on your own.

**Note**: 3 nested loops are perfectly valid as well:


```java
for(int i = 0; i < array3D.length; i++){  
    for(j = 0; j < array3D[i].length; j++){  
        for(k = 0; k < array3D[i][j].length; k++){  
            System.out.println(array3D[i][j][k]);  
        }  
     }  
}
```

## Chapter VII: Control Statements & Enumerated Types

### Conditional Statements 

Sometimes in our code, we want to be able to make decisions based on certain information. For example, this method would return true if the provided number is prime, and false if the provided number is not prime:

```java
boolean isPrime(int num){ //Algorithm assumes num is >= 2  
    for(int i = 2; i < num; i++){  
        if( num % i == 0){  
            return false;  
        }  
    }  
    return true;  
}
```

The above code is an implementation of an algorithm known as trial division. It uses the modulus operator to find the remainder of the input number divided by all numbers smaller than it, but still greater than 1. If a remainder of 0 is found at any point during this process, the number cannot be prime, because a remainder of 0 indicates the input was evenly divided by another number.

**Example**: input = 7. 7 % 2 does not equal 0, 7 % 3 does not equal 0, 7 % 4 does not equal 0, 7 % 6 does not equal 0. Therefore, 7 is prime.

Let’s analyze it step-by-step. Firstly, using our for loop, we iterate from number 2 all the way up to num – 1. This is because we used i < num for our loop rather than i <= num like we did earlier when we converted sigma notation into a for loop. This is extremely important for this algorithm, because if our counting variable was able to reach the same value of num, our algorithm would break and tell us that every number was not prime since x % x always equals 0.

During each iteration, we check whether or not the remainder of num divided by i is 0. **If it is**, we know the number in question can’t be prime since something other than 1 or itself evenly divided into it, so we end the method by returning false.

If we manage to go through every iteration without finding a number than evenly divides the input number, then we know we have a prime number and finally return true after the for loop ends. The syntax for if is, yet again, relatively simple and fairly intuitive. We say:

```java
if(condition) {  
    //Code here...  
}
```

But what if we wanted two options? What if we wanted to do **x** if the condition is true, but **y** if it isn’t? The solution is simple:

```java
if(condition) {  
    //Do something  
} else {  
    //Do something else  
}
```

We can even chain these statements together:

```java
if(condition) {  
    //Code here  
} else if (condition2) {  
    //Code here  
} else if(condition3) {  
    //Code here  
} else {  
    //Code here  
}
```

If condition1 is true, then the code inside of the first if statement will execute and nothing else. If it’s false, we then evaluate condition2. If condition2 is true, we execute the second block and nothing else. If condition2 is false, we then evaluate conditon3, and so on, and so on.

**Note**: Some programming languages combine “else if” into a single word, such as Python’s “elif” key word.

We can even put them inside of each other:

```java
if(condition){  
    //Code here  
    if(condition){  
        //Code here  
    } else if(condition){  
        //Code here  
    }  
}
```

Yes, that was quote a few abstract examples right out of the gate. Let’s look at some concrete examples:

```java
if(5 > 4){  
    System.out.println(“I would sure hope five is greater than four”);  
}
```

```java
boolean someBool = false;  
    if(someBool){  
        System.out.println(“If this code executes, logic has been violated!”);  
    } else {  
        System.out.println(“Logic has been preserved!”);  
    }
```

There are many more examples I could show, but they would get rather redundant quite quickly. I encourage you to try the various combinations of if and else statements on your own.

### Break, Continue, Return

Was the algorithm shown in the previous section an excuse to talk about prime numbers? Yes, because I really like prime numbers. More importantly, It was a way to demonstrate a how to manipulate loops. We were able to interrupt our for loop using the following:

```java
if( num % i == 0){  
    **return false;**  
}
```

There are other ways we can manipulate loops without completely stopping a method. For example, suppose we wanted to print only odd numbers from 1 to 100, we could do this:

```java
for(int i = 1; i <= 100; i++){
    //Braces can be omitted if the if statement’s
    // content is only a single expression/line   
    if(i % 2 == 0) continue; 
    System.out.println(i);  
}
```

The **continue** key word will stop the current iteration of a loop and _continue_ to the next one. So, in the above example, we would have 1, 3, 5, 7, 9, 11 … printed to our screen. We could even combine this with our algorithm from earlier and print only prime numbers from 3 to 100:

```java
for(int i = 3; i <= 100; i++){  
    if(isPrime(i) == false) continue;  
    System.out.println(i);  
}
```

In this case, we would get 3, 5, 7, 11, etc. Go ahead and try the isPrime method and the above loop for yourself. Couldn’t we have simply placed the print statement inside of an if statement? Yes, but this is a simple example. In more complex loops with more code, the continue key word has more utility.

The break keyword has different uses depending on context. Inside of loops, break terminates the loop completely. break can also be used inside of switch statements and labels which we will cover shortly. Here’s an example of break  inside a for loop:

```java
for(int i = 0; i < 20; i++){
    System.out.println(i);
    if(i >= 5) break;
}
```

We would see 0, 1, 2, 3, and 4 printed to the screen. The loop would then stop executing. Breaking out of a loop prematurely can be a good way to save computing resources by letting the computer avoid unnecessary work if the situation permits doing so.


### Labels

Java has a rather archaic feature built into that is seldom used but extremely valuable in the right context. Suppose we have a nested for loop:

```java
for(int i = 0; i < 10; i++){
    for(int j = 0; j < 10; j++){
        if(i == j * 2 – 3) {
            break;
        }
    }  
}
```

Using break would only break out of the inner loop. What if we want to break out of both the inner and outer loops? This is where labels come in:

```java
someLabel: {
    for(int i = 0; i < 10; i++){
        for(int j = 0; j < 10; j++){
            if(i == j * 2 – 3) {
                break someLabel;
            }
        }  
    }
}
```

While we don’t have to use labels with for loops – anything can go inside a label – they’re a good way to demonstrate their usefulness. We can optionally specify a label’s name when we use the break key word. When we do this, all code inside of the label will stop executing rather than just the nearest loop.

In many cases, feeling the need to use labels is a symptom of poorly written code. When it’s appropriate to use them is a bit of a judgment call. They aren’t common, but they do exist.

### Switch Statements

In addition to for loops, while loops, do-while loops, and if-else statements, there exists yet another way to control the flow of a program: the **switch statement**. Switch statements are completely unnecessary, but they’re certainly nice to have. Everything they’re capable of can be accomplished using various combinations of if, else, and else-if statements. But enough jabbering, here’s what they look like:

```java
int num = 5;

switch(num) {  
    case 1:  
        System.out.println(“Uno”);  
        break;  
    case 2:  
        System.out.println(“Dos”);  
        break;  
    case 3:  
        System.out.println(“Tres”);  
        break;  
    case 4:  
        System.out.println(“Cuatro”);  
        break;  
    case 5:  
        System.out.println(“Cinco”);  
        break;  
}
```

The above example is logically equivalent to the following:

```java
int num = 5;

if(num == 1){  
    System.out.println(“Uno”);  
} else if(num == 2){  
    System.out.println(“Dos”);  
} else if(num == 3){  
    System.out.println(“Tres”);  
} else if(num == 4){  
    System.out.println(“Cuatro”);  
} else if(num == 5){  
    System.out.println(“Cinco”);  
}
```

Ok, that’s great and all, but why use them? Well… They look nice? Like I said before, they’re really truly not necessary. They’re just another way to accomplish the same thing albeit in a slightly more compact and a e s t h e t i c a l l y pleasing way.

Much like how break will end a loop, break will also completely end a switch statement. But what if we omitted break and didn’t include it in our switch statement at all? What would happen?  
  
Here’s a simpler switch statement to demonstrate:

```java
int num = 5;  
switch(num) {  
    case 5:  
        System.out.println("5");  
    case 6:  
        System.out.println(6);
}
```

What do you think will be printed to the screen? If you guessed “only the number 5” like a rational human being would assume, you’d be wrong, because that’s now how switch statements work. ¯\_(ツ)_/¯

Instead, we get both the number 5 and 6 printed to the screen. But why? The reason is that as soon as one of the cases we list matches the value we’re using the switch statement on (num in this case), _**all subsequent cases will execute as well**_, which is why you should probably be using the break key word in _most_ cases.

One final thing to note about switch statements is their odd lack of {} braces. Unlike basically everything else in Java, they rely on using colons to designate different sections of code. These sections, unlike in the above examples, _**can**_ contain multiple statements, but I only used single print statements for simplicity. Nothing stops us from doing something like this:

```java
case 5:  
    System.out.println(“5”);  
    System.out.println(“is a nice, prime number”);  
break;
```

In short, switch statements are a nice, optional addition to the language. Just don’t forget to use break if you choose to use them! And yes, you can use switch statements on things other than integers, just not strings (you could previously do this, but switch statements on strings are no longer possible in modern Java) or objects.


### Enumerated Types

To the best of my knowledge, enumerated types aren’t even covered in programming I at UF, but they’re extremely simple and go hand-in-hand with switch statements. Knowing them will serve you well later, even if that’s long after this class. Feel free to skip this section if you’re just trying to get your degree and move on with your life.

From Oracle’s Java documentation:

> An enum type is a special data type that enables for a variable to be a set of predefined constants. The variable must be equal to one of the values that have been predefined for it. Common examples include compass directions (values of NORTH, SOUTH, EAST, and WEST) and the days of the week.

Enumerated types cannot have their values reassigned after they are created. They can have constructors, properties, and methods though they very often don’t. Enums can be put inside of their own .java files or put inside of a class as a property of the class. Here’s how to make some:

```java
enum Weekday {  
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY;  
}
```

For most cases, the above example is sufficient. We can then create a variable of type Weekday by doing the following:

```java
Weekday day = Weekday.MONDAY;
```

However, as previously stated, enumerated types can have properties and methods as well:

```java
enum OldBook {

    PARADISE_LOST_("Paradise Lost", "John Milton", 1667),
    PILGRIMS_PROGRESS_("Pilgrim's Progress", "John Bunyan", 1678),
    ROBINSON_CRUSOE_("Robinson Crusoe", "Daniel Defoe", 1719);

    private String name;
    private String author;
    private int year;
    
    OldBook(String name, String author, int year){
        this.name = name;
        this.author = author;
        this.year = year;
    }

    public int getYear() {
        return year;
    }

  

    public String getAuthor() {
        return author;
    }

  

    public String getName() {
        return name;
    }

}
```

Enumerated types are one of the few occasions in Java where the order of code matters. When creating instances of a enum, those instances **must** go at the top of the enum definition. Despite this, the order of the other code following the enum declarations is irrelevant.

As mentioned previously, the switch statement pairs nicely with enums:

```java
OldBook book = randomBook();

switch(book){
    case PARADISE_LOST:
        System.out.println(“p old tbh”);
        break;
    case PILGRIMS_PROGRESS:
        System.out.println(“Kinda old”);
        break;
    case ROBINSON_CRUSOE:
        System.out.println(“11/10 would recommend”);
        break;
}
```

## Chapter VIII: The Foundations of OOP

Up this point, all of the topics covered have been more or less universal across modern programming languages. The things covered in this chapter are specific to object-oriented programming and are among the most difficult subjects in OOP.

The four defining characteristics of object-oriented programming are **abstraction**, **inheritance**, **polymorphism**, and **encapsulation**. Without a mastery of these topics, using an object-oriented language is a waste of time.

### Abstraction 

Abstraction is undoubtedly one of the most important ideas not only in object-oriented programming, but perhaps in all of computer science. In my assessment, computer science is the science of abstraction. But what is abstraction? Allow me to illustrate with some examples.

When you’re late for a hair appointment, does your barber really care _why_ you were late? When you start your car in the morning to get to work or to class, do you care about _how_ your car manages to start when you turn the key? When you’re sick and fall behind on class work, do you really care about the intricacies of how the flu replicates within the human body and how viral load influences the accuracy of flu screening? No!

In all of the above examples, we are not concerned with unnecessary details. They don’t help us in any way and only add needless complexity to our understanding of the situation. This idea – the ignoring or hiding of unneeded details – is one component of **abstraction**.

To translate this idea to programming, imagine you’re writing a math-heavy program and someone sends you the code for a class that contains some math methods. It can calculate trigonometric functions, compound interest, statistical data, and some common geometric calculations. Should you be concerned with _**how**_ this class works when you need to use it for your own program? Assuming it works as intended, no. From your perspective, this would be unnecessary information. Why bog yourself down learning how they wrote the class when you can accept that it works as intended and not waste time having to dissect their creation?

Abstraction can take many forms, however, and it is not limited to receiving other people’s code. In many cases, we may wish to abstract our own code. Suppose we have a method that is 100, 200 lines long. A method of that size would likely be difficult to understand and even more difficult to modify without introducing unintended behavior. To fix this, we would ideally break the method up into smaller methods and then string them together.

Here’s an example of what an overly large method that has been properly broken down by abstraction might look like:

```java
void bakeBread(){
    preheatOven();
    activateYeast();
    Bowl mixingBowl = new Bowl();
    addDryIngredients(mixingBowl);
    addLiquidIngredients(mixingBowl);
    Dough breadDough = knead(mixingBowl);
    bake(breadDough);
}
```

Even though I didn’t include any of the other methods or classes, it is still clear what is going on due to abstraction. We needn’t concern ourselves with the intricacies of the other parts of our code. The above method _**could**_ have been written by cramming 100 – 200 lines of code into a single method, but doing so would have overcomplicated matters.

The presented implementation of the bakeBread method is highly abstract: it has very little information as to _how_ the bread is actually baked. Instead we have a very high-level explanation of what it means to bake bread rather than the nitty gritty details. We still have to write the same amount of code, but it is broken up and organized in a way that is less mentally taxing.

A more succinct definition for abstraction comes from [a user on StackOverflow](https://stackoverflow.com/questions/21220155/what-does-abstraction-mean-in-programming): “_Abstracting something means to give names to things, so that the name captures the core of what a function or a whole program does._”

Proper abstraction makes programs easier to understand, develop, debug, and reason about.

### Inheritance: The Basics

The second cornerstone of object-oriented programming is inheritance, and it’s extremely powerful. In short, inheritance allows for the creation of hierarchical relationships between different classes. That might sound a bit odd, so here’s an example:

```java
class Animal {

    boolean isAlive;
    
    void die(){
        isAlive = false;
        System.out.println(“The animal has died. :(”);
        System.out.println(“Plz press F to pay respects.”);
    }
    
}
```

We start with the above **base class** that will sit at the top of our class hierarchy. However, for there to be a hierarchy, we will need other classes to sit beneath it. Let’s make two classes at the bottom of our pyramid. In the following situation, the Animal class is the **superclass** of the Cat and Dog classes. Cat and Dog are both **subclasses** of the Animal class.

```java
class Cat extends Animal {

    String furColor;

    Cat(String furColor){
        this.furColor = furColor;
    }

    void meow(){
        System.out.println(“The cat with ” + furColor + “ fur says hello.”);
    }
}
```

And another class for dogs:

```java
class Dog extends Animal {

    double barkFrequency;

    Dog(double barkFrequency){
        this.barkFrequency = barkFrequency;
    }

    void bark(){
        System.out.println(“The dog barks at a frequency of ” + barkFrequency + “ hertz”);
    }

}
```

We now have a very simple hierarchy of classes with the Animal class sitting at the top and the Cat and Dog classes sitting at the bottom. But what does the creation of this class hierarchy accomplish? The answer is code reuse, one of the goals of object oriented programming. To demonstrate, note that the following code is perfectly valid:

```java
//I have no clue what frequency dogs bark at
Dog dog = new Dog(100D); 
dog.bark();
dog.die();
```

Despite the fact that the Dog class does not contain a method called die, we are still able to call the die method on a dog object. This is because when we write class Dog extends Animal, the Dog class _**inherits**_ everything from the Animal class which does have the die method. As said before, computer scientists aren’t known for their creative use of language.

This inheriting code from the Animal class is not limited to methods. Inside of the Dog class, we can even reference the properties of the Animal class. For example, suppose we changed the bark method slightly inside the Dog class:

```java
void bark() {
    System.out.println(“The dog barks at a frequency of ” + barkFrequency + “ hertz”);
    System.out.println(“The dog is alive: ” + isAlive);
}
```

Despite the Dog class not having a field called isAlive, we are able to reference it anyway since it was inherited from the Animal class. The reverse isn’t true, however. Inside the Animal class, we wouldn’t be able to reference the bark method or the barkFrequency field. The relationship is one-way much like the one between me and my ex girlfriend was.

Inheritance hierarchies can have multiple layers to them. Suppose we wanted to add a third layer by doing this:

```java
class Mammal extends Animal {
    void giveBirth(){
        if(isAlive){
            System.out.println(“The mammal has given birth.”);
        } else {
            System.out.println(“The mammal is unable to give birth as it is dead. :(”);
        }
    }
}
```
```java
class Cat extends Animal {
    //Pretend the old code from before is here
}

class Dog extends Mammal {
    //Pretend the old code from before is here
}
```

Now we can do this:

```java
Dog dog = new Dog();
dog.bark();
dog.giveBirth();
dog.die();
```

There is no (realistic) limit for how long the inheritance chain can be. And as seen above, the inheritance hierarchy is not necessarily always a pyramid; the Cat class still extends Animal, not Mammal.

When the class hierarchy reaches multiple layers in size such as in the above demonstration, it is important to note the following: Mammal is a super class of Dog, but Animal is no longer a super class of dog. _A class can only have a single super class_.

The relationships between the Animal and Mammal classes and between the Mammal and Cat/Dog classes is often described as an **is-a relationship** by textbooks and professors. This is because a mammal _**is**_ an animal, and both cats and dogs are kinds of mammals. The significance of this will be made clear in the next section on inheritance and when we cover polymorphism.

### Inheritance: Constructors

Suppose we have an Animal class like from before:

```java
class Animal {

    String name;

    Animal(String name){
        this.name = name;
    }
    
}
```

And we also make a Dog class that does nothing other than extend Animal for the sake of demonstration:

```java
class Dog extends Animal {

}
```

Because the Animal class has only a single constructor and that constructor demands that we provide a name to create an animal, all animals must have a name. All dogs are animals (**is-a relationship** as previously described), so by extension all dogs **must** be provided a name when they are created. But this causes a problem: the default empty constructor for our Dog class has 0 parameters, so we are unable to provide a name when we create a instance of Dog.

Because of this logical problem, the empty Dog class above will not compile. Upon first hearing this problem, you may be tempted to think the following version of the Dog class rectifies the situation:

```java
class Dog extends Animal {

    Dog(String name){
        this.name = name;
    }

}
```

Unfortunately, this doesn’t work either. When we create class hierarchies using inheritance, we must ensure that all classes in the inheritance chain have their own constructors’ demands satisfied. The Animal class’s constructor is never called, so we have an error. How do we fix this?

```java
class Dog extends Animal {

    Dog(String name){
        super(name);
    }
    
}
```

The **super** key word allows us to reference the superclass of the object we are currently writing code inside of. Depending on context, super acts like both a method and an object. When used inside a constructor as a method, it must be the first thing we type. No other code can come before it, though other code can come after it.

In the above example, we satisfy the demands of the Animal class’s constructor by directly calling it using super. Of course, the Dog class doesn’t necessarily need to have any parameters in its constructor so long as the appropriate values are provided to its super class. If we wanted every instance of Dog to be named Fido, the following would work as well:

```java
class Dog extends Animal {

    Dog(){
        super(“Fido”);
    }

}
```

In larger inheritance chains, we can pass arguments up multiple layers and in some situations we must do so:

```java
class A {

    int someNumber;
    
    A(int someNumber){
        this.someNumber = someNumber;
    }
    
}

class B extends A {
    B(int someNumber){
        super(someNumber);
    }
}

class C extends B {
    C(){
        super(1337);
    }
}

class D extends C {

}
```

The base class A requires an integer to be created. B also requires an integer, and it passes it up the chain to A’s constructor. C doesn’t require an integer and it always passes a value of 1337 up to B which is then passed to A. D’s default constructor takes no arguments nor does it need to since C’s constructor doesn’t take any arguments either.

### Inheritance: Method Overriding 

Inheriting all of the methods from a super class is certainly useful, but it has its shortcomings. What if we want to be able to override some of the behavior we inherit from a super class while leaving the rest of the inherited behavior unchanged? Fortunately, we can through **method overriding**. This is not to be confused with the previously described _method overloading_.

  
  

Suppose we have the following two classes:

```java
class Animal {

    String name;

    Animal(String name){
        this.name = name;
    }

    void attack(Animal anotherAnimal) {
        System.out.println(this.name + “ attacks ” + anotherAnimal.name);
    }

    void forageFood(){
        System.out.println(this.name + “ manages to find some food.”);
    }

    void sleep(){
        System.out.println(this.name + “ takes a nap.”);
    }

}
```

```java
class Dog extends Animal {

    Dog(String name){

        super(name);

    }

}
```

As of right now, an instance of the Dog class is identical to an instance of Animal for all practical purposes. If we ran the following code, we would see the “Fido takes a nap” followed by “Fido manages to find some food.”

```java
Dog dog = new Dog(“Fido”);
dog.sleep();
dog.forageFood();
```

However, what if we did this?

```java

class Dog extends Animal {

    Dog(String name){
        super(name);
    }

@Override
void forageFood(){

        System.out.println(“Using his unbridled canine aggression, ” + this.name + “ shakes down an innocent bystander at Whole Foods for some avocado toast. ”);

    }

}
```

Now when we make an instance of Dog like before, we should see that one of the messages has changed while the other remained the same:

```java
Dog dog = new Dog(“Fido”);
dog.sleep(); //Same message from before
dog.forageFood(); //Prints message about Fido’s immoral foraging tactics
```

Every other method and field in the Dog class remains unchanged compared to the Animal base class. The only difference is that the forageFood method has been forcibly modified.

The @Override **annotation** isn’t strictly necessary, but it does two things. Firstly, it denotes to the reader that a method has been overwritten which helps with clarity. Secondly, it will result in a compile-time error if we override a method not present higher up the inheritance chain. Why would we want to intentionally cause an error? In a case where we remove a method from a super class, it’s quite likely that we will also forget to remove it from classes where we overwrote it. By intentionally causing an error in that case, we can avoid a great deal of headache and confusion by having this mistake immediately pointed out to us by the compiler.

For the most part ™, this is as complicated as method overwriting gets. By simply redefining a method already defined higher up the inheritance hierarchy, the behavior can be changed without abandoning other inherited features.

### Polymorphism: Type Casting

In chapter 2, we explored the different data types. While there are 3 broad categories – integers, floating point numbers, and booleans – both integers and floating points have sub-types.

From a logical point of view, it isn’t unreasonable to assume that we can convert a byte to a short, an integer to a long, or even from a double to a byte. After all, these are all kinds of numbers. As luck would have it, Java allows us to perform these conversions using something called **type casting**:

```java
int someNumber = 1337;
short someOtherNumber = (short) 1337;
```

In my head, I always read line two as the following: “a short called someOtherNumber _**is equal to the short version of**_ someNumber”.

What would happen if we attempted to convert 1337 into a byte? A byte can only hold 256 possible values, so such a conversion would rely on the mechanics of integer overflow/underflow as briefly described in chapter 2. When we convert 1337 into a byte, it yields a value of 57.

We can also convert floating points to integers and integers to floating points. Converting a double with a value of 13.37 into an integer value results in 13. When converting from a floating point number into an integer, the numbers after the decimal place are removed (truncation) and then a standard integer to integer conversion is performed.

While the type casting of primitives isn’t polymorphism in the object-oriented sense, the underlying idea and syntax will translate into the next section. We see here that a single value can be expressed in a variety of forms.


### Polymorphism

Polymorphism is related to inheritance and is perhaps best understood by analyzing its semantic meaning: “many forms”.

In one of our earlier examples on inheritance, we constructed a inheritance chain involving four classes: Animal, Mammal, Cat, and Dog. All mammals are animals, and all cats and dogs are both animals and mammals **at the same time**. In other words, _both the_ _C__at and_ _D__og classes can take one of three forms depending on context_.

To illustrate this point, suppose we had three methods with the following signatures:


```java
void animalMethod(Animal a){

}

void mammalMethod(Mammal m){

}

void dogMethod(Dog d){

}
```
If we created a Dog object, we could call all three methods using said object. This shouldn’t come as too much of a surprise. Suppose, however, that we wanted animalMethod to behave differently depending on what kind of animal we passed into it. We can do that with the instanceof keyword:

```java
void animalMethod(Animal someAnimal){
    if(someAnimal instanceof Dog){
        System.out.println(“The animal is indeed a doggo.”);
    } else {
        System.out.println(“The animal is not a floof. :(”);
    }
}
```

the ```instanceof``` keyword is used to create a boolean expression and takes the form “variableName instanceof ClassName”. If the variable is an instance of the provided class, the expression evaluates to true. Otherwise, it evaluates to false.

Suppose the Dog class had a method called bark() that the Animal class did not. If we wanted to execute that method if the provided variable was an instance of the Dog class, we would first need to convert the provided animal object into a Dog object to execute it. Let us amend the above example to achieve this:

```java
void animalMethod(Animal someAnimal){

    if(someAnimal instanceof Dog){
    
        Dog dog = (Dog) someAnimal;
        dog.bark();
        
    } else {
    
        System.out.println(“The animal is not a floof. :(”);
        
    }
    
}
```

The snippet in blue is an example of **down casting**. We type casted (converted) an object from its form higher up the inheritance chain into a form farther down the inheritance chain; type casting is not limited to just primitives. This then allowed us to execute the bark() method on the casted version of the object since it did not have the bark() method in its Animal form.

**Up casting** occurs when we go from low to high on the inheritance hierarchy, ie from Dog to Animal. Up casting can always be performed, but down casting can result in errors in situations where doing so does not logically make sense such as the following scenario:

```java
Animal animal = new Animal();

Dog dog = (Dog) animal;
//Down casting error.
//The object in question is **only** an animal, not a dog.
// Conversion in this case does not logically make sense.
```

The language I’ve used here is very deliberate. I said we were able to call bark on the dog _**version**_ of the object. In the above method, someAnimal and dog both refer _to the same object. It simply exists in different forms in different parts of the method._ If we were to use the equality operator == on both dog and someAnimal, it would evaluate to true. This is because both dog and someAnimal occupy the same memory address – they are the same object.

```java
void polymorphism(Animal animal){

    if(animal instanceof Dog){
        Dog dog = (Dog) animal;
        System.out.println(dog == someAnimal); //prints “true”
    }

}
```

This is polymorphism. The same object can gain or lose functionality depending on what form it takes. We should note one final thing when it comes to method overwriting and how it interacts with polymorphism. Suppose we have the following two classes:

```java
class Animal {

    void eat(){
        System.out.println(“The animal eats”);
    }

}
```

```java
class Dog extends Animal {

    @Override
    void eat(){
        System.out.println(“The dog eats”);
    }
    
}
```

And we then do the following:

```java
//Think about why we can do this.
// The syntax used to create objects should now make sense and seem less arbitrary.
Animal animal = new Dog();  
animal.eat();
Dog dog = (Dog) animal;
dog.eat();
```

Instead of seeing “The animal eats” followed by “The dog eats”, we simply see “The dog eats” two times. This is because the object was created using the constructor of the Dog class and it is therefore ultimately a dog rather than an animal. _Much in the same way that human beings often change their outward appearance while their true nature remains the same, an object’s presentation can change but its nature (behavior) cannot._

### Encapsulation: How and Why?

Of the four pillars of OOP, encapsulation is by far the easiest to understand. The reasoning behind using it isn’t immediately as clear, however.

Up to this point, when we wanted to create a class and modify the values contained within instances of that class, we did something like this:

```java
Student student = new Student();
student.name = “Greg”;
student.gpa = 3.75D;
```

Though this approach works, there are a few possible problems with it. Suppose when we initially made the Student class, we decided to store a student’s GPA as a property of the class. Later on, we decide we want to store a student’s grades in an array and then use the array to automatically calculate the student’s GPA. If we make this transition, _anywhere that our code references student.gpa will be broken code and must be manually updated_.

The better, future-proof approach for making the student class would have been this:

```java
class Student {

    double gpa;

    double getGpa(){
        return this.gpa;
    }

}
```

Now, instead of using student.gpa, we would use student.getGpa(). In the short term, this accomplishes absolutely nothing. In the long-term, it prevents us from having to update other code should we choose to change how the GPA value is calculated like in the following modified version of the class:

```java
class Student {

    double[] grades;

    Student(double[] grades){
        this.grades = grades;
    }

    double getGpa(){
        int totalScore = 0;
        for(double d: grades){
            totalScore += d;
        }
        return totalScore / grades.length;
    }

}
```

After we change the Student class to calculate the GPA differently than it did before, any code that referenced the getGpa() method will remain perfectly valid. A similar approach is used for assigning values as well:

```java
class Student {

    String email;

    void setEmail(String email){
        this. email = email;
    }

    String getName(){
        return this.email;
    }

}
```

Why would we want to jump through more hoops just to assign a value? In the case of reading a value from a class, the use case is more obvious. The way in which that value is calculated is subject to change, but what benefit could possibly be derived from this additional step for assigning values?

What if we wanted to verify that the email address being passed into the setEmail method is actually a valid email address? Rather than check the validity of an email each and every time before we assign it to a student object, we could simply edit the setEmail method to perform a check. The code used to check the email is definitely not perfect, but it’s a quick and dirty implementation for the sake of demonstration:

```java
setEmail(String email){

    if(email.contains(“@”) == false || email.contains(“.”) == false){
        System.out.println(“Error! Email not valid!”);
    } else {
        this.email = email;
    }

}
```

With this approach, updating how we determine the validity of an email address is quite easy. We only have to update a single method rather than updating our validity checks all across our code base.

These “getter” and “setter” methods are known as **accessors** because they allow us to access the fields of a class (I have said it before and I’ll say it again: the average computer scientist is a far cry from a poet).

Even in situations where you’re certain there is no need for accessors, they are common practice in Java and should almost always be used for the sake of convention and consistency. In many cases they serve no purpose whatsoever and are just an annoyance, but they are still considered good practice. There may be an occasional exception to this (such as the java.awt.Point class), but those cases are the exception and not the rule. For the remainder of this book, accessors will always be used.

Now, you may wonder “even though we made accessor methods for the email address, what’s to stop someone from still doing student.email = “asdf” ?” As of right now, there is nothing to prevent this. We don’t want this to be the case since it could lead to unintended behavior and defeat the point of having accessors, so we’ll cover how to rectify this problem in the next subsection.

The goal of encapsulation is to hide the details of _how_ code works from someone using it. I would argue that it is a form of abstraction. When we call a getter method and receive a value, we are not concerned with _how_ that value was returned, only that it was. When we call a setter method to set a value, we again don’t care what goes on behind the scenes so long as the value is set accordingly.

### Encapsulation: Visibility Modifiers

In a previous chapter, we saw the enigmatic “public” modifier in the public static void main(String[] args) method used to start all Java programs. public is one of the 3 **visibility modifiers** in Java. The other two are protected and private.

These modifiers allow us to control from where in a program certain fields and methods can be accessed from. Like always, the best way to demonstrate this is with an example:

```java
class Movie(){

    private String name;

    Movie(String name){
        this.name = name;
    }

    boolean isGood(){
        return this.name.equalsIgnoreCase(“The Big Lebowski”);
    }

    String getName(){
        return this.name;
    }

}
```

Now if we make a movie and attempt to access its name without using getName(), we will get an error (example assumes this code is executing outside of the Movie class):

```java
Movie movie = new Movie(“Terminator”);
System.out.println(movie.name); //Error
```

The reason for this is that we marked the name property of the Movie class as being private. As a consequence, the only place we can access it from is inside of the Movie class _**and not even in any of its subclasses**_ (if it had any). Anywhere else and we’ll get an error.

Visibility modifiers can also be used on methods, constructors, and even classes:

```java
public class Movie(){

    private String name;

    public Movie(String name){
        this.name = name;
    }

    public boolean isGood(){
        return this.name.equalsIgnoreCase(“The Big Lebowski”);
    }

    public String getName(){
        return this.name;
    }

}
```

Unsurprisingly, the public modifier means that the method or field in question can be accessed from anywhere in our program. The protected modifier is somewhat in between public and private. If a field or method is marked as protected, it is visible from within the class, within any subclass, and within the same package.

Oracle’s Java documentation summarizes the four levels of visibility in the following table ([source](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html)):

| Modified | Class | Package | Subclass | World (everywhere) |
|--|--|--|--|--|
| public | **Yes** | **Yes** | **Yes** | **Yes** |
| protected | **Yes** | **Yes** | **Yes** | *No* |
| no modifier | **Yes** | **Yes** | *No* | *No* |
| private | **Yes** | *No* | *No* | *No* |

What’s a package? It’s a collection of classes that are typically related in some way. If you do not explicitly create a package, all your class files will be in the same package by default. Packages are covered in more detail in a later chapter. When I took Programming I, the protected modifier was almost an afterthought and was used very sparingly.

Constructors and accessors are generally marked as public, and non-static fields are almost always marked as private. There are some exceptions to this such as the [singleton design pattern](https://en.wikipedia.org/wiki/Singleton_pattern), but design patterns fall outside the scope of this book.

## **Chapter IX: Interfaces & Abstract Classes**

### Interfaces

Java’s model of inheritance is somewhat limited compared to other object-oriented languages like C++. A class can only have one super class and no more. **Multiple inheritance** is simply not possible.

So how, then, do we create a class which inherits code from multiple sources? The solution lies with interfaces:

```java
public interface Employee {
    public double getSalary();
}
```

```java
public interface Student {
    public String getMajor();
}
```
```java
public class Example implements Employee, Student {

    private double salary;
    private String major;

    public Example(double salary, String major){
        this.salary = salary;
        this.major = major;
    }

    @Override
    public double getSalary(){
        return salary;
    }

    @Override
    public String getMajor(){
        return major;
    }

}
```

An **interface** is an agreement or contract. It specifies what behavior (methods) must occur, but not _how_ it should occur. An interface cannot have fields, only methods. Interfaces also do not have to have method definitions, only method signatures. When a class **implements** an interface, that class must have all of the same methods that the interface does. When a class has all of the required methods, the contract has been satisfied. If the contract is violated (required methods are missing), the Java compiler will not be very happy.

Now you may be thinking that this isn’t quite inheritance, and you’d be right. After all, if multiple classes have to implement the same interface, each class would have to have its own implementation of the required methods, ultimately defeating the point of inheritance! Fortunately, Java version 8 introduced the ability for interfaces to have default implementations of methods:

```java
public interface Dog {

    public default void bark(){
        System.out.println(“Woof!”);
    }
    
}
```

Default methods have their own shortcomings, however. When writing a default implementation of a method inside of an interface, we cannot use the this key word. The reason why is straightforward. Any number of different classes could implement the interface, so this could refer to an object created from any number of different classes and what this refers to would be incoherent.

When a class implements an interface, objects created using that class are instances of the interface as well as instances of the class. So for example, if we have class Maltese implements Animal, Dog, then the following values would both be true:

```java
Maltese maltese = new Maltese();
System.out.println(maltese instanceof Dog);
System.out.println(maltese instanceof Animal);
```

Continuing on the topic of interfaces and polymorphism, interfaces can extend other interfaces:

```java
public interface Animal {
    public void sleep();
}
```

```java
public interface Mammal extends Animal {
    public void giveBirth();
}
```

A class implementing Mammal would be both an instance of Mammal and an instance of Animal at the same time, just like we would expect in the case of classes.

When one interface extends another, default methods can be overwritten just as with classes:

```java
public interface A {

    public default void someMethod() {
        System.out.println(“Hello, world!”);
    }
    
}
```

```java
public interface B extends A {

    @Override
    public default void someMethod() {
        System.out.println(“Goodbye.”);
    }

}
```

As a final note, here’s the syntax for when you want to extend a class and inherit an interface:

```java
public class SomeClass extends SomeOtherClass implements A, B, C
```

### Abstract Classes

Abstract classes fall somewhere between interfaces and regular classes. Here are their properties:

*   The constructors of abstract classes cannot be used to create instances of objects. The constructors of their subclasses must be used instead.
*   Method definitions inside of an abstract class are optional and the default key word can be used just like with interfaces
*   Unlike with interfaces, abstract classes are actually classes. As a consequence, it is possible to use the this key word in contrast to interfaces.

Marking an abstract class is quite simple:

```java
public abstract class Person {

}
```

As previously mentioned, the following code would result in an error since abstract classes cannot be **instantiated**:

```java
Person person = new Person(); //Error: Cannot instantiate abstract classes.
```
What, then, is the point of making a class that we can’t use directly? Remember, abstract classes are classes with some of the properties of interfaces. We get the benefit of being able to use the this key word as well as effectively having an interface. Here’s an example:

```java
public abstract class Person {

    private String name;
    private int age;
    private int strength;

    public Person(String name, int age, int strength){
        this.name = name;
        this.age = age;
        this.strength = strength;
    }

    public default String getName(){
        return this.name;
    }

    public default int getAge(){
        return this.age;
    }

    public default int getStrength(){
        return this.strength;
    }

    public int getAttractiveness();

    public boolean wantsToSeeManager();

    public default boolean fight(Person otherPerson){
        boolean won = this.strength > otherPerson.getStrength();

        if(won){
        
            System.out.println(this.name + “ mops the floor with ” + otherPerson.getName());
            
        } else {
        
            System.out.println(this.name + “ got destroyed by ” + otherPerson.getName());
            
        }
        return won;
    }

}
```

```java
public class Chad extends Person {

    public Chad(int age, int strength) {
        super(“Chad”, age, strength);
    }

    @Override
    public int getAttractiveness(){
        return 10;
    }

    @Override
    public boolean wantsToSeeManager(){
        return false;
    }

}
```

```java
public class Karen extends Person {

    public Karen(int age, int strength){
        super(“Karen”, age, strength);
    }

    @Override
    public int getAttractiveness(){
        return 0;
    }

    @Override
    public boolean wantsToSeeManager(){
        return true;
    }

}
```

```java
Chad chad = new Chad(21, 10);
Karen karen = new Karen(55, 2);
chad.fight(karen);

>> Chad mops the floor with Karen!
```

We are able to make instances of Chad and Karen because they have their own constructors and neither of them are abstract. Even though they share the common superclass Person, we can still create instances because neither are abstract themselves.

## Chapter X: Packages

Packages are simply folders on your computer that contain .java files or other folders. The contents of a package are typically related in some way. To take a real-world example, one of the packages for Minecraft’s multiplayer server is net.minecraft.server. Folders are separated with periods. So, if we had a folder called parent that contained a folder called child, the resulting package would be parent.child.

Packages help immensely with code organization. As Java programs get more complex and have more and more files, some level of additional organization beyond classes becomes a necessity. The java language itself comes with a number of useful packages, such as java.awt (Abstract Window Toolkit; used for making programs with GUIs) and java.util, a collection of utility classes.

To access code in a different package, an **import statement** must be used _at the top of the file_ before the class, enum, or interface definition. Here is an example:

```java
import java.awt.Robot;

public class PackageExample {

    public static void main(String[] args){
        Robot robot = new Robot();
    }

}
```

Because we imported the Robot class, we now have access to it. Alternatively, we could have used import java.awt.* to import everything inside of the java.awt package, but this is considered bad practice and it wastes resources by importing unneeded files. While importing classes can be tedious and it can be difficult to remember the names of everything, both the Eclipse and IntelliJ IDEs allow for automatic package importing. On Eclipse, pressing CTRL + SHIFT + O will import all required packages that haven’t been imported yet. I’ve never used IntelliJ so I can’t help you with that one.

Creating our own package is simple. If we were to do it manually (not recommended), we would make the needed files. I typically use the package cameron.white, so I would make a folder called “cameron” and then make a folder inside of cameron called “white”. We would then make our new java file inside of the white folder. IDEs automate this process and you should be using them when possible.

To create a new package inside of Eclipse, navigate through the following menus:

![](https://i.imgur.com/YeUlQ9l.png)

![](https://i.imgur.com/pK3FUc5.png)

After creating our package, we can then create a .java file like the following:

```java
package cameron.white;

public class PackageTest {

    public PackageTest(){
        System.out.println(“Congratulations, you made a useless object!”);
    }

}
```

At the top of our file is the **package declaration** which tells Java what package this file belongs to. You would think the Java compiler would be intelligent enough to figure this out automatically given the location of a file, but that is unfortunately not the case.

While packages exist almost entirely for the purpose of organization, they can also allow for classes with the same name to coexist. As far as Java is concerned, a class named Person inside of package some.package is entirely different from a class named Person inside of some.other.package.

In the unfortunate event that we need to use two classes with the exact same name inside of the same .java file, we can do so by prefixing the class name with the name of its package. Going back to the Person example in the last paragraph, we could distinguish the two like this:

```java
void someMethod(some.package.Person){
    //Code here
}

void someMethod(some.other.package.Person){
    //Code here
}
```

This is possible because the two Person classes are entirely different data types, and the above two methods don’t conflict with one another because of this.

## Chapter XI: Data Structures

In a previous chapter, we explored how arrays can be used to store any arbitrary data type that we choose. Arrays are not the only **data structure** offered by Java however. A data structure is some kind of object that stores information, provides ways for that information to be manipulated, and typically offers some level of abstraction to the data being manipulated. Data structures make certain kinds of data easier to understand and manipulate.

### Lists

Lists are the easiest data structure not yet covered and are very similar to arrays. Let’s make a list of integers:

```java
import java.util.List;
import java.util.ArrayList;

public class Whiteboard {

    public static void main(String[] args){
        List<Integer> = new ArrayList<Integer>();
    }

}
```

The List class from the java.util package is abstract, and so it cannot be instaniated. We instead create an instance of ArrayList, a subclass of List. There are other kinds of lists such as CopyOnWriteArrayList (yes, the name really is that long), but we won’t get into them here.

Also notice that rather than make a list of ints, we made a list of Integers. The reason for this is Java’s implementation of **generic data types**  (not covered in this book) does not support primitives, only objects. For most situations this is merely a technicality and has little bearing on actual code. If a method requires an int, an Integer can be provided instead. For all intents and purposes, instances of primitive objects are entirely interchangeable with primitives, just not for data structures.

Another oddity is that when we create instances of primitive objects like Boolean, Integer, Short, Long, etc, we don’t need to use the new key word. The following is perfectly valid:

```java
Integer a = 5;
System.out.println(a * 5);
Boolean someBool = false;
```

With Java’s design failures out of the way, why use a list over an array? An array has a fixed size while a list does not. By default, a list has 0 elements and it will continue to gain elements as we call the add method on the list. For example:

```java
List<String> list = new ArrayList<String>();
list.add(“Hello, ”);
list.add(“world!”);
```

The contents of the list can then be accessed using the get method and the size of the list is given by the size() method:

```java
for(int i = 0; i < list.size(); i++){
    System.out.println(list.get(i));
}
```
Though the above approach works, the List class implements a special interface called Iterable from the java.lang package. Any class implementing this interface can be used with a for loop:

```java
List<String> list = new ArrayList<String>();

//pretend I added some values here

for(int i: list){
    //Note, I put int even though it’s an array of Integers.
    //They’re very interchangeable.
    System.out.println(i);
}
```

Elements of the list can be removed one of two ways. If we know the index of the elemtn, we can simply call list.remove(index). If and only if we are not storing some kind of integer data type in the list, we can instead specify the object we wish to remove without even knowing where it falls in the list:

```java
List<Dog> dogList = new ArrayList<Dog>();

Dog dog1 = new Dog(“Fido”);
Dog dog2 = new Dog(“Casper”);
Dog dog3 = new Dog(“Floofer”);

list.add(dog1);
list.add(dog2);
list.add(dog3);

list.remove(dog2);
```

### Maps

The concept is a map is integral to programming. A **map** is a collection of unique **keys** that each point towards a single value. For example, we could have a map representing an address book in which we have a collection of unique phone numbers each pointing towards the name of the individual with that number.

| Key | Value |
|--|--|
| 867-5309 | Jenny |
| 911 | The Alphabet Boys |
| 555-5555 | My crush |

After creating a map, we can provide one of its keys to retrieve the value associated with that particular key. Here is an example:

```java
Map<String, String> addressBook = new HashMap<String, String>();
addressBook.put(“8675-309”, “Jenny”);
addressBook.put(“911”, “The alphabet boys”);
addressBook.put(“555-5555”, “My crush”);
System.out.println(addressBook.get(“8675-309”));

>> Jenny
```

Much like with lists, we cannot create an instance of Map so we instead create an instance of HashMap. The first data type inside of the <> brackets is the data type of the key, and the second is the data type of the value.

Key-value pairs can be removed from a map by calling the remove method:

```java
addressBook.remove(“8675-309”);
```

If you’d like to get a list of all of the keys in the map, you can do so by calling the keySet() on the map. Note, the keySet() method doesn’t return a List object, it returns a Set object, a data type similar to List but not quite the same. The Set class implements Iterable, meaning you can use a for loop on.

Why use a map? Without delving too deep into computational complexity theory, certain implementations of maps are extremely fast. When using a **hash map**, we can instantly* retrieve a value from a map. It’s not quite instant, but for the sake of analogy it’s close enough. Even if speed wasn’t a benefit, certain kinds of programming problems lend themselves to being solved with maps.

If we wanted to make an address book without a map, we would need to construct two arrays or lists of identical size and make sure that we always inserted and removed the key-value pairs appropriately. This quickly becomes tedious and is highly prone to error.


### Other Data Structures

There are far more kinds of data structures than just lists and maps. There are trees, heaps, stacks, queues, linked lists, and more. These data structures are not typically something you need to use when you are new to programming. **Data Structures and Algorithms** (or something with a similar name) is a class offered by all colleges and universities with a computer science program. The course is dedicated to the exploration of various data structures, their applications, strengths, benefits, tradeoffs, etc. While they are important, there isn’t enough room in this text to cover them in detail.

## Chapter XII: Exceptions

In programming, an **exception** (error) occurs when a program enters an irreparably broken state. When an exception occurs, a program can crash which makes them quite the hassle to deal with. In Java, exceptions are actually objects and all exceptions are a sub-class of the java.lang.Exception class.

One of the most common exceptions in Java is the dreaded NullPointerException. When an object is not assigned a value, it defaults to a special value called **null**. If a method is called on null or a property of null is referenced, Java will **throw** (create) an instance of NullPointerException.

```java
Dog dog = null;
dog.bark(); //NullPointerException
System.out.println(“This code will never run because the program will crash”);
```

TODO: Finish chapter

## Chapter XIII: Tips & Tricks

This chapter is dedicated exclusively to useful techniques that didn’t fit neatly into other parts of the book. They appear in no particular order and aren’t necessarily related to one another.

### Anonymous Objects

It is possible to create an **anonymous object****s**, aptly named because they are never assigned a variable name:

```java
void someMethod(Dog dog) {
    //Code here…
}
```

```java
someMethod(new Dog(){

    {
        //Inside these braces is the constructor of the anonymous object.
        this.name = “Fido”;
    }

    @Override
    public void bark(){
        System.out.println(“Woof woof!”);
    }

});
```

We can create anonymous instances of interfaces as well. For example, let’s use an interface provided to us by Java called Runnable. It’s an interface with only a single void method called “run” and nothing more:

```java
Runnable runnable = new Runnable(){

    @Override
    public void run(){
        System.out.println(“Hello, world!”);
    }

};
```

### The Common Ancestor

By default, all objects extend a class called Object from the java.lang package. The Object class sits at the top of all inheritance hierarchies. It comes with a few useful methods such as equals and toString. To make use of these methods, we must override them:

```java
public class Dog {

    private String name;

    @Override
    public String toString(){
        return this.name;
    }

}
```

### Final

One of the few modifiers not mentioned earlier on is the final modifier. It can be used on fields of a class as well as methods, though how it affects the two differs.

```java
Class SomeProgram {
    public static final String VERSION = “0.0.1”;
}
```

When a variable is marked as final, it must be assigned a value at its declaration and cannot have another value assigned to it after that. If a method is designated as final, that method cannot be overwritten by any subclasses.

### String Conversion

In Java, it is not possible to type cast strings into primitive data types like in other languages. For example, a string with the value “5” can’t be converted to the integer value 5 using the standard type casting syntax. Instead, We must rely on the various primitive classes such as Integer, Long, Boolean, etc.


```java
String str = “5”;
int someInt = Integer.parseInt(str);
```

Each of the primitive classes has a parse\_\_\_\_\_ method. Boolean.parseBoolean, Long.parseLong, Double.parseDouble, etc.
