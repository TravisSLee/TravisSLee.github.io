---
layout: post
title:      "A Blog about Ruby Variables"
date:       2020-10-11 23:38:53 +0000
permalink:  a_blog_about_ruby_variables
---


Throughtout my time in Flatiron School here's what I have learned about Ruby variables:

To start off, local variables in Ruby are defined as names that begin with a lower case letter or an underscore, and are assigned a value upon initailization, because this will cause a name error if initialized as nil. Local variables are most used in Ruby programs, due to the fact that their values can be easily overwritten. Like for example:
```
a = "hello"

puts a
#the output here would be "hello"

a = "new things"
#here we overwrite the value of a 

puts a
#since we overwritten the value of a, the new output of the variable a is "new things"
```
How we use local variables all depends on the scope is written on. We can use them within procs, loops, methods, class methods, modules, or the entire program.

Next we have global variables, and they are defined as a variable that can be referred anywhere in a program. Global variable begin with a $ at the beginning of the variable and have an assigned value of nil before initialization. Unlike a local variable, initializing a global variable by itself won't throw an error because it is already assigned nil. These variables are very rarely used in programs, due to the fact they make it hard to isolate bugs within a program. The scope of this variable is the entire program. A global variable would like this within a program:

```
$var

$var = 1

$var
#var will be "1" anywhere within the program
```

The next variable I'll discuss is the instance variable. Instance variables are variables that are intialized with an object. They identified by having a "@" in the beginning of the variable. They're used  like  attributes for an instance of a certain class. The scope of the variable is encapsulated within the object it refers to.  It would be written like so:

```
class Smthng

def initialize(smthng)

@smthng = smthng
# @smthng would be the instance variable in this case
end

end
```

Next up is the class variable. A class variable is a variable that can be called within a class. We can use such a variable to set up one reuseable variable within a class, so we would not need to write such a variable over and over again. The class variables have "@@" in the beginning of them. The scope of this variable is only within the class itself. These variables will be written as so:

```
class Bob


@@all = []
#here we set up a class variable as an empty array

def initialize(name)
@name = name
@@all << self
end
#here we are saving all the instances of Bob within a class variable of @@all

end
```

Finally, we have the constant variable. Constant variables are variables that have values that shouldn't be change. If said value is changed, the program will throw a warning when you want to change. We use constants to save certain values we want to reuse. Constants are identified by being captialized at the beginning of the variable. The scope of the variable is depending where it was initialized. Meaning if it was initialized within a class, you could use the constant within and outside such class. If the constant is instialized without a value, an error will be thrown.

```
Toy
#This will throw an error due to not having an assigned value

Toy = 1
#When assigned a value the constant will return its value
```

