# To Mock or Not to Mock

## Justin Searls

  - [@searls](http://twitter.com/searls)
  - [Github](https://github.com/searls)
  - [http://about.me/searls](http://about.me/searls)


## Different kinds of tests


  - Intetration test
  - Unit test
  - Isolation tset


## Types of replacement objects


### Test Double

  The precise term for a fake object that takes the place of a real object.


### Stub

  Prevonfigured to respond to messages.


### Mock

  pre-configured to expect messages

    # mocha code
    database = mock(Database)
    database.expects(:save!).with_dog
    database.save!(dog)
    database.verify


### Spy

  Silently records your interactions


## Mocking Boundaries

  Value

  - each object is exercised by many tests
  - practical tests without deep knowledge of test views

  Cost

  - one change many test fixes


## Case-by-case

  Value

  - Developer freedom to choose best tool & approach
  - You'll fit right in on most Rails teams

  Cost

  - Test doubles are often abused
  - Mix-n-match fake & real -> murkier value
  - "Wanna mock that?" timesink


## The GOOS Way

  GOOS: Growing Object-Oriented Software

  - isolution tests to drive design
  - end-to-end tests to prove it works


## No silver bullet

  1. employ test doubles in our Rails integration tests
  2. write PORO

## Resources

  - [a post on Ruby test double tools](http://is.gd/rubymocks)
  - [test double lib](http://is.gd/gimmeruby)
