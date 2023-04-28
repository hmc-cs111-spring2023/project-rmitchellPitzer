# Design notebook entry

## Last week's critique

**TODO:** Fill in this part with a summary and reflection on the critique you received for
last week's work. Answer questions such as:  How, specifically, did the feedback help
improve the project? Did the feedback point out or offer something you hadn't considered?
Did it help you make a design decision? Was it helpful in addressing the most pressing
issues in your project? How will you incorporate the feedback into your work? Will you
change something about the design, implementation, or evaluation as a result?




I think I made a lot of progress this week on starting the project and have some ideas of where to start!
	The feedback received in bullet points is as follows:
- It’s best to use a library if it exists for the host language being used.
- Both Python and Java have libraries that will be useful
- There are still questions about how the schedule will be visualized, not only in what file type and format but how the user will see the calendar (daily, weekly, monthly?”
- Sounds very extreme, but can be exactly what some niche users are looking for. 
- Should focus on efficiency instead of features.
- Choices can be made to skew towards language design vs systems design.
- PyQt in Python is a free and simple way to make a GUI that can be used for a frontend.
- The frontend doesn’t have to look ridiculously professional.
- Plan is a nice balance of knowing what milestones to complete, while also having some flexibility if you need it. 
- Between Python, Scala, and Rust, Python will most likely give the best balance of language design and systems design.

Some of this feedback has already been considered and will be used when building the project in week 2. For instance, Python will be used instead of Scala as the host language. This ensures that libraries exist that will offset much of the systems design work and balance the project towards language design. This also allows in the future for the development of a frontend, which will most likely use PyQt or Tkinter, which was recommended in feedback. I had originally considered a desktop app using a mix of Javascript/Rust purely because that’s what I already have experience with, but from feedback I decided it wasn’t worth complicating every aspect of the project just to have a slightly prettier frontend. 99%, if not 100%, of what I would want to do in Javascript/Rust would also be possible using Python.  
	Something I hadn’t considered in detail is how the calendar/schedule will be visualized. I had assumed that it could look something similar to Google Calendar/Apple calendar, but people use calendars in different ways and one might want to view their schedule for the day or for the week/month. For this reason, the output file to visualize the schedule will be a .csv file.





## Description

**TODO:** Fill in this part with information about your work this week:
important design decisions, changes to previous decisions, open questions,
exciting milestones, preliminary results, etc. Feel free to include images
(e.g., a sketch of the design or a screenshot of a running program), links to
code, and any other resources that you think will help clearly convey your
design process.




This week I made a goal to:
- Investigate benefits and tradeoffs between host languages, and determine whether an external/internal implementation will work best. 
Finalize the syntax/language design knowing this. 
- Decide on a general architecture/structure of the DSL
- Understand how an iCalendar file could be output using a language, whether through writing to a file manually or by using libraries in the host language.

Fortunately, each of these goals has been completed! After considering each possible host language and their benefits and drawbacks, I settled on Python as a host language. I already have experience with Python and many of its libraries, so I feel that offsetting some of the work for parser combinators/CSV/frontend applications will give me more time for language design and balance the project more. Python also has support from many libraries, such as CSV https://docs.python.org/3/library/csv.html , ICalendar parser/generator https://pypi.org/project/icalendar/ , Parsec which is a parser combinator library in Python https://pythonhosted.org/parsec/ , and for the frontend stretch goal either Tkinter or PyQt could be used https://docs.python.org/3/library/tkinter.html https://wiki.python.org/moin/PyQt . 
	As for external or internal DSL, I decided to go with an external approach. One of my goals for this project was to learn more about parser combinators and to learn how to transfer my knowledge of DSL’s from Scala to other languages. Using an external implementation in Python will allow for this.
	The idea syntax has also already been decided. Users will either have the option to use syntax similar to natural language used in other DSL’s, or to optimize for efficiency and time, barely any syntax. This ideally would look similar to:
NEW EVENT “CS111” WITH DESCRIPTION “My course for domain specific languages in Shanahan 2465.” ON MONDAY WEDNESDAY FROM 1:15PM TO 2:30PM 
“CS111” “My course for domain specific languages in Shanahan 2465.” M W 13:15 14:30
I’ve also decided on a general architecture/structure of the DSL. I plan to have two DSL’s, one for parsing user input and another for parsing the output of the first DSL. The first DSL will take in lines of user input similar to the ideal syntax described above, and compile a .ics file using Python’s Icalendar library. This could then be passed to the second DSL, which will parse Icalendar files from the first DSL and create an excel file which could then be used to view daily/weekly events. 
	As for how I plan to output an Icalendar file and visualize the schedule, this will be done by using Python’s libraries. The schedule could then be viewed in the output .ics file.




## Questions

**What is the most pressing issue for your project? What design decision do
you need to make, what implementation issue are you trying to solve, or how
are you evaluating your design and implementation?**




The most pressing issue for my project currently is probably learning how to implement the libraries listed above in the DSL. My plan for week 2 vaguely referenced parsing user input and implementing the syntax for the user. This means I’ll have to learn how to implement Parsec in a way that would make sense for the users and would best represent the ideal syntax shown above. I also plan to think more about the limited featureset of this schedule maker compared to other schedule makers, as I feel I might need to introduce more features so that it is usable. 



**What questions do you have for your critique partners? How can they best help
you?**



No questions so far for my critique partners, thank you for the PyQt recommendation! 


**How much time did you spend on the project this week? If you're working in a
team, how did you share the work?**



I spent roughly 2-3 hours this week on the project. Much of this time was spent in class or writing out this notebook.



**Compared to what you wrote in your contract about what you want to get out of this
project, how did this week go?**



This week went really well! I am turning this in somewhat late due to other commitments, but this sounds like a great starting point for this project and I’m excited for week 2! 
