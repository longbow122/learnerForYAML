---
hide:
  - footer
title: "YAML Errors"
---

# Errors. Too erroneous for my liking.
Errors! Disgusting little beasts, but helpful. Sometimes. Hopefully, you'll never need to read this page, as you should know enough to write perfect YAML with ease! But, this information, as always, is good to know for that "just in case" scenario. To help you learn all about YAML errors, we're going to be using a useful tool. I recommend you have this [YAML validator](http://yaml-online-parser.appspot.com/) open as we go along this lesson. Don't worry, it's completely safe.

Take a look at the small (fake) configuration file below:
```yaml
section: #Line 1
  lore: #Line 2
    - 'Hello there!' #Line 3
     - 'What''s this?' #Line 4
```

Can you spot what's wrong with this file? A YAML validator sure can! A YAML validator is very useful in the case where your configuration file could be thousands of lines long. This will help you pinpoint issues with your file much quicker. Now, take a look at the YAML error that is returned when you throw this file into it:
```
ERROR:

while parsing a block collection
  in "<unicode string>", line 3, column 5:
    - 'Hello!'
    ^
expected <block end>, but found '<block sequence start>'
  in "<unicode string>", line 4, column 6:
     - 'E'
     ^
```
This would be highlighted to you in red, normally. Confusing, right? Fortunately, there is information we can pull from this error, to be able to analyse the file itself. Firstly, we'll take a look at the bottom one first, since we know that it's already the problem line. If you count the indentations, you'll see that column 6 is after the hyphen. Looking at this line, we should be able to see that the indentation is off by one. We can fix this by simply removing one space, and lining it up with the rest of the file. Doing so will fix the error. Much bigger files will be more complicated, but a YAML error will always show you which section has the problem line at best. Using this information, you should be able to read your own YAML errors and find out where the problem lies.

**Tip:** Sometimes, a YAML file may be so badly riddled with errors that, when you fix one, you end up causing five different errors. If you ever reach this stage, it may be best to start over. The number one culprit for a file reaching this stage is people copying and pasting repeated sections over and over to make life quicker for them, without paying attention to the formatting itself. Keep in mind that copying and pasting will normally mess up your formatting. If you choose to do this, it's best you do so while checking and correcting the section you've pasted in before copying and pasting again.

!!! info ""

    *Please note that some information may be wrong in this wiki, and I have done my best to ensure whatever has been written is correct. This was written in British English (with the odd oxford comma). If you believe there is a spelling, grammatical, or technical error, please contact me immediately through Discord:* ***longbow122#1576***