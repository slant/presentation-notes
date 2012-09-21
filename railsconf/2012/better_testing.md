# Testing Best Practices, or the Five Habits of Highly Effective Tests
by Noel Rappin (@noelrap) of Groupon
Author of Rails Test Prescriptions

In a well-tested code base, the bugs are shallow. Usually a result of a
missed test.

Relatively simple and clean design

Tests are a way to determine if what I, as the developer, thing the code
should be doing is happening.

Tests are NOT a way to make sure that the code is as effective as it
should be. That's what test-driven development does.

## Signs that the tests are not well written

BDD is a software design process. This is only useful if the developers
are able to partake in deciding the design of the project.

Lots of test fragility
A sign that the code is too highly coupled or that you're testing the
wrong thing.

Test-based slowdowns

A remaining lack of confidence in changing the code.


## Why Is Testing Effective?

Why is TDD an effective process?

One opinion:
You're expressing your code's requirements. This causes you to think
through the whole process.

Universal client
Every part of your code needs to be accessible to the tests. (This
forces decoupled code.)


## Rapid Feedback

Pair programming technique:
One person writes a test, the other person writes the dumbest code
possible to make it pass.

If you have to setup a lot of "state" or that you have a lot of
dependancies, the code is too complex and could be refactored and
decoupled. The first sign of this is that the tests get harder and
harder to write.

"More Testable" is a legitimate engineering goal.
This goal naturally leads to less coupled code.


## TDD vs Test-first

TDD
  - Assume that the tests are correct. Change the code to make the test pass.

Test-first
  - Tweak the tests until they pass, matching the code.


## What Makes an Effective Test?

  Tests are code without test! (Awesome!)


## SWIFT

  Simple
    A test is simple if it's purpose is clear
    Bad (too complex): fixtures, long tests, bad-naming, clever
    Good: good naming, factories, refactoring tests
    If the tests can't be simple, THE CODE IS BAD.

  Well-defined
    A test is well-defined if someone can understand what the code does by reading it.
    Bad: dates, random
    Good: encapsulation, mocks

  Independant
    Bad: global data, fixtures
    Good: factories, teardown/transactions (remove persistance between testing)

  Fast
    A test is fast if it is fast.
    Sorting: only use two items, not the entire database.
    Don't touch the database unless you have to.
    Good: encapsulation, unit testing
    Can you go back and forth between your code and tests without having to wait?

  Truthful
    A test is truthful if it accurately reflects the underlying code
    Bad: too specific, mocks, surface values
    Testing for an incidental feature of your code, not critical functionality

Test both sides of a problem
  Both true and false conditions of a method


## The Testing Pyramid and Chains of Responsibility

  Use Rspec, Minitest or Cucumber appropriately.
  One cucumber test   
