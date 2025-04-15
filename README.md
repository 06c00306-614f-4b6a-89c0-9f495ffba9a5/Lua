# Lua Programming Language: Comprehensive Reference Guide

<img src="https://www.lua.org/images/lua-logo.gif" alt="Lua Logo" width="128" height="128" align="right" />

## Table of Contents

- [Introduction](#introduction)
  - [What is Lua?](#what-is-lua)
  - [Design Philosophy](#design-philosophy)
  - [Use Cases](#use-cases)
- [Getting Started](#getting-started)
  - [Installation](#installation)
  - [Running Lua Code](#running-lua-code)
  - [Development Environment](#development-environment)
- [Language Fundamentals](#language-fundamentals)
  - [Lexical Conventions](#lexical-conventions)
  - [Comments](#comments)
  - [Variables and Assignments](#variables-and-assignments)
  - [Scope](#scope)
  - [Naming Conventions](#naming-conventions)
- [Data Types](#data-types)
  - [Nil](#nil)
  - [Booleans](#booleans)
  - [Numbers](#numbers)
  - [Strings](#strings)
  - [Functions](#functions)
  - [Userdata](#userdata)
  - [Threads](#threads)
  - [Tables](#tables)
  - [Type Checking and Conversion](#type-checking-and-conversion)
- [Operators](#operators)
  - [Arithmetic Operators](#arithmetic-operators)
  - [Relational Operators](#relational-operators)
  - [Logical Operators](#logical-operators)
  - [String Concatenation](#string-concatenation)
  - [Length Operator](#length-operator)
  - [Operator Precedence](#operator-precedence)
- [Control Structures](#control-structures)
  - [Conditional Statements](#conditional-statements)
  - [Loops](#loops)
  - [Alternative to Switch Statements](#alternative-to-switch-statements)
  - [Alternative to Ternary Operator](#alternative-to-ternary-operator)
- [Functions](#functions-1)
  - [Function Definition](#function-definition)
  - [Parameters and Arguments](#parameters-and-arguments)
  - [Return Values](#return-values)
  - [Variadic Functions](#variadic-functions)
  - [Anonymous Functions](#anonymous-functions)
  - [Closures](#closures)
  - [Function Environments](#function-environments)
  - [Tail Calls](#tail-calls)
- [Tables in Depth](#tables-in-depth)
  - [Table Creation](#table-creation)
  - [Table Access and Manipulation](#table-access-and-manipulation)
  - [Arrays (Sequential Tables)](#arrays-sequential-tables)
  - [Dictionaries (Associative Tables)](#dictionaries-associative-tables)
  - [Mixed Tables](#mixed-tables)
  - [Table Traversal](#table-traversal)
  - [Table Library Functions](#table-library-functions)
  - [Multi-dimensional Tables](#multi-dimensional-tables)
  - [Tables as Namespaces](#tables-as-namespaces)
  - [Performance Considerations](#performance-considerations)
- [Metatables and Metamethods](#metatables-and-metamethods)
  - [Setting and Getting Metatables](#setting-and-getting-metatables)
  - [Arithmetic Metamethods](#arithmetic-metamethods)
  - [Relational Metamethods](#relational-metamethods)
  - [Table Access Metamethods](#table-access-metamethods)
  - [Call Metamethod](#call-metamethod)
  - [Metatable Applications](#metatable-applications)
- [Object-Oriented Programming](#object-oriented-programming)
  - [Tables as Objects](#tables-as-objects)
  - [Self and Colon Syntax](#self-and-colon-syntax)
  - [Constructors](#constructors)
  - [Methods](#methods)
  - [Inheritance](#inheritance)
  - [Multiple Inheritance](#multiple-inheritance)
  - [Privacy and Encapsulation](#privacy-and-encapsulation)
  - [OOP Design Patterns](#oop-design-patterns)
- [Modules and Packages](#modules-and-packages)
  - [Creating Modules](#creating-modules)
  - [Loading Modules](#loading-modules)
  - [Module Patterns](#module-patterns)
  - [Standard Modules](#standard-modules)
  - [LuaRocks Package Manager](#luarocks-package-manager)
- [Error Handling](#error-handling)
  - [Error Generation](#error-generation)
  - [Error Catching](#error-catching)
  - [Assertions](#assertions)
  - [Error Messages](#error-messages)
  - [Traceback](#traceback)
- [Coroutines](#coroutines)
  - [Creating Coroutines](#creating-coroutines)
  - [Coroutine States](#coroutine-states)
  - [Yielding and Resuming](#yielding-and-resuming)
  - [Coroutines vs Threads](#coroutines-vs-threads)
  - [Use Cases](#use-cases-1)
- [File I/O](#file-io)
  - [Simple I/O Operations](#simple-io-operations)
  - [File Handles](#file-handles)
  - [Reading From Files](#reading-from-files)
  - [Writing To Files](#writing-to-files)
  - [File Position](#file-position)
  - [Other File Operations](#other-file-operations)
- [Standard Libraries](#standard-libraries)
  - [String Library](#string-library)
  - [Table Library](#table-library)
  - [Math Library](#math-library)
  - [IO Library](#io-library)
  - [OS Library](#os-library)
  - [Debug Library](#debug-library)
  - [UTF-8 Library](#utf-8-library)
- [Advanced Topics](#advanced-topics)
  - [Garbage Collection](#garbage-collection)
  - [Weak References](#weak-references)
  - [Lua C API](#lua-c-api)
  - [Performance Optimization](#performance-optimization)
  - [JIT Compilation](#jit-compilation)
  - [Embedding Lua](#embedding-lua)
- [Best Practices](#best-practices)
  - [Code Style](#code-style)
  - [Memory Management](#memory-management)
  - [Error Handling](#error-handling-1)
  - [Testing](#testing)
  - [Documentation](#documentation)
- [Resources](#resources)
  - [Official Documentation](#official-documentation)
  - [Books](#books)
  - [Community](#community)
  - [Tools](#tools)

## Introduction

### What is Lua?

Lua is a powerful, efficient, lightweight, embeddable scripting language. Designed to be a compact scripting language with extensible semantics, it has found applications across a wide spectrum of domains, from game development to embedded systems.

Developed at the Pontifical Catholic University of Rio de Janeiro in Brazil since 1993, Lua has gained prominence for its clean design, high performance, and ease of integration with other languages, particularly C and C++.

### Design Philosophy

Lua is guided by the following principles:

- **Simplicity**: Lua has a minimalist syntax and semantics, making it easy to learn and use.
- **Efficiency**: It is implemented as a single, small C library, with excellent performance and low overhead.
- **Portability**: Lua is written in ANSI C, making it compatible with virtually any platform.
- **Embeddability**: Lua is designed to be embedded in other applications, with a clean C API.
- **Extensibility**: Users can extend the language through metatables and C functions.

### Use Cases

Lua's versatile nature has led to its adoption in numerous domains:

- **Game Development**: Used in titles like World of Warcraft, Angry Birds, and Roblox
- **Embedded Systems**: Found in routers, TVs, and IoT devices
- **Configuration**: Used as a configuration language in applications like Nginx
- **Application Scripting**: Provides extensibility in applications like Adobe Lightroom
- **Scientific Computing**: Used in numerical computing and data analysis
- **Mobile Applications**: Powers scripting in many mobile apps

## Getting Started

### Installation

#### Unix/Linux/macOS

```bash
# Using package managers
sudo apt-get install lua5.3          # Debian/Ubuntu
sudo yum install lua                 # CentOS/RHEL
brew install lua                     # macOS with Homebrew

# From source
curl -R -O http://www.lua.org/ftp/lua-5.4.4.tar.gz
tar -zxf lua-5.4.4.tar.gz
cd lua-5.4.4
make linux test    # or 'macosx' for macOS
sudo make install
```

#### Windows

- Visit [luaforwindows.github.io](https://github.com/rjpcomputing/luaforwindows) for a comprehensive Lua environment
- Alternatively, download binaries from [lua-users.org/wiki/LuaBinaries](http://lua-users.org/wiki/LuaBinaries)

#### Verifying Installation

```bash
lua -v
```

### Running Lua Code

#### Interactive Mode

```bash
lua
```

You can enter Lua code directly, and it will be executed immediately.

#### Running Scripts

```bash
lua script.lua
```

#### Command Line Arguments

```bash
lua -e "print('Hello, World!')"
```

### Development Environment

#### Text Editors and IDEs

- **Visual Studio Code** with Lua extension
- **ZeroBrane Studio**: Dedicated Lua IDE
- **IntelliJ IDEA** with Lua plugin
- **Sublime Text** with Lua package
- **Vim/Neovim** with Lua syntax highlighting

#### Debugging Tools

- **ZeroBrane Studio**: Integrated debugger
- **MobDebug**: Remote debugger
- **Lua Debug Adapter**: For Visual Studio Code

## Language Fundamentals

### Lexical Conventions

Lua is case-sensitive. The language has a free-form syntax and generally ignores whitespace except as a delimiter between tokens.

#### Reserved Keywords

```
and       break     do        else      elseif
end       false     for       function  goto
if        in        local     nil       not
or        repeat    return    then      true
until     while
```

### Comments

```lua
-- Single line comment

--[[
  Multi-line
  comment
]]
```

### Variables and Assignments

Variables in Lua are dynamically typed and not declared before assignment:

```lua
name = "John"     -- Global variable
local age = 25    -- Local variable

-- Multiple assignment
local x, y, z = 10, 20, 30

-- Swapping values
x, y = y, x
```

### Scope

Lua has lexical scoping with global and local variables:

```lua
-- Global variable (accessible anywhere)
globalVar = "I'm global"

function scopeDemo()
    -- Local to the function
    local localVar = "I'm local to scopeDemo"
    
    if true then
        -- Local to the if block
        local blockVar = "I'm local to this block"
        print(blockVar)    -- Accessible
        print(localVar)    -- Accessible
        print(globalVar)   -- Accessible
    end
    
    -- print(blockVar)     -- Error: not accessible
    print(localVar)        -- Accessible
    print(globalVar)       -- Accessible
end

print(globalVar)           -- Accessible
-- print(localVar)         -- Error: not accessible
```

Variables are global by default. Best practice is to explicitly declare variables as `local` to avoid polluting the global namespace.

### Naming Conventions

- Variable names can contain letters, numbers, and underscores
- Cannot start with a number
- Common convention is to use `camelCase` or `snake_case`
- Constants are often written in `ALL_CAPS`

```lua
-- Valid names
name = "John"
user_age = 25
userEmail = "john@example.com"
MAX_SIZE = 100

-- Invalid names
-- 2ndPlace = "Silver"    -- Cannot start with a number
```

## Data Types

Lua is dynamically typed, with the following basic types:

### Nil

Represents the absence of a useful value:

```lua
nonExistentVar = nil     -- Explicit nil assignment
print(undefinedVar)      -- Prints "nil" for undefined variables
```

### Booleans

Boolean values are `true` and `false`:

```lua
isValid = true
isFinished = false

-- Note: only false and nil are considered false in conditionals
-- All other values (including 0, "", {}) are considered true
```

### Numbers

Lua uses double-precision floating-point for all numbers:

```lua
integer = 42
floating = 3.14159
scientific = 1.5e10
hexadecimal = 0xFF       -- 255

-- Maximum integer precision
maxInteger = 9007199254740992  -- Beyond this, precision may be lost
```

### Strings

Strings are immutable sequences of characters:

```lua
-- String literals can use single or double quotes
singleQuoted = 'Hello'
doubleQuoted = "World"

-- Multi-line strings
multiline = [[
This is a
multi-line string
with preserved whitespace
]]

-- Escape sequences
escaped = "Line 1\nLine 2\tTabbed"

-- Concatenation
fullName = "John" .. " " .. "Doe"

-- Simple string operations
length = #"Hello"                    -- 5
length = string.len("Hello")         -- 5

-- String conversion
numString = tostring(123)            -- "123"
```

#### String Library Functions

```lua
-- Finding substrings
index = string.find("Hello World", "World")    -- 7

-- Replacing substrings
newStr = string.gsub("Hello World", "World", "Lua")    -- "Hello Lua"

-- Case conversion
upper = string.upper("Hello")                  -- "HELLO"
lower = string.lower("Hello")                  -- "hello"

-- Substring extraction
sub = string.sub("Hello World", 1, 5)          -- "Hello"

-- Pattern matching
for word in string.gmatch("hello world", "%a+") do
    print(word)          -- Prints "hello" then "world"
end
```

### Functions

Functions are first-class values in Lua:

```lua
-- Function definition
function add(a, b)
    return a + b
end

-- Functions as variables
multiply = function(a, b)
    return a * b
end

-- Function calls
sum = add(5, 3)              -- 8
product = multiply(5, 3)     -- 15
```

### Userdata

Userdata represents C data in Lua. It's primarily used for interaction with C code and is not typically created directly in Lua.

### Threads

Threads in Lua represent coroutines (cooperative multitasking):

```lua
co = coroutine.create(function()
    for i = 1, 5 do
        print("Coroutine", i)
        coroutine.yield()
    end
end)
```

### Tables

Tables are the only composite data structure in Lua, used to represent arrays, dictionaries, objects, and more:

```lua
-- Empty table
empty = {}

-- Array-like table (indices start at 1 by convention)
array = {10, 20, 30, 40}

-- Dictionary-like table
person = {
    name = "John",
    age = 30,
    ["favorite color"] = "blue"  -- Keys with spaces need square brackets
}

-- Mixed table
mixed = {
    "first",
    second = "value",
    [3] = "third"
}

-- Access elements
firstElement = array[1]           -- 10
personName = person.name          -- "John"
color = person["favorite color"]  -- "blue"
```

### Type Checking and Conversion

```lua
-- Check type
valueType = type(value)    -- Returns "nil", "number", "string", "boolean", etc.

-- Explicit conversions
numStr = "123"
num = tonumber(numStr)     -- 123

num = 123
str = tostring(num)        -- "123"
```

## Operators

### Arithmetic Operators

```lua
sum = 10 + 5       -- Addition: 15
difference = 10 - 5  -- Subtraction: 5
product = 10 * 5    -- Multiplication: 50
quotient = 10 / 3   -- Division: 3.3333...
modulus = 10 % 3    -- Modulus: 1
exponentiation = 10 ^ 2  -- Exponentiation: 100
negation = -10      -- Negation: -10
```

Lua does not have increment/decrement (++/--) or compound assignment operators (+=, -=, etc.):

```lua
-- Instead of x++, use:
x = x + 1

-- Instead of x += 5, use:
x = x + 5
```

### Relational Operators

```lua
equal = (10 == 10)          -- Equal to: true
notEqual = (10 ~= 5)        -- Not equal to: true
lessThan = (5 < 10)         -- Less than: true
greaterThan = (10 > 5)      -- Greater than: true
lessOrEqual = (5 <= 5)      -- Less than or equal to: true
greaterOrEqual = (10 >= 10) -- Greater than or equal to: true
```

### Logical Operators

```lua
andResult = true and false          -- Logical AND: false
orResult = true or false            -- Logical OR: true
notResult = not true                -- Logical NOT: false

-- Short-circuit evaluation
result = nil and someFunction()     -- someFunction() is not called

-- Logical operators can be used for conditional assignment
x = x or defaultValue               -- Set x to defaultValue if x is nil or false
```

### String Concatenation

```lua
greeting = "Hello, " .. "World!"    -- "Hello, World!"
```

### Length Operator

```lua
arrayLength = #{"a", "b", "c"}      -- 3
stringLength = #"Hello"             -- 5
```

### Operator Precedence

From highest to lowest precedence:

```
^
unary operators (not, #, -)
*, /, %
+, -
..
<, >, <=, >=, ~=, ==
and
or
```

Use parentheses for clarity:

```lua
result = (a + b) * c       -- Explicit precedence
```

## Control Structures

### Conditional Statements

#### If Statement

```lua
if age < 18 then
    print("Minor")
elseif age >= 18 and age < 65 then
    print("Adult")
else
    print("Senior")
end
```

### Loops

#### While Loop

```lua
local i = 1
while i <= 10 do
    print(i)
    i = i + 1
    
    if i == 8 then
        break  -- Exit the loop early
    end
end
```

#### Repeat-Until Loop

The condition is tested at the end, so the loop always executes at least once:

```lua
local i = 1
repeat
    print(i)
    i = i + 1
until i > 10
```

#### Numeric For Loop

```lua
for i = 1, 10, 1 do  -- start, end, step (step is optional)
    print(i)
end

-- Count down
for i = 10, 1, -1 do
    print(i)
end
```

#### Generic For Loop

Iterates over items provided by an iterator function:

```lua
-- Iterate over table elements
for key, value in pairs(table) do
    print(key, value)
end

-- Iterate over array elements
for index, value in ipairs(array) do
    print(index, value)
end

-- Iterate over string characters
for i = 1, #str do
    print(string.sub(str, i, i))
end
```

### Alternative to Switch Statements

Lua doesn't have switch statements, but there are several alternatives:

```lua
-- Using if-elseif-else
if action == "create" then
    createFile()
elseif action == "read" then
    readFile()
elseif action == "update" then
    updateFile()
elseif action == "delete" then
    deleteFile()
else
    errorHandler()
end

-- Using a table of functions
local actions = {
    create = createFile,
    read = readFile,
    update = updateFile,
    delete = deleteFile
}

local handler = actions[action] or errorHandler
handler()
```

### Alternative to Ternary Operator

Lua doesn't have a ternary operator, but this pattern works:

```lua
-- Instead of: result = condition ? trueValue : falseValue
result = condition and trueValue or falseValue

-- Example
canVote = age >= 18 and true or false
```

Note: This works because `and` returns its second operand if the first is true, and `or` returns its second operand if the first is false.

## Functions

### Function Definition

```lua
-- Named function
function add(a, b)
    return a + b
end

-- Anonymous function assigned to a variable
multiply = function(a, b)
    return a * b
end

-- Local function
local function subtract(a, b)
    return a - b
end
```

### Parameters and Arguments

```lua
-- Basic parameters
function greet(name)
    return "Hello, " .. name
end

-- Default values
function greetWithDefault(name)
    name = name or "Guest"  -- Default value if name is nil or false
    return "Hello, " .. name
end

-- Multiple parameters
function fullName(firstName, lastName)
    return firstName .. " " .. lastName
end
```

### Return Values

Lua functions can return multiple values:

```lua
function getPersonInfo()
    return "John", 30, "Developer"
end

-- Capture all return values
name, age, job = getPersonInfo()

-- Capture only the first value
name = getPersonInfo()

-- Capture specific values
name, age = getPersonInfo()
```

### Variadic Functions

Functions that accept a variable number of arguments:

```lua
function sum(...)
    local total = 0
    -- Pack arguments into a table
    local args = {...}
    
    for _, value in ipairs(args) do
        total = total + value
    end
    
    return total
end

result = sum(1, 2, 3, 4, 5)  -- 15

-- Direct iteration over variadic arguments
function printAll(...)
    for i, value in ipairs({...}) do
        print(i, value)
    end
end
```

### Anonymous Functions

Functions without names, often used as callbacks or for one-time use:

```lua
-- As an argument to another function
table.sort(numbers, function(a, b)
    return a > b  -- Sort in descending order
end)

-- Stored in a variable
local callback = function(x)
    return x * x
end
```

### Closures

Functions that capture and remember their environment:

```lua
function createCounter()
    local count = 0
    
    return function()
        count = count + 1
        return count
    end
end

local counter = createCounter()
print(counter())  -- 1
print(counter())  -- 2
print(counter())  -- 3

-- Each closure has its own environment
local counter2 = createCounter()
print(counter2())  -- 1
```

### Function Environments

Every function in Lua has an environment associated with it:

```lua
-- In Lua 5.1
function envTest()
    localVar = "This is actually global!"
end

-- In Lua 5.2+
function envTest()
    _ENV.localVar = "This is actually global!"
end
```

### Tail Calls

A tail call is a function call that is the last action in a function. Lua optimizes proper tail calls for efficient recursion:

```lua
function factorial(n, accumulator)
    accumulator = accumulator or 1
    if n <= 1 then
        return accumulator
    end
    -- This is a tail call - it doesn't need to keep the current stack frame
    return factorial(n - 1, n * accumulator)
end
```

## Tables in Depth

### Table Creation

```lua
-- Empty table
local empty = {}

-- Table with initial values
local numbers = {10, 20, 30}

-- Table with explicit indices
local sparse = {[1] = "one", [5] = "five", [10] = "ten"}

-- Table with named fields
local person = {
    name = "John",
    age = 30,
    isEmployed = true
}

-- Mixed table
local mixed = {
    "first value",  -- Implicitly [1] = "first value"
    second = "named value",
    [3] = "explicit index"
}

-- Nested tables
local nested = {
    personal = {
        name = "John",
        age = 30
    },
    professional = {
        title = "Developer",
        skills = {"Lua", "Python", "JavaScript"}
    }
}
```

### Table Access and Manipulation

```lua
-- Accessing array elements (indices start at 1 by convention)
local first = numbers[1]      -- 10

-- Accessing dictionary elements
local name = person.name      -- "John"
local age = person["age"]     -- 30 (alternative syntax)

-- Adding or updating elements
numbers[4] = 40               -- Add to array
person.email = "john@example.com"  -- Add to dictionary
person["phone"] = "555-1234"       -- Alternative syntax

-- Removing elements
numbers[2] = nil              -- Remove by setting to nil
person.age = nil              -- Remove from dictionary

-- Checking if a key exists
if person.email ~= nil then
    print("Email exists")
end
```

### Arrays (Sequential Tables)

Lua conventionally uses 1-based indexing for arrays:

```lua
local fruits = {"apple", "banana", "cherry"}

-- Length operator works properly only for arrays without gaps
local count = #fruits         -- 3

-- Inserting elements
table.insert(fruits, "date")              -- Append to end
table.insert(fruits, 2, "blueberry")      -- Insert at position

-- Removing elements
local removed = table.remove(fruits)      -- Remove and return last element
local removed = table.remove(fruits, 2)   -- Remove and return element at position

-- Iterating through arrays
for i = 1, #fruits do
    print(i, fruits[i])
end

-- Or using ipairs (safer for arrays)
for i, fruit in ipairs(fruits) do
    print(i, fruit)
end
```

### Dictionaries (Associative Tables)

```lua
local person = {
    name = "John",
    age = 30,
    ["favorite color"] = "blue"  -- Keys with spaces need brackets
}

-- Adding or updating entries
person.job = "Developer"
person["salary"] = 75000

-- Removing entries
person.age = nil

-- Checking existence
if person.email then
    -- This block is skipped because person.email is nil
end

-- Iterating through dictionaries
for key, value in pairs(person) do
    print(key, value)
end
```

### Mixed Tables

Tables that contain both array-like and dictionary-like components:

```lua
local mixed = {
    "First",
    "Second",
    name = "Mixed Table",
    [10] = "Tenth element"
}

-- Accessing components
local second = mixed[2]       -- "Second"
local name = mixed.name       -- "Mixed Table"

-- Length only counts sequential array part starting from 1
print(#mixed)                 -- 2, not 3
```

### Table Traversal

```lua
-- pairs(): Iterates over all table keys in arbitrary order
for key, value in pairs(table) do
    print(key, value)
end

-- ipairs(): Iterates over sequential array indices (1, 2, 3, ...)
for index, value in ipairs(array) do
    print(index, value)
end

-- next(): Low-level iterator
local key, value = next(table, previousKey)
```

### Table Library Functions

```lua
-- Insert and remove (as shown in Arrays section)
table.insert(t, [pos,] value)
table.remove(t, [pos])

-- Concatenate elements into a string
local str = table.concat({"a", "b", "c"}, ", ")  -- "a, b, c"

-- Sort array elements
table.sort(numbers)                 -- Default: ascending order
table.sort(strings, function(a, b)  -- Custom comparison function
    return a:lower() < b:lower()    -- Case-insensitive sort
end)

-- Get maximum index of array portion (Lua 5.2+)
local maxIndex = table.maxn(t)

-- Create a new table filled with a value (Lua 5.2+)
local newTable = table.pack(...)    -- Packs arguments into a table
local arg1, arg2 = table.unpack(t)  -- Unpacks a table into separate values
```

### Multi-dimensional Tables

```lua
-- Creating a 2D table
local grid = {}
for i = 1, 3 do
    grid[i] = {}
    for j = 1, 3 do
        grid[i][j] = i * j
    end
end

-- Accessing elements
local value = grid[2][3]  -- 6

-- Iterating through a 2D table
for i = 1, #grid do
    for j = 1, #grid[i] do
        print(i, j, grid[i][j])
    end
end
```

### Tables as Namespaces

```lua
-- Using tables to organize related functions
local math2 = {
    square = function(x)
        return x * x
    end,
    
    cube = function(x)
        return x * x * x
    end,
    
    isEven = function(x)
        return x % 2 == 0
    end
}

-- Using the namespace
local result = math2.square(5)  -- 25
```

### Performance Considerations

- Sequential tables (arrays) are optimized for fast access and iteration
- Hash tables are used for non-sequential keys
- Pre-allocating large tables can improve performance
- Avoid resizing tables frequently
- Prefer local variables over table lookups in loops

## Metatables and Metamethods

Metatables enable customizing table behavior for various operations.

### Setting and Getting Metatables

```lua
-- Create a metatable
local mt = {
    -- Metamethods will be defined here
}

-- Create a table
local t = {1, 2, 3}

-- Set the metatable
setmetatable(t, mt)

-- Get the metatable
local meta = getmetatable(t)
```

### Arithmetic Metamethods

```lua
local mt = {
    -- Addition
    __add = function(t1, t2)
        local result = {}
        for i = 1, math.max(#t1, #t2) do
            result[i] = (t1[i] or 0) + (t2[i] or 0)
        end
        return result
    end,
    
    -- Subtraction
    __sub = function(t1, t2)
        local result = {}
        for i = 1, math.max(#t1, #t2) do
            result[i] = (t1[i] or 0) - (t2[i] or 0)
        end
        return result
    end,
    
    -- Other arithmetic metamethods:
    -- __mul, __div, __mod, __pow, __unm (unary minus)
}

local t1 = {1, 2, 3}
local t2 = {4, 5, 6}
setmetatable(t1, mt)

local sum = t1 + t2  -- {5, 7, 9}
local diff = t1 - t2  -- {-3, -3, -3}
```

### Relational Metamethods

```lua
local mt = {
    -- Equality
    __eq = function(t1, t2)
        if #t1 ~= #t2 then
            return false
        end
        
        for i = 1, #t1 do
            if t1[i] ~= t2[i] then
                return false
            end
        end
        
        return true
    end,
    
    -- Less than
    __lt = function(t1, t2)
        return #t1 < #t2
    end,
    
    -- Less than or equal
    __le = function(t1, t2)
        return #t1 <= #t2
    end
    
    -- Note: Lua derives __gt and __ge from __lt and __le
}

local t1 = {1, 2, 3}
local t2 = {1, 2, 3, 4}
setmetatable(t1, mt)
setmetatable(t2, mt)

print(t1 == t1)  -- true
print(t1 == t2)  -- false
print(t1 < t2)   -- true
```

### Table Access Metamethods

```lua
local mt = {
    -- Called when accessing a missing key
    __index = function(t, key)
        if key == "length" then
            return #t
        else
            return "Key not found: " .. key
        end
    end,
    
    -- Called when assigning to a key (Lua 5.1+)
    __newindex = function(t, key, value)
        print("Setting", key, "to", value)
        rawset(t, key, value)  -- Actually set the value
    end
}

local t = {1, 2, 3}
setmetatable(t, mt)

print(t.length)  -- 3
print(t.missing)  -- "Key not found: missing"
t.newKey = "value"  -- Prints "Setting newKey to value"
```

### Call Metamethod

Makes a table callable like a function:

```lua
local counter = {count = 0}
local mt = {
    __call = function(t, increment)
        increment = increment or 1
        t.count = t.count + increment
        return t.count
    end
}

setmetatable(counter, mt)

print(counter())      -- 1
print(counter(5))     -- 6
```

### Metatable Applications

#### Default Values

```lua
function setDefault(t, default)
    local mt = {
        __index = function()
            return default
        end
    }
    setmetatable(t, mt)
    return t
end

local t = setDefault({}, 0)
print(t.nonexistent)  -- 0
```

#### Inheritance

```lua
-- Base class
local Shape = {area = 0}
function Shape:new(o)
    o = o or {}
    setmetatable(o, self)
    self.__index = self
    return o
end

function Shape:printArea()
    print("Area:", self.area)
end

-- Derived class
local Square = Shape:new()
function Square:new(side)
    local o = Shape:new{side = side}
    setmetatable(o, self)
    self.__index = self
    return o
end

function Square:calculateArea()
    self.area = self.side * self.side
end

local square = Square:new(5)
square:calculateArea()
square:printArea()  -- Area: 25
```

## Object-Oriented Programming

Although Lua isn't an object-oriented language by design, tables and metatables enable OOP patterns.

### Tables as Objects

```lua
-- Simple object
local person = {
    name = "John",
    age = 30,
    
    greet = function(self)
        return "Hello, my name is " .. self.name
    end
}

print(person.greet(person))  -- "Hello, my name is John"
```

### Self and Colon Syntax

The colon operator `:` implicitly passes `self`:

```lua
local person = {
    name = "John",
    
    greet = function(self)
        return "Hello, my name is " .. self.name
    end,
    
    birthday = function(self)
        self.age = self.age + 1
        return self.age
    end
}

-- These are equivalent:
print(person.greet(person))  -- Using dot notation
print(person:greet())        -- Using colon notation (passes self automatically)
```

### Constructors

```lua
-- Define a "class" table
local Person = {}

-- Constructor
function Person:new(name, age)
    local instance = {
        name = name,
        age = age or 0
    }
    setmetatable(instance, self)
    self.__index = self
    return instance
end

-- Methods
function Person:greet()
    return "Hello, my name is " .. self.name
end

function Person:birthday()
    self.age = self.age + 1
    return self.age
end

-- Create instances
local john = Person:new("John", 30)
local jane = Person:new("Jane", 25)

print(john:greet())  -- "Hello, my name is John"
print(jane:greet())  -- "Hello, my name is Jane"
```

### Methods

```lua
-- Adding methods to an existing "class"
function Person:introduce()
    return self.name .. ", " .. self.age .. " years old"
end

-- Instance methods vs class methods
function Person.isAdult(age)  -- Class method (dot notation)
    return age >= 18
end

function Person:canRetire()   -- Instance method (colon notation)
    return self.age >= 65
end

-- Using the methods
print(Person.isAdult(30))     -- true
print(john:canRetire())       -- false
```

### Inheritance

```lua
-- Base class
local Animal = {}

function Animal:new(name)
    local instance = {name = name}
    setmetatable(instance, self)
    self.__index = self
    return instance
end

function Animal:speak()
    return "Animal sound"
end

-- Derived class
local Dog = Animal:new()  -- Create Dog as an instance of Animal

function Dog:new(name, breed)
    local instance = Animal:new(name)  -- Call base constructor
    instance.breed = breed
    setmetatable(instance, self)
    self.__index = self
    return instance
end

function Dog:speak()  -- Override method
    return "Woof!"
end

-- Create an instance
local rex = Dog:new("Rex", "German Shepherd")
print(rex:speak())  -- "Woof!"
```

### Multiple Inheritance

```lua
function createClass(...)
    local baseClasses = {...}
    local class = {}
    
    -- Create a search metamethod that looks in all base classes
    class.__index = function(instance, key)
        for _, baseClass in ipairs(baseClasses) do
            local value = baseClass[key]
            if value ~= nil then
                return value
            end
        end
        return class[key]
    end
    
    function class:new(...)
        local instance = {}
        setmetatable(instance, {__index = class.__index})
        if class.init then
            class.init(instance, ...)
        end
        return instance
    end
    
    return class
end

-- Example classes
local Flyer = {fly = function() return "Flying" end}
local Swimmer = {swim = function() return "Swimming" end}

-- Multiple inheritance
local FlyingFish = createClass(Flyer, Swimmer)
function FlyingFish.init(self, name)
    self.name = name
end

local fish = FlyingFish:new("Finley")
print(fish:fly())   -- "Flying"
print(fish:swim())  -- "Swimming"
```

### Privacy and Encapsulation

Lua doesn't have built-in private members, but there are conventions and patterns:

```lua
-- Using local variables for privacy
function createPerson(name, age)
    -- Private variables
    local private = {
        age = age,
        secretCount = 0
    }
    
    -- Public interface
    return {
        name = name,
        
        greet = function()
            return "Hello, I'm " .. name
        end,
        
        getAge = function()
            return private.age
        end,
        
        birthday = function()
            private.age = private.age + 1
            private.secretCount = private.secretCount + 1
            return private.age
        end
    }
end

local john = createPerson("John", 30)
print(john.name)      -- "John"
print(john:getAge())  -- 30
print(john:birthday()) -- 31
print(john.age)       -- nil (private)
print(john.secretCount) -- nil (private)
```

### OOP Design Patterns

#### Factory Pattern

```lua
local ShapeFactory = {}

function ShapeFactory.createCircle(radius)
    return {
        radius = radius,
        area = function(self)
            return math.pi * self.radius * self.radius
        end
    }
end

function ShapeFactory.createRectangle(width, height)
    return {
        width = width,
        height = height,
        area = function(self)
            return self.width * self.height
        end
    }
end

local circle = ShapeFactory.createCircle(5)
local rectangle = ShapeFactory.createRectangle(4, 6)

print(circle:area())     -- ~78.54
print(rectangle:area())  -- 24
```

#### Observer Pattern

```lua
local Subject = {}

function Subject:new()
    local instance = {observers = {}}
    setmetatable(instance, self)
    self.__index = self
    return instance
end

function Subject:addObserver(observer)
    table.insert(self.observers, observer)
end

function Subject:removeObserver(observer)
    for i, obs in ipairs(self.observers) do
        if obs == observer then
            table.remove(self.observers, i)
            break
        end
    end
end

function Subject:notify(...)
    for _, observer in ipairs(self.observers) do
        observer:update(...)
    end
end

-- Example usage
local WeatherStation = Subject:new()

local Display = {}
function Display:new()
    return {
        update = function(self, temp, humidity)
            print("Temperature: " .. temp .. "°C, Humidity: " .. humidity .. "%")
        end
    }
end

local mainDisplay = Display:new()
WeatherStation:addObserver(mainDisplay)
WeatherStation:notify(22.5, 65)  -- Triggers update
```

## Modules and Packages

### Creating Modules

A module is a file that exports a table of functions and variables.

Example module file `mymath.lua`:

```lua
-- Define the module table
local mymath = {}

-- Public functions
function mymath.add(a, b)
    return a + b
end

function mymath.subtract(a, b)
    return a - b
end

-- Private function
local function isNumber(x)
    return type(x) == "number"
end

-- Function that uses private functionality
function mymath.safeAdd(a, b)
    if isNumber(a) and isNumber(b) then
        return a + b
    else
        error("Both arguments must be numbers")
    end
end

-- Return the module table
return mymath
```

### Loading Modules

```lua
-- Import the module
local mymath = require("mymath")

-- Use the module's functions
print(mymath.add(5, 3))      -- 8
print(mymath.subtract(5, 3)) -- 2
```

Lua's module search path is stored in `package.path`. It includes the current directory and directories listed in the `LUA_PATH` environment variable.

### Module Patterns

#### Basic Return Pattern

```lua
-- module.lua
local module = {}

function module.foo()
    return "foo"
end

return module
```

#### Local Module Pattern

For better performance, especially with many accesses to module functions:

```lua
-- module.lua
local module = {}

-- Local references to avoid table lookups
local math_floor = math.floor
local string_format = string.format

function module.formatNumber(num)
    return string_format("%.2f", math_floor(num * 100) / 100)
end

return module
```

#### Environment-based Pattern (Lua 5.1)

```lua
-- module.lua
module("mymodule", package.seeall)

function foo()
    return "foo"
end

-- Use with: require("mymodule"), then mymodule.foo()
```

### Standard Modules

Lua comes with several standard modules:

- `string`: String manipulation
- `table`: Table manipulation
- `math`: Mathematical functions
- `io`: Input/output operations
- `os`: Operating system facilities
- `debug`: Debugging facilities
- `coroutine`: Coroutine operations
- `package`: Package loading
- `utf8`: UTF-8 support (Lua 5.3+)

### LuaRocks Package Manager

LuaRocks is the package manager for Lua modules:

```bash
# Install LuaRocks
# On Debian/Ubuntu
sudo apt-get install luarocks

# Install a package
luarocks install luasocket

# Use an installed package
local socket = require("socket")
```

Popular Lua packages:

- `luasocket`: Network support
- `luafilesystem`: File system operations
- `penlight`: Extended standard library
- `luasql`: Database connectivity
- `lua-cjson`: JSON encoding/decoding
- `middleclass`: Object-oriented programming

## Error Handling

### Error Generation

```lua
-- Generate an error
error("Something went wrong")

-- Conditionally generate an error
if not file then
    error("File could not be opened", 2)  -- 2 is the error level
end
```

### Error Catching

```lua
-- Basic error handling
local status, result = pcall(function()
    return 10 / 0  -- Will cause an error
end)

if status then
    print("Success:", result)
else
    print("Error:", result)  -- "Error: attempt to divide by zero"
end

-- Handling errors in loaded code
local status, err = pcall(require, "non_existent_module")
if not status then
    print("Failed to load module:", err)
end
```

### Assertions

```lua
-- Assert will error if the condition is false
function divide(a, b)
    assert(b ~= 0, "Cannot divide by zero")
    return a / b
end

-- Usage
local result = divide(10, 2)  -- 5
local result = divide(10, 0)  -- Error: Cannot divide by zero
```

### Error Messages

```lua
-- Creating descriptive error messages
function processUser(user)
    if not user then
        error("processUser: user parameter is required", 2)
    end
    
    if not user.name then
        error("processUser: user.name is required", 2)
    end
    
    -- Process user...
end
```

### Traceback

```lua
-- Getting a traceback of the call stack
function errorHandler(err)
    print("Error:", err)
    print(debug.traceback())
    return err
end

local status, result = xpcall(riskyFunction, errorHandler)
```

## Coroutines

### Creating Coroutines

```lua
-- Define a coroutine
co = coroutine.create(function()
    for i = 1, 5 do
        print("Coroutine", i)
        coroutine.yield(i)  -- Pause and return i
    end
    return "completed"
end)
```

### Coroutine States

A coroutine can be in one of these states:

- `"running"`: Currently executing
- `"suspended"`: Paused or not started
- `"normal"`: Not the main coroutine or an error'd coroutine
- `"dead"`: Completed or errored

```lua
-- Check coroutine status
print(coroutine.status(co))  -- "suspended" (initially)
```

### Yielding and Resuming

```lua
-- Start or resume a coroutine
local status, value = coroutine.resume(co)
print(status, value)  -- true 1

-- Check status again
print(coroutine.status(co))  -- "suspended" (after yielding)

-- Resume again
local status, value = coroutine.resume(co)
print(status, value)  -- true 2

-- Complete execution
while coroutine.status(co) ~= "dead" do
    local status, value = coroutine.resume(co)
    print(status, value)
end
```

### Coroutines vs Threads

- Coroutines are cooperative: they yield control voluntarily
- Real threads run concurrently and are preemptively scheduled
- Coroutines don't need synchronization mechanisms
- Coroutines are lightweight compared to threads

### Use Cases

#### Iterators

```lua
function range(start, stop)
    local current = start
    return function()
        local value = current
        if value <= stop then
            current = current + 1
            return value
        end
    end
end

for i in range(1, 5) do
    print(i)  -- Prints 1 to 5
end
```

#### State Machines

```lua
function createStateMachine()
    return coroutine.create(function()
        local state = "initial"
        
        while true do
            if state == "initial" then
                local input = coroutine.yield("In initial state")
                if input == "start" then
                    state = "running"
                end
            elseif state == "running" then
                local input = coroutine.yield("In running state")
                if input == "pause" then
                    state = "paused"
                elseif input == "stop" then
                    state = "stopped"
                end
            elseif state == "paused" then
                local input = coroutine.yield("In paused state")
                if input == "resume" then
                    state = "running"
                elseif input == "stop" then
                    state = "stopped"
                end
            elseif state == "stopped" then
                coroutine.yield("In stopped state")
                break
            end
        end
    end)
end

local machine = createStateMachine()
local _, message = coroutine.resume(machine)
print(message)  -- "In initial state"

_, message = coroutine.resume(machine, "start")
print(message)  -- "In running state"

_, message = coroutine.resume(machine, "pause")
print(message)  -- "In paused state"
```

## File I/O

### Simple I/O Operations

```lua
-- Read from standard input
name = io.read()

-- Write to standard output
io.write("Hello, ", name, "!\n")

-- Read entire file
contents = io.input("file.txt") and io.read("*all")

-- Write to file
io.output("output.txt")
io.write("Writing to a file\n")
io.close()
```

### File Handles

```lua
-- Open a file (mode defaults to "r" for read)
-- Modes:
--   "r": read (default)
--   "w": overwrite or create new
--   "a": append or create new
--   "r+": update existing (read/write)
--   "w+": overwrite and read or create new
--   "a+": append and read or create new
file = io.open("data.txt", "r")

if file then
    -- Read operations
    file:close()
else
    print("Error opening file")
end

-- Write to a file
file = io.open("output.txt", "w")
file:write("Line 1\n")
file:write("Line 2\n")
file:close()
```

### Reading From Files

```lua
file = io.open("data.txt", "r")
if not file then return end

-- Read the entire file
content = file:read("*all")

-- Or read line by line
file:seek("set")  -- Go back to beginning of file
for line in file:lines() do
    print(line)
end

-- Or read chunks
file:seek("set")
chunk = file:read(10)  -- Read 10 characters

file:close()
```

### Writing To Files

```lua
file = io.open("output.txt", "w")
if not file then return end

-- Write strings
file:write("Hello, World!\n")

-- Write formatted output
file:write(string.format("Pi = %.4f\n", math.pi))

-- Flush buffered output
file:flush()

file:close()
```

### File Position

```lua
file = io.open("data.txt", "r+")
if not file then return end

-- Get current position
pos = file:seek()  -- "cur" is default
print("Current position:", pos)

-- Move to beginning of file
file:seek("set", 0)

-- Move to end of file
file:seek("end")

-- Move relative to current position
file:seek("cur", 5)  -- Move 5 characters forward

file:close()
```

### Other File Operations

```lua
-- Check if file exists
function fileExists(path)
    local file = io.open(path, "r")
    if file then
        file:close()
        return true
    end
    return false
end

-- Get file size
function getFileSize(path)
    local file = io.open(path, "r")
    if not file then return nil end
    
    local size = file:seek("end")
    file:close()
    return size
end
```

## Standard Libraries

### String Library

```lua
-- Length
length = string.len("Hello")              -- 5
length = #"Hello"                         -- 5

-- Case conversion
upper = string.upper("Hello")             -- "HELLO"
lower = string.lower("Hello")             -- "hello"

-- Substring
sub = string.sub("Hello, World", 1, 5)    -- "Hello"
sub = string.sub("Hello, World", -5)      -- "World"

-- Find substring
start, end = string.find("Hello, World", "World")  -- 8, 12

-- Replace
newStr = string.gsub("Hello, World", "World", "Lua")  -- "Hello, Lua", 1

-- Pattern matching
for word in string.gmatch("Hello Lua world", "%a+") do
    print(word)  -- "Hello", "Lua", "world"
end

-- Format
formatted = string.format("Name: %s, Age: %d", "John", 30)
```

### Table Library

```lua
-- Array operations
table.insert(t, value)        -- Add to end
table.insert(t, pos, value)   -- Insert at position
value = table.remove(t)       -- Remove from end
value = table.remove(t, pos)  -- Remove from position

-- Sorting
table.sort(t)                 -- Default sort (ascending)
table.sort(t, function(a, b)  -- Custom comparator
    return a > b              -- Descending order
end)

-- Concatenation
str = table.concat({"a", "b", "c"})       -- "abc"
str = table.concat({"a", "b", "c"}, ", ") -- "a, b, c"

-- Packing/unpacking (Lua 5.2+)
args = table.pack(...)               -- Create table with arguments
a, b, c = table.unpack({1, 2, 3})    -- Unpack table to variables
```

### Math Library

```lua
-- Constants
pi = math.pi           -- 3.1415926535898
huge = math.huge       -- Infinity

-- Basic functions
abs = math.abs(-10)    -- 10
floor = math.floor(3.7)  -- 3
ceil = math.ceil(3.3)   -- 4
max = math.max(5, 10)  -- 10
min = math.min(5, 10)  -- 5

-- Trigonometry (in radians)
sin = math.sin(math.pi/2)  -- 1
cos = math.cos(0)          -- 1
tan = math.tan(math.pi/4)  -- 1

-- Powers and logarithms
sqrt = math.sqrt(16)       -- 4
pow = math.pow(2, 3)       -- 8
exp = math.exp(1)          -- 2.718...
log = math.log(10)         -- 2.302... (natural log)
log10 = math.log10(100)    -- 2

-- Random numbers
math.randomseed(os.time())
random = math.random()     -- 0.0 to 1.0
random = math.random(10)   -- 1 to 10
random = math.random(1, 100)  -- 1 to 100

-- Angle conversion
rad = math.rad(180)        -- Convert degrees to radians
deg = math.deg(math.pi)    -- Convert radians to degrees
```

### IO Library

```lua
-- Standard input/output
io.write("Enter name: ")
name = io.read()

-- File operations
file = io.open("data.txt", "r")
content = file:read("*all")
file:close()

-- Setting default input/output
oldInput = io.input()  -- Save current
io.input("data.txt")   -- Set new default input
line = io.read()       -- Read from data.txt
io.input(oldInput)     -- Restore original

-- Temporary files
temp = io.tmpfile()
temp:write("Temporary data")
temp:seek("set")
content = temp:read("*all")
temp:close()
```

### OS Library

```lua
-- Time and date
timestamp = os.time()                      -- Current time (seconds since epoch)
date = os.date("%Y-%m-%d %H:%M:%S")        -- Format current time
date = os.date("*t")                       -- Table with date/time components

-- System operations
os.exit(0)                                 -- Exit with status code
os.getenv("HOME")                          -- Get environment variable
os.execute("ls -l")                        -- Execute shell command
os.remove("file.txt")                      -- Delete file
os.rename("old.txt", "new.txt")            -- Rename file

-- Time measurement
start = os.clock()
-- Do something...
elapsed = os.clock() - start               -- Seconds of CPU time
```

### Debug Library

```lua
-- Trace and backtrace
function trace()
    print(debug.traceback())
end

-- Get information about a function
info = debug.getinfo(func)

-- Access local variables
function debugLocals()
    local i = 1
    while true do
        local name, value = debug.getlocal(2, i)
        if not name then break end
        print(name, value)
        i = i + 1
    end
end

-- Hooks
debug.sethook(function(event)
    print("Hook:", event)
end, "cr")  -- Called on function calls and returns
```

### UTF-8 Library

Available in Lua 5.3+:

```lua
-- Check if string is valid UTF-8
valid = utf8.len("Hello")  -- 5
valid = utf8.len("こんにちは")  -- 5

-- Get unicode code point
for i, c in utf8.codes("こんにちは") do
    print(i, c)
end

-- Get character at a position
char = utf8.char(0x3053)  -- "こ"

-- Get offset of character at given position
offset = utf8.offset("こんにちは", 3)
```

## Advanced Topics

### Garbage Collection

Lua uses automatic garbage collection:

```lua
-- Force garbage collection
collectgarbage()

-- Control garbage collection
collectgarbage("stop")  -- Stop automatic collection
collectgarbage("restart")  -- Restart automatic collection
collectgarbage("collect")  -- Perform a full collection cycle

-- Get memory usage (in Kbytes)
usage = collectgarbage("count")

-- Set garbage collection parameters
collectgarbage("setpause", 200)  -- Set pause between cycles
collectgarbage("setstepmul", 200)  -- Set collection speed
```

### Weak References

Weak tables allow objects to be collected if there are no other references:

```lua
-- Weak keys
weakKeys = setmetatable({}, {__mode = "k"})

-- Weak values
weakValues = setmetatable({}, {__mode = "v"})

-- Weak keys and values
weak = setmetatable({}, {__mode = "kv"})
```

### Lua C API

For embedding Lua in C applications:

```c
#include <lua.h>
#include <lauxlib.h>
#include <lualib.h>

int main() {
    lua_State *L = luaL_newstate();
    luaL_openlibs(L);
    
    // Execute Lua code
    luaL_dostring(L, "print('Hello from Lua!')");
    
    // Call Lua function from C
    lua_getglobal(L, "math");
    lua_getfield(L, -1, "sin");
    lua_pushnumber(L, 1.0);
    lua_call(L, 1, 1);
    double result = lua_tonumber(L, -1);
    printf("sin(1) = %f\n", result);
    
    lua_close(L);
    return 0;
}
```

### Performance Optimization

```lua
-- Local references for frequently used globals
local floor = math.floor
local insert = table.insert

-- Precompute expensive operations
local lookup = {}
for i = 1, 1000 do
    lookup[i] = math.sqrt(i)
end

-- Avoid table creation in loops
local results = {}
for i = 1, 1000 do
    results[i] = i * i
end

-- Use appropriate data structures
local set = {}  -- Use table as a set
for _, v in ipairs(values) do
    set[v] = true
end
```

### JIT Compilation

LuaJIT is a Just-In-Time compiler for Lua:

```lua
-- LuaJIT-specific features
local ffi = require("ffi")

ffi.cdef[[
int printf(const char *fmt, ...);
]]

ffi.C.printf("Hello, %s!\n", "world")
```

### Embedding Lua

Integrating Lua into applications:

- Game engines (e.g., World of Warcraft, Roblox)
- Text editors (e.g., Neovim)
- Web servers (e.g., Nginx with OpenResty)
- Database systems (e.g., Redis)
- Graphics applications (e.g., Adobe Lightroom)

## Best Practices

### Code Style

```lua
-- Naming conventions
local MAX_USERS = 100                 -- Constants in uppercase
local UserManager = {}                -- Types/classes in CamelCase
local function calculateTotal(items)  -- Functions in camelCase
    local itemCount = #items          -- Variables in camelCase
end

-- Indentation: Use spaces (2 or 4) or tabs consistently
if condition then
    doSomething()
end

-- Line length: Keep lines under 80-100 characters
-- Comment style:
-- Single-line comments above code they describe
-- Avoid end-of-line comments except for simple clarifications
```

### Memory Management

```lua
-- Reuse tables instead of creating new ones
local buffer = {}
function processData(data)
    for i = 1, #data do
        buffer[i] = process(data[i])
    end
    return buffer
end

-- Localize global variables in functions
local function processString(str)
    local string_find = string.find
    local result = {}
    -- Use string_find instead of string.find
end

-- Pre-allocate tables when size is known
local large = {}
for i = 1, 10000 do
    large[i] = i
end
```

### Error Handling

```lua
-- Always check file operations
local file = io.open("data.txt", "r")
if not file then
    return nil, "Could not open file"
end

-- Use pcall for operations that might fail
local status, result = pcall(json.decode, rawData)
if not status then
    return nil, "Invalid JSON: " .. result
end

-- Propagate errors with details
function processFile(filename)
    local file = io.open(filename, "r")
    if not file then
        return nil, "Could not open file: " .. filename
    end
    
    local content = file:read("*all")
    file:close()
    
    if #content == 0 then
        return nil, "File is empty: " .. filename
    end
    
    return content
end

-- Usage
local content, err = processFile("data.txt")
if not content then
    print("Error:", err)
    return
end
```

### Testing

```lua
-- Simple test framework
local tests = {}

function tests.testAddition()
    assert(add(2, 3) == 5, "Addition failed")
end

function tests.testSubtraction()
    assert(subtract(5, 3) == 2, "Subtraction failed")
end

-- Run all tests
local passed = 0
local failed = 0
for name, testFunc in pairs(tests) do
    local status, err = pcall(testFunc)
    if status then
        passed = passed + 1
        print(name .. ": PASS")
    else
        failed = failed + 1
        print(name .. ": FAIL - " .. err)
    end
end

print(string.format("Results: %d passed, %d failed", passed, failed))
```

### Documentation

```lua
--- Add two numbers together.
-- @param a The first number.
-- @param b The second number.
-- @return The sum of a and b.
function add(a, b)
    return a + b
end

--- Calculate the area of a circle.
-- @param radius The radius of the circle.
-- @return The area of the circle.
-- @usage
-- local area = calculateCircleArea(5)
-- print(area)  -- Prints 78.53981633974483
function calculateCircleArea(radius)
    return math.pi * radius * radius
end
```

## Resources

### Official Documentation

- [Lua.org](https://www.lua.org/): Official website
- [Lua 5.4 Reference Manual](https://www.lua.org/manual/5.4/): Complete language reference
- [Lua-Users Wiki](http://lua-users.org/wiki/): Community-driven documentation

### Books

- "Programming in Lua" by Roberto Ierusalimschy (creator of Lua)
- "Lua Programming Gems" edited by Luiz Henrique de Figueiredo
- "Game Development with Lua" by Paul Schuytema and Mark Manyen
- "Beginning Lua Programming" by Kurt Jung and Aaron Brown

### Community

- [Lua Mailing List](http://www.lua.org/lua-l.html): Official discussion forum
- [Lua on Stack Overflow](https://stackoverflow.com/questions/tagged/lua): Q&A
- [Lua on Reddit](https://www.reddit.com/r/lua/): Discussion forum
- [Lua Discord Server](https://discord.gg/lua): Real-time chat

### Tools

- [LuaRocks](https://luarocks.org/): Package manager
- [ZeroBrane Studio](https://studio.zerobrane.com/): Lua IDE
- [Busted](https://olivinelabs.com/busted/): Testing framework
- [LuaCheck](https://github.com/mpeterv/luacheck): Linting tool
- [LDoc](https://github.com/stevedonovan/LDoc): Documentation generator
- [LuaJIT](https://luajit.org/): Just-In-Time compiler for Lua
