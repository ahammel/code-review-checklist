# Code Review Checklist

> <i>Given enough eyeballs, all bugs are shallow.</i>
>
> <cite>Linus' Law</cite>

This document aims to be a community-maintained and flexible guide to code
review. The goal is to provide a consistent set of code review practices while
allowing individual groups the freedom to take whichever approach they feel is
best suited to the task.

Groups—or even individual developers—who use this guide may find it useful
to fork this repository and make modifications and specific recommendations to
suit their needs and preferences.

The guide is in two parts: a **Code Review Best Pracice** section, which
contains guidelines for being an effective reviewer, and a **Checklist**,
which is a guide to the questions the reviewer should be asking about the
code.

The checklist is split into five sections, corresponding to what we believe to
be the most important aspects of a piece of software to be covered by a code
review. Developers should consider these aspects when conducting a code
review, and should document their findings about these aspects of the software
while reviewing.

We feel that a the best way to ensure that the guide is relevant an useful is
if it is continually maintained by the developers who *perform the reviews*.

Remember, the purposes of a code review are:

1. To improve the quality of the software
2. To *document* that we have improved the quality of the software
3. To improve the knowledge and skill of *the reviewer*, as well as the
   author.

The checklist was originally developped for use in the Assembly Pipeline
Analysis working group at the [Genome Sciences Centre](http://www.bcgsc.ca).

## Table of Contents

* Code Review Best Practice

* Checklist
    * Correctness
    * Testing
    * Documentation
    * Error Handling and Logging
    * Design


## Code Review Best Practice

> <i>Criticism may not be agreeable, but it is necessary. It fulfils the same
> function as pain in the human body. It calls attention to an unhealthy state
> of things.</i>
>
> <cite>Winston Churchill</cite>

As with the rest of this guide, best pracitce recommendations should come from
the experinece of code reviewers. For some general guidelines to start with,
see the SmartBear whitepaper [11 Best Practices for Peer Code Review][Whitepaper]
(PDF).


## Checklist

It is a major goal of this document that all but the most general and
best accepted guidelines should be derived from the *experience* of the code
reviewers *who use these guidelines*. This will ensure that the checklist
stays flexible, relevant and up to date.

Items on the checklist should be phrased in terms of questions that the
reviewer should ask him or herself about the code under review.


### Correctness

> <i>Correctness is clearly the prime quality. If a system does not do what it is
> supposed to do, then everything else about it matters little.</i>
>
> <cite>Bertrand Meyer</cite>

#### Does the program do what it's supposed to do?

* Is the output correct?
* Are there circumstances under which the program will give the wrong output?
* What assumptions does the program make about input?


### Testing

> <i>[T]esting is not a phase to be performed after development is complete. It
> needs to be done all the time throughout the delivery process by everybody[.]</i>
>
> <cite>Jez Humble</cite>


#### Has the program been tested?

* Are there unit tests available?
* Do the unit tests cover all the important functionality of the program?
* If we have to change some part of the program, how will we know that the
  rest of it still works correctly?


### Documentation

> <i>Incorrect documentation is often worse than no documentation.</i>
>
> <cite>Bertrand Meyer</cite>

#### Will developers be able to understand how to modify the program?

* How is the functionality of the program documented?
* Is the documentation accurate?
* Is the documentation easy to understand?
* Is all of the documentation contained in the source code?

#### Will users be able to understand how to run the program?

* Is there a usage message? Is it accurate? Is it helpful?
* Is the rest of the user-side documentation accurate?
* Is there enough user-side documentation?


### Error Handling and Logging

> <i>When you must fail, fail noisily and as soon as possible.</i>
>
> <cite>Eric S. Raymond</cite>

#### What happens when something goes wrong?

* Under what circumstances will the program fail to run?
* Are the error message informative?
* In cases of user-error, does the user get adequate information about what he
  or she did wrong?
* Does the program produce a reasonable amount of logging for its function?


### Design

> <i>[D]o not let performance considerations stop you from doing what is right.
> You can always make the code faster with a little cleverness. You can
> rarely recover so easily from a bad design.</i>
>
> <cite>Elliotte Rusty Harold</cite>

#### Is the program flexible?

* Will developers be able to modify the program to fit changing requirements?
* Are there hard-coded data that should be modifiable?
* Is the program sufficiently modular? Will modifications to one part of the
  program require modifications to others?

#### Could the program be simpler?

* Do you, the reviewer, understand what the code does?
* Does the program reinvent the wheel?
   * Can parts of the functionality be replaced with the standard library?
   * Is there redundant functionality in two different programs?
* Is all of the functionality necessary? Could parts be removed without
  changing the performance?
* Is the code commented?
   * Are the comments necessary?
   * Could the code be rewritten so that the comments aren't necessary?

#### Is the code readable?

* Is the code formatted according to the conventions of the language?
* Are the formatting conventions consistent?
* Are the variable names reasonable?


[QMS_info]: http://gin.bcgsc.ca/plone/groups/quality/bioinformatics-quality-assurance/documents
[Whitepaper]: http://gin.bcgsc.ca/jira/secure/attachment/32569/WP-CC-11-Best-Practices-of-Peer-Code-Review.pdf
