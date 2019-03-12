## Learning a new language steps

### To start Research questions:
- ask yourself why you want / need to learn it.
- is the language interpreted or compiled?
- is it dynamically or statically typed?
- can you run scripts directly or do they need a Main method?
- does the language have primitives?
- what are the main online resources?
  - library vendors
  - docs
- are there different versions?
  - which are used now?
- is there a widely used style guide?

### Next learn basic syntax:
- variables
  - `cammelCase`, `snake_case` or something else?
- basic types / primitives
- how do you print to stout?
- truthy / falsey values
- comparison operators
  - what do they actually compare?
- control flow structures
  - if-then-else
  - ternary
  - switch
  - other shorthand syntax
- loops
  - what kinds are available?
    - for
    - while
    - for in
- how do you print to stout?
- how do you capture user input from stdin?

_**Exercise ideas:**_
- _hello world_
- _hello 'your name'_
- _temperature convertor (C to F)_
- _guess number game with user input_
- _animal sorter_
  - _user inputs cat it outputs mammal, swan outputs bird, trout outputs fish etc._

### More advanced syntax:
- functions / methods
  - what do functions return if they are empty?
  - what is a functions scope?
  - can functions be anonymous / lambdas?
  - implicit returns?
- inbuilt compound types
  - arrays
  - hashes / dictionaries (i.e. key value pairs).
  - lists
  - strings?
- compound type manipulation / iteration
  - map
  - reduce
  - filter / select
  - each
  - regular loops in this context.
  - which of these mutate the caller?
- ranges
- string manipulation
  - concatenation
  - uppercase / lower case
  - how do you format / interpolate a string?
  - delete a char
- randomness
- file manipulation
  - CRUD for this
- throwing and catching errors / exceptions

_**Exercise ideas:**_
- _fizzBuzz_
- _fibonacci - procedural_
- _fibonacci - functional_
- _magic eight ball function_
- _convert int to string_
- _convert string to array of chars_
- _implement `reduce()` function for an array of ints_
- _roman numeral convertor function_
- _isPrime function_
- _implement a binary search function_
- _implement you own `map()` method on a collection that accepts a function as an an argument._
- _inventory tracker using a flat file._
- _short text adventure game._
- _scrabble word scorer_
- _blackjack game_

### OOP:
- how do you declare a class?
  - class methods
  - class variables
  - class instance variables
  - private methods
  - inheritance
  - getter / setter shorthand?
- how do you instantiate an object?
- is the language pass-by-reference or pass-by-value?
- modules / abstract classes?

### Testing:
- what is the main TDD framework?
  - i.e. the Rspec / xUnit?
  - how do you?
    - use test doubles
    - mock
    - stub
    - expect / assert things
    - matchers
  - what is the best way to structure test files.
- what is the main BDD testing framework?

_**OOP TDD exercise ideas**_
- _transport hierarchy - 'a motorbike is a vehicle'_
- _oyster card system_
- _restaurant system_
- _tube system with multiple stops._
- _airport_
- _car with separate parts (composition)_
- _noughts and crosses_
- _battleships_
- _guess who_
- _rock paper scissors spock._
- _define you own exception class called Tantrum_
- _create a Kight class that has an inventory and can go on quests / has damage / strength._

### Upfront work:
- how do you set up an environment?
  - install the language
  - manage language versions / environments
  - manage packages
  - manage builds
- how do you work with multiple project files?
  - import / require / load etc.

### Basic tools:
- how do you open the REPL?
- debugging tool?
- code linting?
- test coverage tool?
- task runner?
- how do you run scripts from the `cli`?
- code metric reporter
- packages to make coding the language easier in your favourite editor.

### Further basic things:
- browse standard library
  - how do you do basic net working?
    - http
    - tcp
  - maths modules?
  - file / dir navigation
  - UI modules?
  - logging modules?
  - anything else that catches your eye.

### Web:
- what is the 'minimal' web framework? (e.g. Sinatra or Flask)
- what is the 'maximal' web framework? (e.g. Rails or Django)
- how do you configure these to be up and running? Set up testing etc.
- what is the suitability of each?

_**Web projects / exercises**_
- _hello world_
- _bookmark manager_
- _readability score calculator_
- _twitter clone_
- _ipsum lorem generator_
- _group chat app_
- _simple calendar app_
- _online battleships game_
- _income distribution calculator_
