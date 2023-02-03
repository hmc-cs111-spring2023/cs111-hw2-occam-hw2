_Fill in each this file with your responses, placing each response after its
corresponding question._

---

**Question**

Pick three quotes from the readings about language design. Good candidates
are:

- Something you agreed with / resonates with your own experience
- Something you disagree with
- Something that is interesting, a new idea or perspective you'd like to remember
- Something you didn't understand

For each quote, describe what it was about the quote that led you pick it.

**Response**

- One quote I especially liked was "It would not be fair to weigh down all
programmers with the need to have or to learn all the words for all niche uses."
[Steele, 1998]
I liked this because, in my programming, I find I can often get bogged down by
trying to add features or even the ability for a function to be used for more
cases than I currently intend it to be used for.
In terms of PL design, it also makes a lot of sense since the programs should
have the capabilities of the user creating what they want even if it may take
a bit more work on the user side.
Languages seem to often be evaluated based on whether they have enough
capabilities for a desired task, but if they have too many capabilities, it can
also affect performance and decrease clarity/simplicity of the code.

- A quote I thought was particularly insightful was part of the quote from
Christopher Alexander: "When people lose the sense of responsibility for the
environment they live in, and realize that they are merely cogs in someone
else’s machine, how can they feel any sense of identification with the
community, or any sense of purpose there?" [Steele, 1998]
This is important for understanding the need for programming languages to be at
least partially developed by the users (through libraries or base code change
requests), but it also applies more generally.
In fact, any environment whether it's a PL, a UI, a house, a school, etc. can
benefit from understanding this information.
Without response to user feedback, environments can drift further and further
away from users' desires and needs as the environment grows.

- One thing I found confusing at first was when Steele described language design
as "a pattern for growing the pattern for defining the patterns that programmers
can use for their real work and their main goal." [Steele, 1998]
After reading through it more, I realized that it's highlighting these three
levels of patterns that should be considered in language design: the pattern for
growth, the pattern for language structure, and the patterns of the programs
the users create.
I really liked how Steele emphasized the importance of creating patterns rather
than creating specific "things" in the language that may not be as adaptable as
patterns can be since they're more general.

---

**Question**

How would you know a well-designed language? What are the symptoms? How would
you know a poorly designed language? What are the symptoms?

**Response**

A key part of a well-designed language is its adaptability.
First, it should change and grow over time.
Steele highlights this idea saying "a main goal in designing a language should
be to plan for growth." [Steele, 1998]
The idea here is that if a language can't change, it can't adapt to its users
or change with the change in demands of languages, making it poorly designed.
Another part of adaptability is how seamless the user code can be with the
built-in functions and operations.
Steele shows an example of this in comparing APL and Lisp.
APL makes it difficult to define variables "in such a way that
the new words look like primitives" but in Lisp "new words defined by the user
look like primitives and... primitives look like words defined by the user."
[Steele, 1998]
This seamlessness is what makes Lisp more adaptable to what
current users want and need.

---

**Question**

How might the themes of _Growing a Language_ relate to ideas from the Fowler reading?

**Response**

Since _Growing a Language_ explains practices of general language design, many
of the ideas relate to the specific case of DSL design described by Fowler,
and furthermore, DSLs can help achieve what Steele describes as valuable for a
general programming language.
For example, Steele explains that languages should continually grow and have
additions such as libraries that increase the ability of the programmers.
DSLs, as Fowler explains, can add fluency for a specific audience, thus
expanding the capabilities of the host language and increasing its usefulness.

---

**Question**

In what way is an API a language?

**Response**

Although I don't completely understand what defines an API and makes it separate
from a language or from an advanced data structure, the readings did highlight
some ways they relate to languages.
APIs have a specific defined vocabulary similar to programming languages, but
there are also aspects that APIs are missing compared to PLs.
Fowler reiterates this saying "A command-query API defines the vocabulary of the
abstraction whereas an internal DSL adds a grammar." [Fowler, "Using DSLs"]
Similarly, a PL has a specific grammar that APIs lack, and with the added
grammar comes added fluency.
Despite this, when designing an API, the practices are very similar to designing
a PL.
Bloch highlights an imperative practice in API design: "Every facet of an API
should be as small as possible, but no smaller.
You can always add things later, but you can't take them away." [Bloch, 2006]
This is also key in PL design as Steele emphasizes starting small and then
letting the PL grow over time.
An important point of the Bloch quote is that features can't be removed after
they have been added if you want forward compatibility!
This is a key reason both APIs and PLs should be made with just the base
functionality necessary so no extraneous parts haunt their future.
APIs also tend to have a narrower scope than a general PL, so this makes some of
the design practices more critical for API design.

---

**Question**

What does the post on grayscale tell us about the process of API design?

**Response**

I think the key thing this post shows is that there are many different ways
to design things that are "intuitive" and it depends heavily on the audience.
For example, the argument for the `white` function is that 100% (or 255) would
be more in line with the 100% used in `rgb`.
Since `rgb(100%, 100%, 100%)` is white, this makes sense to those familiar with
the `rgb` function.
In contrast, the argument for `black` is that "people are familiar [with]
thinking that way from grayscale printing." [Verou, 2014]
Thus, it really depends on who the language should be more intuitive for.
In addition, the other options provided could be more intuitive for novices
(`gray` creates a grayscale color) or those who work with `rgb`/`rgba` already
with grayscale and would want to just decrease their arguments.
Each has its own drawback too, so the goal seems to be what Bloch stated:
"You can't please everyone so aim to displease everyone equally" [Bloch, 2006]
where "everyone" here refers to all the users.

---

**Question**

The Pavlus article mentions the researchers' comments that people preferred
"natural-language replacements for some of the more abstruse syntax". In other
words, people found it easier to work with code that looks more like a human language (e.g.,
English). Consider the following quote by William R. Cook, one of the creators
of AppleScript:

> The experiment in designing a language that resembled natural languages (English
> and Japanese) was not successful. It was assumed that scripts should be
> presented in “natural language” so that average people could read and write
> them. … In the end the syntactic variations and flexibility did more to confuse
> programmers than to help them out. It is not clear whether it is easier for
> novice users to work with a scripting language that resembles natural language,
> with all its special cases and idiosyncrasies. The main problem is that
> AppleScript only appears to be a natural language: in fact, it is an artificial
> language, like any other programming language. … even small changes to the
> script may introduce subtle syntactic errors that baffle users. It is easy to
> read AppleScript, but quite hard to write it.
> [[Cook 2007, page 1-20]](https://dl.acm.org/citation.cfm?doid=1238844.1238845)

Are these two experiences of natural languages at odds with one another? Would
you choose to include natural language in the design of a DSL? If so, how might
you do so? If not, why not?

**Response**

I would not say they are strictly at odds since when discussing usability of
natural languages for novice users, Cook says "it is not clear whether it is
easier" [Cook, 2007] whereas the study described by Pavlus found "novice
programmers were able to write sample programs more accurately in Quorum versus
Perl." [Pavlus, 2012]
Although this later study seemed to move the unclear to a more clear difference
in usability for novices, it isn't a direct contradiction.
I think the key part of the Cook quote is that it's harder for programmers to
use natural languages because of the idiosyncrasies.
The Palvus article seems to be discussing more about the novice experience with
natural languages and how natural languages can make it easier to get started.
What I would argue is that the benefit of ease for novices using natural
languages is much smaller than the benefit of ease for programmers using more
minimal languages since the idiosyncrasies will hinder both the novices and the
programmers, but it really depends on the audience for the PL.
It is always helpful to try to use somewhat natural language (i.e. not
gibberish), but I don't think I will make that a key goal of my DSL due to its
drawbacks.
Instead, I may consider a more visual way of programming (like Scratch or Max)
that would be intuitive to both programmers and novices.

---
