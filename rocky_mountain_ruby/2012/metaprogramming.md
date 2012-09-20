# Ruby Metaprogramming

Matt Yoho
Jumpstart Lab
https://speakerdeck.com/u/mattyoho/p/metaprogramming-ruby


## Ruby Object Model

obj = Object.new


Who am I? self
Where am I? ???


## Explicit vs Implicit Receiver

def bar
  return self.foo
end

def bar
  return foo
end


## define_method

Creating a setter method requires string interpolation

    define_method("#{attr}=") do |value|
    end


## Code samples

https://gist.github.com/6747c89369da0f11dc7b
