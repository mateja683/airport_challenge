Airport Challenge [![Build Status](https://travis-ci.org/mateja683/airport_challenge.svg?branch=master)](https://travis-ci.org/mateja683/airport_challenge)
=================

UPDATED README

Attached are all the files associated with my airport challenge.

I started by creating a Plane class, and created methods to allow them to be either flying or grounded. From there, I set the Airport class, which could instruct for specific planes to take off and land. Within these two methods, I built up several features which allowed for errors, including when the airport was too full, and preventing flying planes from taking off and grounded planes from landing.

Finally, I created the weather class, which allowed me to introduce stormy weather into the airport class. I did this by sampling through a series of weather types, and creating a stormy variable for when the variable was stormy. In the airport class, I then created a bad weather variable for when the weather was stormy.

Please have a look, and let me know if you have any suggestions. Many thanks!

Example of the IRB functionality:

mateja@Matejas-MacBook-Pro:~/Projects/airport_challenge$ irb
2.2.3 :001 > require './lib/airport.rb'
 => true
2.2.3 :002 > a = Airport.new
 => #<Airport:0x007f80390a3e38 @capacity=50, @planes=[], @weather=#<Weather:0x007f80390a3de8>>
2.2.3 :003 > p1 = Plane.new
 => #<Plane:0x007f803909aef0 @location=:grounded>
2.2.3 :004 > p2 = Plane.new
 => #<Plane:0x007f80390916c0 @location=:grounded>
2.2.3 :005 > p3 = Plane.new
 => #<Plane:0x007f8039081248 @location=:grounded>
2.2.3 :006 > p4 = Plane.new
 => #<Plane:0x007f8039071cd0 @location=:grounded>
2.2.3 :007 > p5 = Plane.new
 => #<Plane:0x007f80390634a0 @location=:grounded>
2.2.3 :008 > p1.flying?
 => :air
2.2.3 :009 > p2.flying?
 => :air
2.2.3 :010 > p3.flying?
 => :air
2.2.3 :011 > a.land(p1)
 => [#<Plane:0x007f803909aef0 @location=:grounded>]
2.2.3 :012 > a.land(p2)
 => [#<Plane:0x007f803909aef0 @location=:grounded>, #<Plane:0x007f80390916c0 @location=:grounded>]
2.2.3 :013 > a.land(p3)
 => [#<Plane:0x007f803909aef0 @location=:grounded>, #<Plane:0x007f80390916c0 @location=:grounded>, #<Plane:0x007f8039081248 @location=:grounded>]
2.2.3 :014 > a.take_off(p4)
RuntimeError: plane is already flying
	from /Users/mateja/Projects/airport_challenge/lib/airport.rb:25:in `take_off'
	from (irb):10
	from /Users/mateja/.rvm/rubies/ruby-2.2.3/bin/irb:15:in `<main>'
2.2.3 :015 > a.take_off(p5)
from /Users/mateja/Projects/airport_challenge/lib/airport.rb:25:in `take_off'
from (irb):10
from /Users/mateja/.rvm/rubies/ruby-2.2.3/bin/irb:15:in `<main>'
2.2.3 :016 > a.land(p1)
RuntimeError: plane is already grounded
	from /Users/mateja/Projects/airport_challenge/lib/airport.rb:17:in `land'
	from (irb):16
	from /Users/mateja/.rvm/rubies/ruby-2.2.3/bin/irb:15:in `<main>'
2.2.3 :017 > a.land(p2)
RuntimeError: plane is already grounded
	from /Users/mateja/Projects/airport_challenge/lib/airport.rb:17:in `land'
	from (irb):17
	from /Users/mateja/.rvm/rubies/ruby-2.2.3/bin/irb:15:in `<main>'
2.2.3 :018 > a.land(p3)
RuntimeError: plane is already grounded
	from /Users/mateja/Projects/airport_challenge/lib/airport.rb:17:in `land'
	from (irb):18
	from /Users/mateja/.rvm/rubies/ruby-2.2.3/bin/irb:15:in `<main>'
2.2.3 :019 > a.land(p4)
 => [#<Plane:0x007f803909aef0 @location=:grounded>, #<Plane:0x007f80390916c0 @location=:grounded>, #<Plane:0x007f8039081248 @location=:grounded>, #<Plane:0x007f8039071cd0 @location=:grounded>]
2.2.3 :020 > a.take_off(p4)
RuntimeError: cannot take off in a storm
	from /Users/mateja/Projects/airport_challenge/lib/airport.rb:26:in `take_off'
	from (irb):20
	from /Users/mateja/.rvm/rubies/ruby-2.2.3/bin/irb:15:in `<main>'
2.2.3 :021 > a.take_off(p4)
 => #<Plane:0x007f8039071cd0 @location=:air>
2.2.3 :022 > a.take_off(p3)
 => #<Plane:0x007f8039081248 @location=:air>
2.2.3 :023 > a.take_off(p2)
 => #<Plane:0x007f80390916c0 @location=:air>
2.2.3 :024 > a.take_off(p1)
RuntimeError: cannot take off in a storm
	from /Users/mateja/Projects/airport_challenge/lib/airport.rb:26:in `take_off'
	from (irb):24
	from /Users/mateja/.rvm/rubies/ruby-2.2.3/bin/irb:15:in `<main>'
2.2.3 :025 > a.take_off(p1)
 => #<Plane:0x007f803909aef0 @location=:air>
2.2.3 :026 > p1
 => #<Plane:0x007f803909aef0 @location=:air>
2.2.3 :027 > p2
 => #<Plane:0x007f80390916c0 @location=:air>
2.2.3 :028 > p3
 => #<Plane:0x007f8039081248 @location=:air>
2.2.3 :029 > p4
 => #<Plane:0x007f8039071cd0 @location=:air>
2.2.3 :030 > p5
 => #<Plane:0x007f80390634a0 @location=:air>
2.2.3 :031 >



Instructions
---------

* Challenge time: rest of the day and weekend, until Monday 9am
* Feel free to use google, your notes, books, etc. but work on your own
* If you have a partial solution, **still check in a partial solution**
* You must submit a pull request to this repo with your code by 9am Monday morning
* If you do not submit a pull request, we will not be able to see your progress

Steps
-------

1. Fill out your learning plan self review for the week: https://github.com/makersacademy/learning_plan_october2015 (edit week 1 - you can edit directly on Github)
2. Fork this repo, and clone to your local machine
3. run the command `gem install bundle`
4. When the installation completes, run `bundle`
3. Complete the following task:

Task
-----

We have a request from a client to write the software to control the flow of planes at an airport. The planes can land and take off provided that the weather is sunny. Occasionally it may be stormy, in which case no planes can land or take off.  Here are the user stories that we worked out in collaboration with the client:

```
As an air traffic controller
So planes can land safely at my airport
I would like to instruct a plane to land

As an air traffic controller
So planes can take off safely from my airport
I would like to instruct a plane to take off

As an air traffic controller
So that I can avoid collisions
I want to prevent airplanes landing when my airport if full

As an air traffic controller
So that I can avoid accidents
I want to prevent airplanes landing or taking off when the weather is stormy

As an air traffic controller
So that I can ensure safe take off procedures
I want planes only to take off from the airport they are at

As the system designer
So that the software can be used for many different airports
I would like a default airport capacity that can be overridden as appropriate

As an air traffic controller
So the system is consistent and correctly reports plane status and location
I want to ensure a flying plane cannot take off and cannot be in an airport

As an air traffic controller
So the system is consistent and correctly reports plane status and location
I want to ensure a plane that is not flying cannot land and must be in an airport

As an air traffic controller
So the system is consistent and correctly reports plane status and location
I want to ensure a plane that has taken off from an airport is no longer in that airport
```

Your task is to test drive the creation of a set of classes/modules to satisfy all the above user stories. You will need to use a random number generator to set the weather (it is normally sunny but on rare occasions it may be stormy). In your tests, you'll need to use a stub to override random weather to ensure consistent test behaviour.

For overriding random weather behaviour, please read the documentation to learn how to use test doubles: https://www.relishapp.com/rspec/rspec-mocks/docs . There’s an example of using a test double to test a die that’s relevant to testing random weather in the test.

Please create separate files for every class, module and test suite.

The submission will be judged on the following criteria:

* Tests pass
* [Test coverage](https://github.com/makersacademy/course/blob/master/pills/test_coverage.md) is good
* The code is elegant: every class has a clear responsibility, methods are short etc.

**BONUS**

* Write an RSpec **feature** test that lands and takes off a number of planes

Note that is a practice 'tech test' of the kinds that employers use to screen developer applicants.  More detailed submission requirements/guidelines are in [CONTRIBUTING.md](CONTRIBUTING.md)

Finally, don’t overcomplicate things. This task isn’t as hard as it may seem at first.

* **Submit a pull request early.**  There are various checks that happen automatically when you send a pull request.  **You should pay attention to these - the results will be added to your pull request**.  Green is good.

* Finally, please submit a pull request before Monday at 9am with your solution or partial solution.  However much or little amount of code you wrote please please please submit a pull request before Monday at 9am.
