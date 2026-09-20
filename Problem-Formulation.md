# Problem Formulation

## Learning outcomes

* Construct a computational problem formulation for an English problem statement
* Analyze problem formulations in terms of their values

## What is problem formulation and why should we care about it?

Remember the overarching division between "solving problems" (computational
thinking) and "coding" (giving instructions to the computer in Python) that we
talked about [before](https://i80486.github.io/inst126-intro-programming-notes/what-is-programming.html)?

A BIG part of computational thinking is **problem formulation**.

To do real-world programming, you need to know more than how to write code. You
need to be able to take a relatively vague problem like "get all the email
addresses out of this file", and **model the problem so that it can be solved**
**by a computer**.

### An example

Let's walk through an example together of what this looks like.

Here's a vague problem statement: I get so many emails. I have a blocklist of
usernames that I don't want to see. Filter all the emails that come in
everyday so I don't see the emails from the blocked usernames.

<!-- ```{note}
As a user, I want to get all email addresses out of a file
``` -->

And here is a draft **decomposition** of the overall problem statement that can
be part of a problem formulation:

```{image} assets/probform-ex-email-filter.png
:class: bg-primary mb-1
:width: 1000px
:align: center
```

Notice how this formulation is much more detailed in that it *decomposes*
(breaks down) a large and vague problem into smaller (sub)operations, data, and
describes the logical relationships between the operations/data.

### More on why problem formulation matters

If you don't learn this skill (and it is a skill!) in this class, you *will*
struggle in future programming courses (e.g., INST326) and any other area where
you're actually needing to *use* programming to solve information science problems.

To give a flavor of this, consider this note I got from an INST326 instructor on
what students were really struggling with in her class:

> "They are struggling with programming in general. Even though this is their second course, they **don't have much ability to think about how to solve problems**. We're in the "I watched everything you did and followed but have absolutely no idea where to start" phase, even with very simple work. **I suspect they are sneaking through 126 without learning what they need and suddenly have to create from scratch with me and are panicked**"

To emphasize: If you can't formulate a problem in computational terms, it
doesn't matter whether you know how to write a legal conditional statement, or
how to assign variables, and so on. You'll know *how* to instruct the computer,
but not what instructions to give it! The *what* comes from problem formulation.
It's absolutely critical!

### When/how to do problem formulation?

You should be able to think through these bits without knowing how to write the
code for it yet!

In fact, it's a **really good idea** to get started on this *before* you write
any code. Your problem formulation doesn't have to be perfect or complete, and
you will refine it as you go, but it will guide what you write, and help you
think through your debugging and help-seeking as well (recall how it's useful
to have a navigator and driver in paired programming: the problem formulation
representation can help be a passive navigator resource)

This is why we have your first deliverable for Project 2 be a problem formulation.

## Diagramming Methods

Before we start, I am proposing two methods for diagramming:

### Simple Diagramming using Post-Its

A simple diagramming convention using red post-its for operations, blue
post-its for data, and orange/yellow for logical relationships. The blue
and red should contrast well for those who are colorblind, and the logic
is a separate shape. If anyone has issues, let me know.

Example:

```{image} assets/probform-ex-email-filter.png
:class: bg-primary mb-1
:width: 700px
:align: center
```

### Data Flow Charts

A more full-featured diagramming convention based off of data flow diagrams,
using shapes and arrows. This is much closer to what you would see in the real
world.

Here are the components of this diagram type and what they mean:

#### Processes

A process is an action that your application takes. It could be adding numbers,
parsing a string, printing something to the console, taking, user input, etc.
Any action that your program takes should be a process.

Note the number at the top of the process. This should generally indicate which
order your program runs them in.

This is generally the same concept as 'operations' in the simple diagramming model.

```{image} assets/process-drawio.png
:class: bg-primary mb-1
:width: 350px
:align: center
```

#### External Entities

An external entity is someone giving data to or consuming data from your
application. Use this for whenever you're putting data in your application but,
more relevant for this class, when you're _printing_ something.

This is not present in the simple diagramming model.

```{image} assets/entity-drawio.png
:class: bg-primary mb-1
:width: 350px
:align: center
```

#### Decision Diamonds

A decision diamond reflects a conditional - a fork in the road in your
program. The primary purpose visually is to help you, the user, understand
what actions the program takes and under which circumstances.

```{image} assets/decision-drawio.png
:class: bg-primary mb-1
:width: 350px
:align: center
```

#### Data Flows

A data flow represents what data is going between two other components. Data
can flow between processes, external entities, or decision diamonds (and)
between types as well.

If you use them with decision diamonds, indicate which decision is being made
as multiple flows will exit the diamond. It's not always necessary to say which
type of data is flowing in those cases (you will see why in practice.)

Be sure to name the one or more data pieces that are flowing between the
other components.

```{image} assets/data-flow-drawio.png
:class: bg-primary mb-1
:width: 350px
:align: center
```

## Two components of a problem formulation: Decomposition and Specification

### Decomposition

One key aspect of a computational problem formulation is a problem decomposition:

1. The key steps/**operations** of your program
2. The **data** that is going in and out of the steps/operations
3. The **logical flow** of how all the pieces fit together

Let's see how these map to our initial example:

```{image} assets/probform-ex-email-filter.png
:class: bg-primary mb-1
:width: 1000px
:align: center
```

Alternately, our Data Flow Chart:

```{image} assets/probform-ex-email-filter-drawio.png
:class: bg-primary mb-1
:width: 1000px
:align: center
```

Side note - see how this process is not perfect! Simple models cannot completely
match the true scenario. See how I added a cylinder for the email filter list -
I was thinking it would be a variable in our code, which doesn't have a representation
in our diagramming method! So I chose something that made sense. Maybe I should
have chosen an External Entity like a user setting up their Gmail filter! But it's
grey area, so make your best judgement and choose what's most helpful for you.

Another thing - there's actually no direct connection for the one email on process
1.0 and the 3.0 process. We know it's getting there somehow, but it probably would
have required adding some intermediary components to truly track it properly. So
I have left it implicit here.

In this example, the key elements were:

* Operations: *extract* email address from email record, *extract* username from
  email, *add* email to filtered emails list if the username isn't in the
  blocked username list
* Data: *raw email list*, *filtered emails*, etc.
* Logic: *loop* over every email, *conditional* for the adding operation,
  sequence between the operations.

Here is another simple example: I'm going to give you a list of numbers, and I
want you to give me back a list that only has odd numbers in it:

1. What are the main substeps/**operations** in this problem?
2. What **data** is going in/out of the operations?
3. What is the **logical flow** of how they fit together?

Here's an example problem decomposition for that:

```{image} assets/prob-form-filter-list.png
:class: bg-primary mb-1
:width: 800px
:align: center
```

Notice how it is possible to formulate it to think about substeps/operations
that we know how to do already (check if number is odd)!
<!-- This is a key heuristic for a good problem formulation. -->

Now let's look at slightly more complex example that we *definitely* don't know
how to code yet. I'm going to give you a bunch of birth certificates
(N=500,000), and I want you to tell me what the top 50 and top 10 baby names
are, because I want to choose names that are recognizable (i.e., in the top 50),
but not too common (top 10):

1. What are the main substeps/**operations** in this problem?
2. What **data** is going in/out of the operations?
3. What is the **logical flow** of how they fit together?

Here's an example problem decomposition for that:

```{image} assets/prob-form-baby-names.png
:class: bg-primary mb-1
:width: 800px
:align: center
```

## Let's practice

I'm going to give you a list of emails and I want you to give me back a list
hat only has emails from `@umd.edu`:

1. What are the main substeps/**operations** in this problem?
2. What **data** is going in/out of the operations?
3. What is the **logical flow** of how they fit together?

### Specification

A problem decomposition tells you *what pieces* your program needs. But to
actually build (or verify) each piece, you need something more precise: a
**specification**. A specification answers: for a given piece of your program,
**what should go in, what should come out, and what should happen in different situations?**

For example, in our email filter problem decomposition, we identified an
operation: "extract username from email." A specification for that operation
would pin down:

* **Input:** an email address string like `"joel@umd.edu"`
* **Output:** just the username part, like `"joel"`
* **Examples of expected behavior:**
  * `"joel@umd.edu"` → `"joel"`
  * `"student123@gmail.com"` → `"student123"`
  * What about `"no-at-sign"`? What should happen?

The inputs and outputs are usually the *data* going in/out of the
operations/substeps from our decomposition. But the specification of expected
behaviors helps us think more carefully about the operation/substep.

Writing out concrete examples forces you to confront **edge cases** --- unusual
or tricky inputs that your English description didn't address --- that your
program should address. This is one of the biggest benefits of moving from a
vague problem statement to a precise specification. As we'll see later,
this also facilitates debugging and testing!

<!-- ### Specifying behavior with examples

One of the most powerful ways to sharpen a problem formulation is to write out **concrete examples** of how your program should behave. For each operation, ask: "If I give it *this*, what should I get back?" -->

<!-- This might sound simple, but it's surprisingly powerful.  -->

Let's look at another example: the "filter odd numbers" problem. The operation
is: given a list of numbers, return only the odd ones.

| Input | Expected Output |
|---|---|
| `[1, 2, 3, 4, 5]` | `[1, 3, 5]` |
| `[2, 4, 6]` | `[]` |
| `[7]` | `[7]` |
| `[]` | `[]` |

Notice how the last two rows cover *edge cases*: a list with just one item, and
an empty list. These are exactly the cases that cause bugs if you don't think
about them upfront!

#### Why bother with examples?

* **They expose ambiguity.** If you can't agree on what the output should be for
  a given input, your problem formulation has a gap.
* **They can become your tests.** Once you write code, you can check it against
  your examples to see if it actually works. (We'll formalize this later as
  "testing." This is a key part of professional software engineering practice,
  sometimes called [test-driven development](https://en.wikipedia.org/wiki/Test-driven_development)).
* **They help you communicate.** If you're asking someone for help - a
classmate, a TA, or even a collaborator - showing them your input/output
examples is one of the clearest ways to explain what you're trying to do.

#### Practice: write specification examples

Go back to the "filter UMD emails" practice problem above. Write at least 4 rows
in an input/output table, including at least one edge case.

## What makes for a good problem formulation?

Problem formulation is more of an art.

Here are some things I look out for:

* Detailed enough that you start to be able to map them to functions or bits of
code that you know how to write. This is called recognizing patterns, and is a
key aspect of [computational thinking](https://librarycarpentry.github.io/lc-computational-thinking/aio.html).
* Allows you to write and test parts of your problem in isolation from others.
  You can work on small pieces of code, verify that they work (with your
  specification), then piece them together into the larger program, instead
  of trying to write and test a giant program all at once.
* You can describe **concrete examples** of what each piece should do: "if I
  give it *this* input, I should get *that* output." If you can't come up with
  examples, the formulation is probably still too vague.
* More helpful Google / Stack Overflow search results

You can also look for these affective/emotional/high-level senses:

* I feel like I can see the logical "structure" of my program.
* The problem feels more manageable: I recognize pieces I know how to tackle,
  and the ones I don't are specific in ways that makes it easier to learn / seek
  help. If you don't feel that way, you can keep refining!

## Beyond the "purely technical" for problem formulation

So far we've focused on making problem formulations more *precise* - clear
enough to specify exactly what the program should do. But precision isn't the
only thing that matters. Good problem formulation should also consider *what*
we choose to build in the first place, and how our choices affect the people who
use what we build.

Understanding this is a crucial part of being a professional information scientist and programmer.

### Values show up in your specifications

One dimension of this is that **your specifications encode *values*, whether you notice them or not.** When you write a spec - defining what counts as valid input, what the expected output should be, what edge cases to handle - you are making choices that reflect deeper assumptions about what matters.

Values are *not the same as "features"* (i.e., parts of a system). Values are higher-level constraints and conceptions of what counts as "Good" - things like efficiency, cost-saving, performance, privacy, security, harm-reduction, equity. They shape your specifications (what counts as "correct" or "valid"), which in turn shape your decomposition (what you build). So values ultimately determine what gets built (or not).

Let's see this in action with an example.

#### Example: data validation for a form

Consider a form for data entry for payment. One of the operations in your
decomposition might be: "validate the name." That sounds straightforward.
But what does "valid" mean? That's a *specification* question.

One way to specify it: a valid name is between 2 and 20 characters, ASCII letters only.

```{image} assets/prob-form-name-entry.png
:class: bg-primary mb-1
:width: 800px
:align: center
```

This is how many real-world systems are actually set up. And it works a lot of
the time! But look at what this specification *assumes*: that names are short,
that they use only English letters, and that they follow a "first name / last
name" structure.

I've experience things like this too! My first name is Douglas, but I go by
Erik. This means, for any system that doesn't have a preferred name, I need
to choose between adding my legal first name and having it call me what I
go by!

The specification itself - `valid name <= 20 ASCII characters` — is where the
value choice happens. It implicitly prioritizes *simplicity* over *inclusion*.

This example illustrates part of why **edge cases in your specifications**
**matter**. Edge cases are often where values show up most clearly, because
they're about *who or what gets included vs. excluded*. A spec that doesn't
consider the edge case of a very long name, or a name in a non-Latin script,
causes trouble for the people who don't meet that specification.
