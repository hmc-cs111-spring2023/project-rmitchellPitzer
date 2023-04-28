# Design notebook entry

## Last week's critique

This week I worked more on the parser for the DSL. Most of the feedback received was to
use a parsing library such as parsec.py. After talking with professor Wiedermann, I
decided to just use Python's built in string processing. The input being taken in isn't
anything too complex/it doesn't require parser combinators, and I can also throw error
messages in case syntax is missing and point out where an error was thrown. In these
error messages I also give examples of the ideal syntax, that way users are able to
follow along in case the syntax/messaging is vague. 

## Description

This week I worked more on the parser, and I also started work on the .ics library. I
was able to output a .ics calendar using the information a user would save in a file!
Most of the parser and the .ics output is complete, I just need to troubleshoot a bit
more on some things that are giving me problems. I also worked on using the datetime
library so that events could be made using the .ics library.

## Questions

Currently the most pressing issue is the lack of RRULE support in the .ics
library. RRULE allows recurring events in calendars, so an event could occur weekly.
This isn't supported by the .ics library (which has been a feature requested since 2016,
so I doubt it'll be added in soon), so I'm going to try to instead output the .ics file,
open it into python once made as a plain text file, and add the RRULE manually. I
also need to add support for the faster, no natural language syntax I wanted. This should
be easy to do, I just need to change my ideal syntax a bit to have a keyword indicating that
natural language syntax is not being used. 
I also need to get optional descriptions done, so a user could not have a description for an
event, and could still create the event.

**What questions do you have for your critique partners? How can they best help
you?**

Is there a .ics library that supports RRULE in python? Also, if you were working on a
no natural language syntax, how best would you indicate that the natural language syntax
is not being used? Could this be indicated at the input with a keyword like "VERBOSE" or
just without the "EVENT" keyword? 

**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**

I spent ~4 hours on this projec tthis week. I was a bit busy this week with the hackathon/other courses,
so I unfortunately did not get as far as I wanted to on this.

**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**

This week went well! I'm nearly caught up to where I am on the contract, i just have a bit more
work to do this week before I'm fully caught up.
