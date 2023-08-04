---
hide:
  - footer
title: "Syntax"
---

# Syntax. Juicy.
Like any programming language, everything has a specific syntax, or rules you need to follow when working with YAML. This page will (hopefully) teach you all about the syntax you need to know to be able to use good YAML practice like it's second nature. Firstly, we'll be starting off with a few basic rules for working with YAML. After that, we'll be moving onto variable syntax, so that you can properly declare your variables.

## Indentation
Like most, if not all programming languages, indentation is very important. When copying and pasting, this is something most people will also overlook, so it's always best you manually type everything or just ensure you check your entire file over once you finish the file. When indenting, I like to follow something called the "two-tap" rule. It goes like this: "The deeper you go into a section, indent by two". Since YAML doesn't like the TAB key, you'll have to use the spacebar key for your indentation. This might sound annoying, but it won't be so bad, as long as you remember that **YAML sections and keys should always be indented by a multiple of two**. This sounds confusing at first, but, hopefully with a visual example, it won't be so bad. Take a look:

```yaml
section: #This is a section, this won't be indented, as you don't need to indent for NEW sections. Think of these as parents.
  key: 50 #This is a key, this was "two-tapped" indented in, as it is a part of this section. Think of this as the child.
  section2: #This is a section inside a section, this was "two-tapped" in from the parent section, as it is still part of the original section.
    key2: 'Hello there!' #This is a key, this was "two-tapped" in from its parent section, which is section2. Section2 is a child of section.
newSection: #This was not two-tapped into section, as it is an entirely new section. This does not need to be a child of anything.
  newKey: 'E' #This was two-tapped into newSection, as it needs to be a child of newSection. Without this indentation, YAML wouldn't know that this was a part of newSection. You would also see a YAML error.
```

In this code, do you see where I've needed to use certain sections keys, I've indented those keys into the section it's in? I've also made a section inside a section for you to look at, to show you how the "two-tap" rule would properly apply. Indentation like this is very important in YAML. It can make or break your configurations and can be very hard to find in larger, chunkier files.

## Variable Syntax
Variable what now? That's right, variables also have syntax. As you've seen in previous lessons, keys, or more specifically, their values, have certain syntax, or rules you need to follow when declaring them. In case you didn't know, declaring a variable essentially means you're telling YAML that your value is a variable of a certain type, this is important to learn, as you don't want to confuse a String for an Integer. That, in theory, would cause an error. Since there are different variable types, and each one has a different syntax, I'll be separating each one into a separate explanation.

### Strings
There are two different ways you can declare Strings, which you'll need to know when working with Minecraft plugins. The single quote and the double quote method. We'll be going over both of these methods in this wiki, as they're likely the extent of what you need to use when configuring a Minecraft plugin. Take a look down below:
```yaml
a: 'Hello! This''l look fancy!' #This is the single quote method
b: "Hello! This'll look fancy!" #This is the double quote method
```

As you can see, each has its differences, and both can be used in different ways. This is just a basic example of their differences, take a look down below for a more complicated example:

```yaml
a: 'Hello! This seems to only have ''one'' way to escape characters.'
b: "Hello! This seems to have many patterns you can use. Even \u263a faces!"
```
"\u263a" is actually a smiley face! A double-quoted string can be useful in this way, as they can make use of these patterns. For a more Minecraft-specific use-case, this isn't really needed, the extent of what you'd need would be the single-quoted method of declaring Strings. However, there is one thing you simply must watch out for when using single-quoted String declarations.

```yaml
a: 'Good day to you sir! Wasn't it last Tuesday when I saw you?' #While grammatically correct, YAML will not like this at all! You won't see most of this string printed.
b: 'Good day to you sir! Wasn''t it not last Tuesday when I saw you?' #This will print the entire string, and will work without issues!
```
Strange, isn't it? When using single-quoted string declarations, the character you use is actually an apostrophe. So, when using apostrophes as a part of your string, YAML may think it's the end of your string unless you SHOW YAML that the character there is actually an apostrophe. There's no way to do this other than getting around it, and that's what we call escaping.

Escaping a character essentially means to get around something by using something else. In the case of YAML apostrophes, you'll need to use two apostrophes to have an apostrophe in your sentence. Sound confusing? Take a look below for an example:
```yaml
a: 'I''ve escaped an apostrophe!'
```
This will print **I've escaped an apostrophe!** when returning that value as a String. See how that works? Now take a look at what happens if you use one apostrophe instead of two to declare your String.
```yaml
a: 'I've escaped an apostrophe!'
```
This will either print I when returning that value as a String, or give you an error since you haven't escaped the character, and so, everything after the "I" will not be part of a string, and YAML will trip up. Either way, this is not the result you wanted. This is why it's important to remember to use '' when declaring an apostrophe inside a single-quoted string in YAML.

### Numbers
Phew! Thank god that's over. Now then, onto something a little simpler. Declaring any number is much simpler with YAML. No formatting required! Take a look at the example below:
```yaml
section:
  a: 58 #Two-tapped in, as it is a part of this section! 
newKey: 22.6 #No formatting for any of these numbers, YAML doesn't need them!
anotherNewKey: 4545121212154546789 #Any number, any format, it'll all be detected!
```
Declaring any number is much simpler with YAML, as you can see above. As long as your keys are indented correctly, you won't have any trouble declaring a number as a value with YAML.

### Booleans
Something nice and simple now, aren't you lucky! You should know, that a boolean is a "true" or a "false". Or, a "yes" or a "no". This is the simplest variable type you can use, and its flexibility is infinite. Declaring it in YAML is as easy as it is to use. Just like numbers, no formatting required! Take a look at the example below:
```yaml
boolean1: true #No formatting for any boolean, YAML doesn't need them!
boolean2: false #No matter the boolean, it'll get detected!
```
Declaring any boolean you want (there are only two types of boolean: true, and false!) is easy as that! The simplest declaration for the simplest variable type. Nice and easy!

### String Lists
Buckle up! This one is a little harder! With String lists, while declaring them is definitely very similar to Strings, you'll have to consider that this is still a List. As such, you need to declare it as a list, of Strings. Firstly, you'd declare something as an element (a part of the list) by indenting and hyphenating. Indentation will follow the same two-tap rule you've been following this entire time, so there's nothing to remember there. Once you've indented, all you need to do is add a hyphen, and declare your String like normal. That's what we're going to do here. Take a look at the example down below. Can you see what I've done?
```yaml
stringList: #The start of the stringList. This is still a key! Don't confuse this for a section. The value it holds is the list below.
  - '1' #This is called an "element" of a list.
  - 'A' #You can see that when declaring a StringList item, you need to two-tap indent.
  - 'B' #Once you've two-tapped, you need to declare that this is part of the list. You'd do this by adding a hyphen.
  - 'C' #Once you've added the hyphen, you'll just declare the String like normal. Not so bad, right?
  - 'D' #You can add as many elements to a StringList as you like! 
  - 'E'
```
Not so scary now, huh? As long as you remember to indent, and hyphenate. After all of that, you just need to declare a String like normal. Not so bad.

If you really want to, you can also use a single-lined list. However, this isn't recommended, but has been seen on the rare chance in use by developers for configuration files. These are much simpler than multi-lined lists, as you will soon see.
```yaml
list: ['Hello', 'Hi', 'What''s your name?']
```
See what I've done here? I've listed some single-quoted Strings using commas, and after that, I've simply encased the entire list in a square bracket. This is how you'd declare and use a single-lined StringList.

Additionally, it is also worth noting that you are able to declare an empty list of any type by simply removing all elements from the list, and using an empty set of square brackets. Take a look at the example below:
```yaml
list: []
```

!!! info ""

    It is also worth noting that you can declare a list of any other data type using the same logic shown above. Using this, you could make use of a list of longs, characters, integers, and more!

## Well, this is new.
Want to test what you've just learned? Take a look at the challenge below:

Below this paragraph, I have written out a (fake) configuration file. Can you identify which variable is which from the name of the key and if it's declared incorrectly, can you fix it? (To make things more fun, there are even a few indentation and syntax errors in this file).

```yaml
moneysection:
  moneyonJoin: '1200' #The amount to give as a number
  Should money be given when they join the server?
  shouldGiveMoneyOnJoin:
   - 'true'
  # This will print out a message when the player joins
  messageWhenGiven: 'Congratulations! You've won 1200 dollars!
  soundsToPlay: #This will play sounds when the player joins
      - 'ENTITY_BLOCK_NOISE
      - 'SCREAM'
```

!!! info ""

    *Please note that some information may be wrong in this wiki, and I have done my best to ensure whatever has been written is correct. This was written in British English (with the odd oxford comma). If you believe there is a spelling, grammatical, or technical error, please contact me immediately through Discord:* ***longbow122#1576***