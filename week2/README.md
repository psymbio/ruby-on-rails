# Week 2
## Dated: 2020/10/22

### Introduction to Ruby

Learn about the syntax of ruby and copy examples from github to understand it. Modify, execute and experiment with the examples.

### Github Repository for Module 2

for issues check out: https://github.com/jhu-ep-coursera/fullstack-course1-module2/wiki

### Ruby Basics

Ruby is dynamic, object-oriented, elegant, expressive and declarative. Even integers are objects in ruby. 

Print Hello World in Java 3 times

```java
public class hello {
	public static void main(String args[]) {
		for(int i = 0; i < 3; i++) {
			System.out.println("Hello World!");
	}
}
```

You brain is keeping track of too many things at once.

```ruby
3.times { puts "Hello World!" }
```

This is because 3 is also a full-fleged object in ruby.

2 space indentation. # for comments (should be used less as the code is expressive). Everything in ruby gets evaluated. 

```ruby
3
```

That is a valid program in ruby.

puts is for printing strings also outputs new line.

```ruby
p "Got it" # prints internal represenation of object.
```

Sometimes p is better than puts.

To execute in ruby just in the terminal go ```ruby test.rb```.

Naming conventions:

1. Variables: all lower-case or snake_case if multiple words.
2. Constants: ALL_CAPS or FirstCap.
3. Classes: camelCase.

Semicolons:

1. Leave semicolns at the end of the line.
2. You can do ```a = 2; b = 3``` but it is highly discouraged.

IRB is interactive ruby. To run it just type ```irb``` in the command line.

### Flow of Control

Terms like: if/elsif/else/case/until/unless/while/for/true/false/===

```ruby
a = 5
if a == 3
	puts "a is 3"
elsif a == 5
	puts "a is 5"
else
	puts "a is not 3 or 5"
end
```

```ruby
a = 5
unless a == 6
	puts "a is not 6"
end
```

```unless``` is like ```if a != 6```.

```ruby
a = 10
while a > 9
	puts a
	a -= 1
end
```

```ruby
until a >= 10
	puts a
	a += 1
```

Do it ```until``` this condition is satisfied.

```ruby
a = 5
b = 4
puts "one line" if a == 5 and b == 4
```

```ruby
times_2 = 2
times_2 *= 2 while times_2 < 100
puts times_2
```

Only ```false``` and ```nil``` are false. Everything else is true.

```ruby
puts "0 is true" if 0
puts "false is true"
puts "is false false" if false
puts "even empty strings are true" if ""
puts "nil is true??" if "nil"
puts "nil is actually false" if nil
```

Triple Equal: ```===``` is an equal in its own way. It's not about being exactly equal. Also, use double equal most of the time.

```ruby
if /sera/ === "coursera"
	puts "Triple Equal"
end
if "coursera" === "coursera"
	puts "also works"
end
if Integer === 21
	puts "21 is an integer"
end
```

Case Expressions have two flavors:

1. ```if``` statements
2. Specify a target next to ```case``` and each ```when``` clause is compared to target.
3. ```===``` is called the case equality operator becuase it is used precisely in this case.
4. No fall-through logic in ruby, so there are no C-style default statements.

```ruby
case
	when age >= 21
		puts "You can buy a drink."
	when 1 == 0
		puts "Written by a drunk programmer."
	else
		puts "Default condition."
end
```

```ruby
name = "Fisher"
case name
	when /fish/i then puts "Something is fishy here."
	when 'Smith' then puts "Oh, hi Smith"
end
```

For loops are hardly used in ruby instead ```each/time``` is preferred.

```ruby
for i in 0..2 # range of the data is 0 1 2
	puts i
end
```

### Functions

Functions are defined outside a class and methods inside. But in Ruby every function/method has at least one class it belongs to but it is not always written inside a class. So, technically every function is actually a method. 

Parentheses

Parentheses are optional both when defining and calling a method they are just used for clarity.

```def simple
	puts "no parentheses"
end

def simple1()
	puts "parentheses"
end

simple1()
simple
simple1
```
Return

There's no need to declare type of parameters Can return whatever you want return keyword is optional (last executed line returned).

```ruby
def add(one, two)
	one + two
end 

def divide(one, two)
	return "I don;t thinl so" if two == 0
	one / two
end

puts add(2, 2)
puts divide(2, 0)
puts divide(12, 4)
```
Expressive Method Names

Method names can end with: ```?``` for predictive methods and ```!``` for for dangerous side-effects.

```ruby
def can_dvided_by?(number)
	return false if number.zero?
	true
end

puts can_divide_by? 3
puts can_divide_by? 0
```

Default Arguments

Methods can have default arguments.

```ruby
def factorial_with_default (n = 5)
	n == 0? 1 : n = n * factorial_with_default(n - 1)
end
```

Splat

* prefixes parameter inside method definition.
