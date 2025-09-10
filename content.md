# Ruby Date

Learn how to work with dates in Ruby and get a quick peek at times, datetimes, and time zones.

## Goal

By the end of this lesson, you'll be able to create, manipulate, format, and compare dates in Ruby using the built-in [Date class](https://docs.ruby-lang.org/en/master/Date.html).

## What You'll Build

Today, you'll write Ruby code that:

- Creates a `Date` object
- Formats it into different styles
- Performs calculations (like "yesterday" or "next week")
- Compares two dates

## Quick Demo

Here's a sneak peek at what you'll be able to do:

```ruby
require 'date'

today = Date.today
puts "Today: #{today}"

next_week = today + 7
puts "Next week: #{next_week}"

birthday = Date.new(2025, 9, 10)
puts "Birthday: #{birthday.strftime("%B %d, %Y")}"

puts "Is today my birthday? #{today == birthday}"
```
{: .repl }

Output:

```
Today: 2025-09-10
Next week: 2025-09-17
Birthday: September 10, 2025
Is today my birthday? false
```

## What Is the `Date` Class?

Before diving in, let's connect this to object-oriented programming (OOP). A class is like a blueprint. An object is a specific instance made from that blueprint. Ruby's `Date` class is a blueprint for creating date objects. These objects come with methods you can call to manipulate them.

<aside class="tip">
  In Ruby, almost everything is an object—including numbers, strings, and dates.
</aside>

## Core vs Standard Library

Ruby has core classes like `String`, `Array`, and `Integer`. The `Date` class is part of Ruby's standard library, not core. This means you need to explicitly require it:

```ruby
require 'date'
```
{: .repl }

If you forget, Ruby will throw an error saying it doesn't know what Date is.

## Creating Date Objects

Get today's date:

```ruby
require 'date'
today = Date.today
puts today
```
{: .repl }

Output: `2025-09-10`

Create a specific date:

```ruby
usa_birthday = Date.new(1776, 7, 4)

# 1776-7-4
puts usa_birthday
```
{: .repl }

<aside class="warning">
  The order is <code>year, month, day</code>. Mixing it up is a common mistake!
</aside>

## Formatting Dates

You can format a date into human-friendly strings using `.strftime`.

```ruby
today = Date.today
puts today.strftime("%B %d, %Y")
puts today.strftime("%m/%d/%Y")
```
{: .repl }

<aside class="tip">
<strong>Tip:</strong> <code>%B</code> is the full month name, <code>%d</code> is the day, and <code>%Y</code> is the four-digit year. </aside>

## Date Arithmetic

You can add or subtract days directly with `+` and `-`.

```ruby
today = Date.today

# Yesterday
puts today - 1

# 30 days later
puts today + 30
```
{: .repl }

## Comparing Dates

Dates can be compared using standard comparison operators.

```ruby
today = Date.today
deadline = Date.new(2025, 12, 31)

# true
puts today < deadline

# false
puts today == deadline
```
{: .repl }

## A Quick Word About Time, DateTime, and Time Zones

So far we've worked with just dates. But in the real world, you often need times of day and time zones too. Ruby provides other classes for this:

### Time

built-in, handles both date and clock time (e.g., 2025-09-10 14:35:00).

### DateTime

like Date but also includes times; comes from the same standard library as Date.

### Time Zones

Ruby's Time objects are usually set to your system's local time or UTC. Libraries like ActiveSupport (from Rails) make handling zones easier.

Here's a quick peek:

```ruby
now = Time.now
puts now   # 2025-09-10 14:35:12 -0400 (includes time + offset)

dt = DateTime.now
puts dt    # 2025-09-10T14:35:12+00:00
```
{: .repl }

<aside class="tip">
  You'll use <code>Time</code> or <code>DateTime</code> when you need to track hours, minutes, and seconds, not just calendar dates.
</aside>

## Wrap-Up

The Date class lets you create, format, calculate, and compare dates. It's part of Ruby's standard library, so don't forget `require 'date'`. Dates behave like other Ruby objects, you call methods on them to get things done.

## Quiz

- What must you do before using the Date class in Ruby?
- Nothing, it's built into the core.
  - Not quite! It's not a core class.
- Run require 'date' at the top of your file.
  - Correct! You must load it from the standard library.
- Import date.rb manually from Ruby's source code.
  - Not correct—Ruby handles that when you require it.
{: .choose_best #require_date title="Using Date Class" answer="2"}
