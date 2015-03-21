
#Esoteric Ruby from Ruby Association

Which string matches the following regular expression?

```ruby
/\A\d{3}-\d{4}\z/
```

```
a. foo@example.com

b. 690-0823

c. PCODE690-0823

d. 690-0x23
```

I thought it was D. Correct answer is B.
Plain english: “match the beginning of the string, followed by 3 digits, followed by a hyphen, followed by 4 digits, followed by the end of the string”.

---

What is the correct output of the following program?

```ruby
a = [1, 2, 3]
b = [4, 5, 6]
p a.zip(b).first
```

```
a. 1
b. [1, 2, 3]
c. [1, 4]
d. [3, 6]
```

My guess was C, and its correct. I never saw these methods but I figured that at least 4 has to be in there somewhere. 

The Array#zip method takes an array as its argument and is called upon an array receiver object. The method returns a new array, which is the result of merging the corresponding values from the two arrays.

The a.zip(b) call in the program above thus returns the nested array [[1, 4], [2, 5], [3, 6]]. The Array#first method, which returns the first element of an array, is then called on [[1, 4], [2, 5], [3, 6]], returning the array [1, 4]. Finally the p method is called on [1, 4].


------

Which of the four following Ruby programs will execute without errors?

a.
```ruby
  def foo(x)
    puts x
  end
  foo()
```

b. 
```ruby 
  def bar
    puts n
  end
  n = 10
  bar(n)
````

c. 
```ruby
  10.times do |i|
    n = i
    puts n
  end
  puts n
```

d.
```ruby

  n = 10
  n.times do |i|
    puts i + n
  end
```

My answer D. And its correct. 

-----


What is the correct output of the following program?

```ruby
s = 0xBacFace
s += 1
puts s
```


a. ```A number is printed to the standard output```

b. ```Nothing happens```

c. ```The string “BacFacf” is printed to the standard output```

d. ```A “SyntaxError: compile error” occurs```


No idea. I was thinking an error if I had to choose. correct answer is A. 

On the first line of the program, the literal 0xBacFace is assigned to the variable “s”. The “0x” at the head of the literal indicates that the rest of the literal is to be interpreted by Ruby as an integer in hexadecimal notation. Integers in hexadecimal notation are written using the numbers 0 to 9 and the letters A to F.

Since 0xBacFace is a valid hexadecimal integer, the assignment to “s”, the addition of the integer 1 and the call to the puts method all happen without causing any errors. The hexadecimal value of BacFace corresponds to the decimal number 195885774 and therefore the final output of the program is 195885775.

-----


Which one of the programs below produces the following output?

```ruby

[10, 20, 30, 40]
```

a. ```p [1, 2, 3, 4].select {|i| i * 10}```


b. ```p (1…5).to_a.map {|i| i * 10}```


c. ```p (10..40).to_a```


d. ```p [1, 2, 3, 4].zip([10, 10, 10, 10])```


No choice. Correct answer b. 

----

Which one of the programs below produces the following output?

```"cde" ```

a. ```p [“a”, “b”, “c”, “d”, “e”][0..2].join```

b. ````p “abcdefg” – “ab” – “fg” ```

c. ```p “abcdefg”[2..3]```

d. ```p “abcdefg”[2, 3]```


My choice C. Correct answer D. 

----


Of the following pieces of code, which one finishes execution without any errors?


a. ``` 10.+(“10”)```

b. ```Time.now.strftime(1999, 12, 11)```

c. ```1..10.to_s```

d. ```10.*(0xFace)```


Correct answer D. The 0xFace literal expresses an integer value in hexadecimal notation, so the code 10.*(0xFace)  simply multiplies two integers and completes without errors.

------

Given that the “tmp” directory does not exist in the current working directory, how many “rocking.rb” files are created during the following program’s execution? And how many remains after the execution finishes?

```ruby
["tmp", "tmp/lang",  "tmp/lang/ruby", "tmp/lang/python"].each do |dir|
  Dir.mkdir(dir)
end
Dir.chdir("tmp/lang")
Dir.new(".").each do |entry|
  filename = File.join(entry, "rocking.rb")
  File.open(filename, "w")
end
Dir.rmdir("python")

```

Answer: ```4 are created, 4 remain```

------

Which of the following expressions will return a Time object representing the time at exactly 24 hours ago?


a. ```Time.now - 1```

b. ```Time.now - 86400```

c. ```Time.yesterday```

d. ```Time.now - 24```


Correct answer B! 

------







##Credits

More problems found at:

http://www.minituku.net/drills?locale=en

Most of it is in Japanese but since this is about code, I guess it should not matter. Many interesting exercises I have not seen before. 