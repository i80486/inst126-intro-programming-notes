# 1: What is programming? What is computational thinking?

## What is programming?

Programming is the art of making computers do what we want with programs.

A computer program is **a repeatable set of instructions that a computer can use
to solve a class of problems**

Computers lack a few important things - a comprehensive understanding of the
world, advanced reasoning capabilities, and the inherent meaning behind
language. This means we can't instruct them to do things as simply as
instructing another person: we have to really "dumb it down" with a specialized
and precise language - a programming language.

Critical mental model: programming skill is composed broadly of two things:

1. COMPUTATIONAL THINKING: how to model problems so they can be solved by computers
2. CODING: how to translate these models into valid instructions that a computer
   can follow

CODING tends to get all the attention. This is the syntax, the unfamiliarity of
code language, should you learn Python or Javascript or C++ or Rust... And this
is important!

But COMPUTATIONAL THINKING is the foundation, without which you cannot be a
programmer. Professional programmers use computational thinking to break down
problems so that they can be solved - all before a single line of code is written!

## What is computational thinking?

Let's have a look at what the International Society for Technology in Education
(ISTE) and the Computer Science Teachers Association (CSTA) [have to say about this](https://cdn.iste.org/www-root/Computational_Thinking_Operational_Definition_ISTE.pdf)

> Computational thinking (CT) is a problem-solving process that includes (but is
> not limited to) the following characteristics:
>
> * Formulating problems in a way that enables us to use a computer and other tools to
    help solve them.
> * Logically organizing and analyzing data
> * Representing data through abstractions such as models and simulations
> * Automating solutions through algorithmic thinking (a series of ordered steps)
> * Identifying, analyzing, and implementing possible solutions with the goal of
    achieving the most efficient and effective combination of steps and resources
> * Generalizing and transferring this problem solving process to a wide variety
>   of problems
>
> These skills are supported and enhanced by a number of dispositions or
> attitudes that are essential dimensions of CT. These dispositions or
> attitudes include:
>
> * Confidence in dealing with complexity
> * Persistence in working with difficult problems
> * Tolerance for ambiguity
> * The ability to deal with open ended problems
> * The ability to communicate and work with others to achieve a common goal
>   or solution

## Errors

A good example of computational thinking is Python error types. Each one is
a 'conceptual model' of something that can go wrong in your program.

I also have a [boring video explanation of errors here](https://www.youtube.com/watch?v=X7JGyBK7iAY).

### Syntax Errors

These occur when the computer can't even execute the code because it is not
'grammatically correct'. These bugs require CODING fixes - writing the code with
correct, well-formed syntax for whatever programming language you are coding in.
You can think of this as mapping to things like typos/misspellings and
grammatical errors in writing.

#### Why does Syntax Matter?

While humans can generally figure out from context what you're trying to say,
computers don't have the *advanced reasoning* capabilities to do so. Computers
(as an oversimplification) consist of billions of tiny 'switches'. Switch
settings are either on or off - there's no guesswork about whether you *meant*
to leave a switch on or off (say, it's halfway). In the same way, your code
has to match what the computer expects exactly, otherwise it will not be able
to process it correctly. Your code, in essence, is translated into a bunch of
'switches'.

"What about autocorrect or AI", you might ask? "It understands what I'm trying to
say?" While it may SEEM like the computer is reasoning, in reality it's running
complex mathematical models that produce the most likely correlated value. The code
that *runs* those math calculations still has to be exact, even if the values it's
processing aren't.

### Runtime Errors

A runtime error is when an illegal operation happens while your code is running.
An illegal operation occurs when you try to ask the computer to do something that
doesn't make logical sense - dividing by zero, adding a number and a character,
reading a user's name when the user can't be found in the database... there's
many examples.

Runtime errors will cause an Error to occur in your Python program. An Error is a
message from the program saying what went wrong. You can interact with these errors
in your code - say, anticipating a user might not be found, and then printing
"User Not Found" if an error occurs.

### Logic Errors

A logic error happens when you ask the code to do something that isn't illegal,
but isn't what you want. For example, you may have some user data that stores both
their age (32) and height (170). If you were to try to calculate their most likely
pants size but accidentally used 'age' instead of 'height', you would probably
get some very strange results.