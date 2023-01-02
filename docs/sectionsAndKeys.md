---
hide:
  - footer
title: "Sections and Keys"
---

# Sections and Keys. Where are the doors?
Before moving further, there's something very important you should know about YAML. How it's *organised*. YAML is organised into two things. Sections, and keys. It is vital that you know what each one is and how each one can be useful.

## Sections
Sections are what hold keys. Sections can arrange keys and will help configuration files stay neatly sorted out. Take a look down below to see what a section can do.

```yaml
example: #This is a section. This will store keys!
  longbow: 49 #This is a key!
example2: #This is another section, helping keep things of different categories arranged.
  bowlong: 55 #This is a key!
```
Do you see how this works? Simple, right? Developers will use this when they have configuration options that belong in two different categories. Sorting them out like this will save you a lot of time, and it means you can keep things nice and tidy. When using YAML, tidiness is always very important.

## Keys
Keys are what hold values. Keys are normally what you would edit to change the value of something. If you've ever worked with any programming language before, you should know what a variable is, if not, it's worth taking a little look at my lesson on variables [here](https://github.com/longbow122/learnerForYAML/wiki/Variables). Keys hold values, and developers will assign these to certain variables to make things in their plugin work a certain way. What does this mean for server owners? It means keys, essentially hold each important configuration option in your server. An easy way to identify a key from a section is that a key will ALWAYS have a value assigned to it. If you think it's a key, but it has no value, it would be a section. And what holds keys? Sections. They all link together, all being equally important. Take a look down below to look at an example of keys: (Hint: You've already seen them!)

```yaml
example: #This is a section!
  longbow: 49 #This is a key! This would store a value for something, which you can make use of.
moneyOnJoin: #This is a section from a (fake) configuration file from a (fake) plugin. This plugin will give a certain amount of money to the player upon joining their server.
  money: 500 #This key stores the value of the money to be given. When a player joins, they'll receive $500.
  ```
Do you see how this works? Developers will use keys to store values which they can then access through the code in their plugin. This allows server owners to change these values and customise plugins how they want, to suit their servers.

## No, seriously. Where are the doors?
Want to test what you've just learned? Take a look at the challenge below:

Below this paragraph, I have written out a small (fake) configuration file. Can you identify which is a key and which is a section? (Hint: Keys are what hold values. Values will normally be a variable of a certain type. If a key does not have a value, then it would be a section).
```yaml
a:
  b: 46
  c: "Hello!"
x: 77
y:
  - "Goodbye!"
  - "My friend! See you in another life!"
u:
  longbow: "Did you get them all?"
```

!!! info ""

    *Please note that some information may be wrong in this wiki, and I have done my best to ensure whatever has been written is correct. This was written in British English (with the odd oxford comma). If you believe there is a spelling, grammatical, or technical error, please contact me immediately through Discord:* ***longbow122#1576***