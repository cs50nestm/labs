# Hello

{% video https://www.youtube.com/watch?v=eunVUd6E-Bs %}

{% next %}

## Getting Started

Before starting on this program, make sure you complete the code-a-long in class to create your first program `hello.c`. Your assignment will be to make this program a bit more interesting now by adding user input and saying hello, followed by whatever name you choose to input. 

No matter how you compile or execute this program right now, it only ever prints `hello, world`.

There will be a few important differences to create this program. You will need to include another header file called cs50.h. In this file, which we’ll also discuss in more detail later in the course (so don’t be alarmed by some unfamiliar syntax), we’ve declared the data type of string and declared a function called get_string.

A string in computer science essentially refers to a collection of characters—​a word, a sentence, or a phrase. Because when you ask the user for their name it probably consists of more than a single letter, which would be just a character (char), you need to use get_string to collect their input and to store it in a variable whose data type is string.

What else will change, though? That last line of code. You'll need to add %s in there, and the variable name. Why is that the case?

Essentially, %s is what’s known as a placeholder for a variable. At the time the program is compiled, we don’t know exactly what will be printed out (unlike the original program which will always print out hello, world\n), but we do expect that the program will print hello, followed by whatever the user typed. %s is how we indicate to printf that a string will be printed there.

What string will we print? Well, that’d be name! After we specify what we want printf to print, leaving as many placeholders as necessary, we specify what variables those placeholders refer to in order from left to right, separated by commas. We only have one placeholder in our modified program, a single %s, and so the variable that we’re telling printf to print in place of that %s is whatever the user typed at the prompt. For example:

```
$ ./hello
What is your name?
Alice
Hello, Alice!
```

{% next %}
## Getting User Input

Modify this program in such a way that it first prompts the user for their name and then prints `hello, so-and-so`, where `so-and-so` is their actual name.

As before, be sure to compile your program with:

```
make hello
```

And be sure to execute your program, testing it a few times with different inputs, with:

```
./hello
```

### Staff's Solution

To try out the staff's implementation of this problem, execute

<pre>
./hello
</pre>

within [this sandbox](http://bit.ly/2Qp0a2g).

### Walkthrough

{% video https://www.youtube.com/watch?v=wSk1KSDUEYA %}

{% spoiler "Hints" %}

#### Don't recall how to prompt the user for their name?

Recall that you can use `get_string` as follows, storing its *return value* in a variable called `name` of type `string`.

```c
string name = get_string("What is your name?\n");
```

#### Don't recall how to format a string?

Don't recall how to join (i.e., concatenate) the user's name with a greeting? Recall that you can use `printf` not only to print but to format a string (hence, the `f` in `printf`), a la the below, wherein `name` is a `string`.

```c
printf("hello, %s\n", name);
```

#### Use of undeclared identifier?

Seeing the below, perhaps atop other errors?

```
error: use of undeclared identifier 'string'; did you mean 'stdin'?
```

Recall that, to use `get_string`, you need to include `cs50.h` (in which `get_string` is *declared*) atop a file, as with:

```c
#include <cs50.h>
```
{% endspoiler %}

### How to Test Your Code

Execute the below to evaluate the correctness of your code using `check50`. But be sure to compile and test it yourself as well!

```
check50 cs50/problems/2020/fall/hello
```

Execute the below to evaluate the style of your code using `style50`.

```
style50 hello.c
```

{% next %}


{% next "Ready to Submit?" %}

## How to Submit

Execute the below, logging in with your GitHub username and password when prompted. For security, you'll see asterisks (`*`) instead of the actual characters in your password.

```
submit50 cs50/problems/2020/fall/hello
```
