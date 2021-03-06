# Checkpoint 04

> If you have not completed the survey yet,
please do so by the end of the day!

## Instructions

1. Fork this repo
2. Clone your fork
3. Fill in your answers by writing in the appropriate area, or placing an 'x' in
the square brackets (for multiple-choice questions).
4. Add/Commit/Push your changes to Github.
5. Open a pull request.

> **Note**: Only place your answer between backticks. Don't modify the backticks,
or the language specifier after them.

## Ruby Basics & Enumerables (meets Beauty and the Beast)

### Question 1

Define a method called `offer_rose`, which should take one argument named `person`.

When called the method should `puts` "Would you take this rose, `person`, in exchange for giving an old beggar woman shelter from the bitter cold?"

Demonstrate calling the method, passing in "young prince" as the argument.

Write your code here:
```ruby
def offer_rose(person)
  puts "Would you take this rose, #{person}, in exchange for giving me an old beggar woman shelter from the bitter cold?"
end

offer_rose('young prince')

```

### Question 2

Assume the following hash:

```ruby
town = {
  residents: ["Maurice", "Belle", "Gaston"],
  castle: {
    num_rooms: 47,
    residents: "Robby Benson",
    guests: []
  }
}
```

Using Ruby, remove Belle from the town residents, and
add her to the list of guests in the castle.

Write your code here:
```ruby
town = {
  residents: ["Maurice", "Belle", "Gaston"],
  castle: {
    num_rooms: 47,
    residents: "Robby Benson",
    guests: []
  }
}

puts town[:residents].each do |resident|
	if resident = "Belle"
		town[:guests] << "Belle"
	end
end

```

### Question 3

Assume you have an array of strings representing friend's names:

```ruby
friends = ["Chip Potts", "Cogsworth", "Lumière", "Mrs. Potts"]
```

Using `.each` AND string interpolation, produce output (using `puts`) like so:

```
Belle is friends with Chip Potts
Belle is friends with Cogsworth
Belle is friends with Lumière
Belle is friends with Mrs. Potts
```

Write your code here:
```ruby
friends = ["Chip Potts", "Cogsworth", "Lumière", "Mrs. Potts"]

friends.each do |friend|
	puts "Belle is friends with #{friend}"
end

```
## Ruby OOP (meets Lion King)

### Question 4

Create ruby classes for `Animal` and `Lion`.
Each `Animal` should have:

- a `name` attribute
- a `greet` instance method
- Getter and setter for `name`

Create a new `Animal` instance with the name "Pumba"

Make the `Lion` inherit from the `Animal` class.
The `Lion` class should have a `pack` class variable that holds references to each instance created.

Each lion should have:
- a `king` attribute which is a boolean
  - If the instance's `name` is `Simba` make the `king` attribute true

Create a new lion instance with the name `simba`

```ruby
class Animal
	attr_accessor :name, :greet

	def initialize(name)
		@name = name
	end

	def greet
		puts "Hello, my name is #{@name}"
	end
end

Animal.new("Pumba")


class Lion < ANIMAL
	@@pack = []
	def initialize(name)
		@name = name
		@@pack << self
	end
end

Lion.new("simba")
```

## SQL, Databases, and ActiveRecord (meets Aladdin)

### Question 5

Describe what an ERD is, and why we create them for applications. Also give an
example what the attributes and relationships might be for the following
entities (no need to draw an ERD):
* Genie
* Lamp
* Person
* Pet

Your answer:
```
ERD is Entity Relationship Diagram and it is a visual plan of how you want to create a database and table structures.

Genie: name-string, color-string, age-fixnum, free - boolean, number_of_wishes-fixnum, master-string
  One-One relationship
Lamp: color-string, genie_inside-boolean, cramped_in_there - boolean


Person: f_name-string, l_name-string, age-fixnum, dob-date, height-string, weight_lbs:fixnum, hair-boolean, hair_color-string...
One-One relationship, one-to-many relationship, many-many relationship
Pet: type_of_animal-string, breed-string, weight-fixnum, weight_unit-string...

```

### Question 6

Describe what a schema is, and how we represent a one-to-many relationship in a
SQL database. If you need an example, you can use: people and wishes
(one-to-many).

Your answer:
```
A schema is what defines a table's columns and the names, data-type, and constraints.

A one to many relationship is when one of something can have many  of another thing. In the case of people and wishes, Aladdin has 3 instances wishes, but those wishes are only for Aladdin. If Rajah somehow got a hold of the lamp and had control of the Genie and the Genie spoke tiger, Rajah would have a whole new set of 3 wishes separate from Aladdin. 
```
