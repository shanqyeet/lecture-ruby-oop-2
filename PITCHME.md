# OOP Part 1 

1. Class Variable 
2. Class Method & Self 
3. Module 
---
# Class Variable 

+++ 
## Looks like this
```ruby
class Student 
  @@variable_name = "something"
  
  def initialize
    #some attributes here 
  end 
end 
```
+++ 
## Simple activity, we have...
```ruby
class Vehicle
  @@total = 0
  @@total += 1 
  
  def initialize(model, color)
    @count = 0 
    @count += 1
    @model, @color = model, color 
  end 
end 
```

---

# Class Method & Self 

+++
# "Self" in Ruby

You may have heard people say that everything in Ruby is an object. **If that's true it means that every piece of code you write "belongs" to some object.**

+++

### What????

Basically, "self" gives you access to the current object

+++

### Using Self -  Inside an instance method

```
class Random
  def reflect
    self
  end 
end 

g = Random.new

p g.reflect #=> <Random: some alphanumerics>

p g  #=> <Random: same alphanumerics>

p g.reflect == g #=> true

```

+++

### Using Self - inside of a class method

```
class Random
  def self.reflect
    self 
  end
end 

p Random.reflect == Random #=> true

```
---

# Module 

+++
##### As you start to write bigger and bigger Ruby programs, you'll naturally find yourself producing chunks of reusable code—libraries of related routines that are generally applicable
+++
##### In Ruby, modules are somewhat similar to classes: they are things that hold methods, just like classes do
+++
##### With modules you can share methods between classes
+++
### Example 
```ruby
module Cream
  def cream?
    true
  end
end

class Cookie
  include Cream
end

cookie = Cookie.new
p cookie.cream?
```



