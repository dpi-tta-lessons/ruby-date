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
```
{: .repl }

## What Is the `Date` Class?

Before diving in, let's connect this to object-oriented programming (OOP). A class is like a blueprint. An object is a specific instance made from that blueprint. Ruby's `Date` class is a blueprint for creating date objects. These objects come with methods you can call to manipulate them.

## Core vs Standard Library

Ruby has core classes like `String`, `Array`, and `Integer`. The `Date` class is part of Ruby's [Standard Library](https://docs.ruby-lang.org/en/master/standard_library_md.html), not Core. This means you need to explicitly *require* it.

```ruby
require 'date'
```
{: .repl }

When you use `require` you're telling Ruby, "Please load the extra code from the date library so I can use the `Date` class and all its methods." If you forget, Ruby will throw an error saying it doesn't know what `Date` is.

## Creating Date Objects

Get today's date by calling the class method `Date.today`.

```ruby
require 'date'
today = Date.today
puts today
```
{: .repl }

Create a specific date by calling `Date.new` and passing in the integers for year, month, and day.

```ruby
usa_birthday = Date.new(1776, 7, 4)

# 1776-7-4
puts usa_birthday
```
{: .repl }

## Formatting Dates

You can format a date into human-friendly strings using the method [strftime](https://docs.ruby-lang.org/en/master/Date.html#method-i-strftime).

```ruby
today = Date.today
puts today.strftime("%B %d, %Y")
puts today.strftime("%m/%d/%Y")
```
{: .repl }

<aside class="tip">
  <code>%B</code> is the full month name, <code>%d</code> is the day, and <code>%Y</code> is the four-digit year.
</aside>

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
deadline = Date.new(2024, 12, 31)

# true
puts today > deadline

# false
puts today == deadline
```
{: .repl }

## A Quick Word About Time, DateTime, and Time Zones

So far, we've only worked with calendar dates. But in the real world, you often need to keep track of hours, minutes, seconds, and even time zones. Ruby has a few different classes to help with this:

### Time

The [Time](https://docs.ruby-lang.org/en/master/Time.html) class is built into Ruby (no require needed). It handles both the date and the clock time. It also knows about your computer's time zone.

```ruby
now = Time.now
puts now
```
{: .repl}

Notice the number at the end, that's the time zone offset from UTC.

### DateTime

[DateTime](https://docs.ruby-lang.org/en/master/DateTime.html) is similar to [Date](https://docs.ruby-lang.org/en/master/Date.html), but it also includes hours, minutes, and seconds. Unlike [Time](https://docs.ruby-lang.org/en/master/Time.html), it comes from the standard library, so you must `require "date"` to use it.

```ruby
require "date"

dt = DateTime.now
puts dt
```
{: .repl }

<aside class="tip">
  See the T between the date and time? That's an ISO 8601 format, which is commonly used in APIs and databases.
</aside>

### Time Zones

Time zones are tricky. Ruby's Time objects are usually in either your computer's local time, or UTC (Coordinated Universal Time). For most everyday scripts, you can stick with `Time.now`.

<aside class="tip">
  Use <code>Time</code> or <code>DateTime</code> when you need to track <strong>hours, minutes, and seconds</strong> — not just calendar dates.
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

## Project: Date

In this project, you will write Ruby programs that leverage these date methods. This project includes automated tests, so click this link to get started <https://github.com/dpi-tta-projects/ruby-date/fork>, fork the repository and create a codespace.

<aside class="warning">
  In order to get credit for completing this project you'll need to open the assignment link from canvas to generate an access token.
</aside>

## References

- Ruby Docs: [Date](https://docs.ruby-lang.org/en/master/Date.html)
- [strftime format cheatsheet](https://devhints.io/strftime)
