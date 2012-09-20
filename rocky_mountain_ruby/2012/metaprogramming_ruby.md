# Metaprogramming Ruby

## Matt Yoho

  - [Jumpstart Lab](http://jumpstartlab.com/)
  - [https://speakerdeck.com/u/mattyoho/p/metaprogramming-ruby](https://speakerdeck.com/u/mattyoho/p/metaprogramming-ruby)


## Ruby Object Model

    obj = Object.new


  Who am I? self

  Where am I? That's the question.


## Explicit vs Implicit Receiver

    # explicit
    def bar
      return self.foo
    end

    # implicit
    def bar
      return foo
    end


## define_method

  Creating a setter method requires string interpolation

    define_method("#{attr}=") do |value|
    end


## Resources

  [Code samples from the talk](https://gist.github.com/6747c89369da0f11dc7b)
  [Great article on method scope](http://weblog.jamisbuck.org/2007/2/23/method-visibility-in-ruby)
