# Coffeescript for the Rubiest
Mark Bates


Jeremy Ashkenas wrote Backbone.js
He got tired of writing Backbone models in regular Javascript, so he
developed Coffeescript.


Differences between Coffeescript and Javscript:

* No semi-colons (ever!)
* No curly braces
* No function keyword
* Relaxed parenthises
* Signifigant whitespace


## Assigning anonymous functions to variables

    asdf = ->
    asdf = () ->
    asdf = (arg) ->


## Invoking functions

    asdf() or asdf
    asdf(arg)


## Conditionals

    if condition
      doSomething()

    doSomething() unless condition


## Objects/Hashes

    someObject = { conf: "RailsConf", talk: "CoffeeScript" }

    someObject =
      conf: "RailsConf"
      talk: "CoffeeScript"

## Ranges

    a = [1..5] 
    => a = [1, 2, 3, 4, 5]


## String Interpolation

    name = "asdf"
    => var name;


## Heredocs

    html = """
      <div ...>
        ...
      </div>
    """

## Functions

    p = (name)->
      console.log "Hello #{name}"

    p('RailsConf 2012')


## Lambdas in Ruby
    p = ->(name) {
      puts "Hello name#{}"
    }

    p.call("RailsConf 2012")


## Default Arguments



## Splats
    splatter = (first, second, others...) ->
      console.log(first)
      console.log(second)
      console.log(others.join(', '))

## Loops & Comprehensions

    for someName in someArray
      console.log someName

    for key, value in someArray
      console.log value

    numbers = [1..5]
    low_numbers = (number * 2 for number in numbers when number < 3)
    console.log number for number in numbers when number < 3


## Classes

    class Employee

    emp = new Employee()
    emp.firstName = "Mark"

    emp = new Employee(name: "Mark")


    class Employee
      constructor: (@options = {}) ->

      salary: ->
        @options.salary ?= "$250,000"

    emp = new Employee()
    console.log ep.salary()


## Extending Classes

    class Manager extends Employee

      constructor: ->
        super
        @options.salary ?= "$500,00"

    manager = new Manager()
    console.log manage.salary()


## Bound Functions

    class User
      constructor: (@user) ->

### Difference between this
      sayHi: ->
        console.log "Hello #{name}"

### And this - retains scope
      sayHu: =>
        console.log "Hello #{name}"

    bob = new User('Bob')
    mary = new User('Mary')

    log = (callback) ->
      console.log "about to execute callback...."

    callback()
    console.log "... executed callback"


## Existential Operator

Checks to see if foo exists.

    if foo?
      console.log foo

    console?.log "foo"

## OMFG - that really works??

Sorta like a Ruby 'try'. Using this with IE prevents IE from halting
execution when a console.log is left in the code.

    console?.log "foo"

    if currentUser?.firstName?
      console.log currentUser.firstName


