# Analog

> Not digital.

Before we do any computer-y things, we're going to stay in the physical realm using pen and graph paper (to keep what we write monospace-y). When things get messy (and they will), we'll use scissors, green and red highlighters, and tape.

![image of graph paper](link to image)

We'll be using Tom Dalling's [FizzBuzz In Too Much Detail](https://www.tomdalling.com/blog/software-design/fizzbuzz-in-too-much-detail/) to guide our versioning process. Why? Because it's in Ruby and FizzBuzz should be familiar.

Take a piece of graph paper and write down the following code:

```ruby
1.upto(100) do |i| 
  if i % 3 == 0 && i % 5 == 0
    puts 'FizzBuzz'
  elsif i % 3 == 0 
    puts 'Fizz'
  elsif i % 5 == 0 
    puts 'Buzz'
  else
    puts i
  end
end
```

Great! You have the first version of your FizzBuzz program. Let's call it "FizzBuzz 1.0". Following along with Tom's refactoring, we need to remove the repetitive bits `i % 3 == 0`, `i % 5 == 0`, and `puts`. Our next version 2.0 should look like:

'''ruby
1.upto(100) do |i| 
  fizz = (i % 3 == 0)
  buzz = (i % 5 == 0)
  puts case
       when fizz && buzz then 'FizzBuzz'
       when fizz then 'Fizz'
       when buzz then 'Buzz'
       else i
       end
end
'''

This refactoring would be easy on a computer, but how should we refactor in real life? Erase (provided we used a pencil)? Strike through and write in our new code squeezed above but on the same line? White out and write on top? If we choose any of these options and need to revert back to our prior version, what then? Maybe our new code could be written with a different colored pen, but surely after several revisions it would look like a Jackson Pollock painting! It seems that (for starters) once we have an official version of a file, it should never change just in case we need to go back to it.

If our original (previous) version doesn't change, how then should we generate the new version? Should we take our paper to a copy machine to then edit the copy, or should we write version 2.0 on a new, blank sheet of paper?
