# Design notebook entry

## Last week's critique

This week I focused on finishing the first DSL/the first parser. Taking in feedback, I took Gabriel's feedback and instead of writing the calendar, then reading it, then altering it and writing it again, I just alter the calendar when it's made using the .ics library, then write that to file.
Unfortunately, I can't find when using the .ics library when I could write a rrule for each event.
I also looked at the recurring ical events library, and while that would be a good alternative to use, I feel I already have rrule done, and it isn't a overly complex solution, so I'm just continuing using what I have right now. 

## Description

This week I got a lot done! I implemented the start time/end time based on the current date/time and what day an event occurs. That way, a user could input in a weekday, and it could output a weekly calendar that could also be imported to Google Calendar/Apple calendar and be used.
I also added the natural-language-less syntax, so instead of saying 
EVENT "CS111" DESC "Domain Specific Languages. Occurs ever Monday and Wednesday from 1:15 pm to 2:30 pm." FROM 1:15pm TO 2:30pm ON Monday Wednesday Friday COLOR orange
users can now say:
"CS111" "Domain Specific Languages. Occurs ever Monday and Wednesday from 1:15 pm to 2:30 pm." 1:15pm 2:30pm Monday Wednesday Friday orange

There were a couple problems with this approach:
- One such problem was how to account for differences in time, like if the input string is "12:30pm" or "1:30pm" or "01:30pm" in the NL-less syntax. 
I solved this by finding the index of ":", then just inputing the time found for that. 
Another problem was when finding the color and the days. For instance, if the last part of the input is 
"M W F Yellow"
then checking if W is in the input will remove W from the input, and add it to the list of days to occur on. So the final output for checking when days occur becomes
listOfDays = [M, W, F]
Color = "Yello"
To fix this, I used a fixed list of colors based on the Google Calendar labels. I might revist this and add support for basic colors, that way the day strings don't interferre with the color.
I also implemented RRULE support, so a event is now able to occur every week.

Overall I'm very close to finishing the first DSL, and I suspect the second part will be easier to complete due to the format of .ics files and due to being delimited by newlines.

I also added color support, although I suspect these labels aren't supported by google calendar and apple calendar due to the way their api works. By default it is light blue, but I can append the color to the end of the uid, and that should mean when I parse the .ics file for the HTML visualization, then it should display colors correctly.

## Questions

Right now the most pressing issue is probably how many error messages I want. While there are already error messages for many parts of the DSL, I wonder how I should handle error messages for the natural-language-less syntax, or if Python will handle that for me. It would be the difference between:
"Error: key error "CS111"" 
and
"ERROR: Can not find an event in the input"

I'm also worried about the colors, as I still need to find a way for it to work with Google Calendar/Apple Calendar.

My most pressing question is: Should the preview show the colors the user inputs, or should colors be scrapped entirely? If the colors aren't visible when imported to a calendar app, and default to light blue, is it misleading to have it be present when visualized in a html file?

I probably spent ~12 hours working on this this week.

This week I feel I got a lot done! I'm feeling confident that I can get this done by the end of the week. I'm a bit sad I probably won't get to do the application visualization I wanted to do, unless I finish the rest of this really quickly, but I'm still happy with my progress so far!
