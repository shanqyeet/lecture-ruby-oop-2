# OOP Part 1 

1. Class Variable 
2. Class Method & Self 
3. Module 
---
# Class Variable 
+++ 
### Definition
a class variable is a variable defined in a class of which a single copy exists, regardless of how many instances of the class exist
+++
### Looks like this
```ruby
class Student 
  @@variable_name = "something"
  
  def initialize
    #some attributes here 
  end 
end 
```
+++ 
### Simple activity, we have...
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

```ruby
class Corrupt
  def test
     self 
  end 
  
  def total_bags
    p "282"
  end 
  
  def caught
    p "A total of " + self.total_bags + " luxury bags was found 
        in Rosmah's house"
  end 
end 
```
+++ 
### Question

```ruby
rosmah = Corrupt.new

p rosmah.test #=> output?
p rosmah.reflect == g #=> output?
rosmah.caught #=> output?
```
+++

### Answer

```ruby
rosmah = Corrupt.new
p rosmah.test #=> <Corrupt: some alphanumerics>
p rosmah.reflect == g #=> true
rosmah.caught #=> "A total of 282 luxury bags was found in Rosmah's house"
```
+++

### Using Self - inside of a class method

```
class Election
@@PH_total_seats_won = 121 

  def self.test
    self 
  end
  
  def self.result 
    p "Pakatan Harapan won #{@@PH_total_seats_won} seats"
  end 

  def self.result_percentage
    p ((@@PH_total_seats_won/220).to_f*100).to_s + "%"
  end 
end 

```
+++

### Question
```ruby 
p Election.test == output?
p Election.result #=> output?
p Election.result_percentage #=> output?
```

### Answer 
```ruby
p Election.test == Election #=> true
p Election.result #=> "Pakatan Harapan won 121 seats"
p Election.result_percentage #=> 55.00%
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
---
# Recap



