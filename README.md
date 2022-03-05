# C# / ASP.NET / MVC Live Project Details
Topic: Software to assist end user in managing website content.

### Introduction
I have completed a 2 week sprint in the Software Development Bootcamp through The Tech Academy. I was assigned to a project where I created a website with a topic of my choice to practice what I have been learning. Along the way I also was presented with some new concepts that I hadn't seen up until that point. Such as Html/JSON parsing. Overall, this proved to be a great learning experience as I was able to implement and build on what I had learned so far.

### Takeaway
One of the biggest takeaways from this project are how comfortable I have grown with the unknown. For me this looks like taking in the problem/objective and beginning to figure out how I want to approach it. Another was how important it was to break my code up in to manageable pieces in order for me to keep things straight in my head. And lastly, spending time in my work led to me getting that much more in tune with where things were and what things did.

### Building the basic application
This was mostly an exercise in creating and setting up a new application within a project in Django.

### Creating/displaying a functioning create page
This story was a continuation of the Django set up. A model was created with the appropriate fields to be tracked based on my topic. I chose to reference a website that provided data on cost of living for states in the U.S. Based on this I added a set of choices that could be chosen to submit how the submitted state compares to the base index which was 100.


### Connecting to an API / Parsing through JSON
I used a weather API from rapidapi that turned out to be a little different than most APIs students find. This was a good exercise in learning how to discern between options which is not something I am used to doing with code. Searching for an api introduced new variables to consider before deciding to use it. I decided to continue after instructor approval and ended up being challenged throughout its implementation.

An adjustment I would make is to have the search fields take in three separate fields and creating a string with commas between each input and then using that new string as the search critera. The API required a city, state (abbreviated), and country (abbreviated) in order to popualte the rest of the data. Ultimately a great exercise in learning how to navigate and implement an API.

Another challenge from this story, and an opportunity to have some creativity was that I needed to display specific data that a user may want. The solution I came up with was to use checkboxes to then display only certain information about the searched city. In order to do that I found some resources that showed me how to check if a checkbox has been checked. After which I referenced that variable with the bool of each checkbox that then displayed any selected info.

I am most proud of the outcome of this story! It was an awesome example of struggling but overcoming and completing the task. A total confidence booster and motivator.



### Using Beautiful Soup to Web Scrape / Parsing Through HTML
This set of stories was the setup and use of Beautiful soup to scrape info from a website. The challenge here was to get the requests right in order to distill the info down to what I needed to display. With some instructor assistance, I was able to sucessfully display a page with every state and their average temperatures.


### Front End Improvements
Throughout the project as well as during this story I added various front end improvements. There are various others I would like to add such as the body of the html not getting covered by the footer and styling the navbar.
