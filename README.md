# C# / ASP.NET / MVC Live Project Details
Topic: Software to assist end user in managing website content.

### Introduction
I have completed a second 2 week sprint in the Software Development Bootcamp through The Tech Academy. I was assigned to a project where I added functionality to software intended to facilitate website management for end users with little or no technical knoweldge. This project made use of Razor, C#, HTML, JavaScript, and CSS. While I built upon a lot of what I had been taught throughout the bootcamp, I also had to do even more research than the previous live project. Instructors encouraged us to struggle for a while which improved my use of google and discernment for what was and wasn't relevant. The elvel of specificity of the issues I was running into made that a necessity. 

### Takeaway
This project built upon what the last project had left me with, which was comfort with the unknown. My time on StackOverflow and google exposed me to a wide variety of content, both useful and otherwise. But what wasn't useful in the moment was either useful at a later time or I am sure will be useful at some point in my career. My brain functions in such a way where I will remember, even if only vaguely, something similar. At which point I find myself thinking about it, consciously or otherwise, until it comes back to me and it's my vesrion of a "Brain Blast!" Sometimes it's nothing useful but other times it's a home run and the ball gets rolling. Very enjoyable part of learning because it may someday be useful. 

I also had to level with myself and ask for help when I was stuck or going in circles. Identifying that was helpful because I hadn't really done a great job at catching myself in those seemingly endless circles of my attempts at solving the problem. 

### Sign-In Page - Listing a count for the number of developers that have worked on this project. 
This story was a continuation of the general project set up. I was able to piece together some code after some research and was able to get a count and display it in the correct spot. 

#### JS:
window.onload = function devCounter() {
    let list = document.getElementById("PersonList");
    let names = list.getElementsByTagName('p').length;
    document.getElementById("NumPersons").innerHTML = names;
}

#### cshtml:
<h1>Developers Of TheatreCMS &nbsp;<span id="NumPersons" class="badge badge-secondary" *onload="devCounter()"*></span></h1>

![image](https://user-images.githubusercontent.com/92490029/156861286-bdaf7449-0205-4069-a94d-f7e2b8478953.png)


### Creating the model and CRUD pages
This was mostly an exercise in creating and setting up a new application using ASP.NET/MVC in Visual Studio. After creating the model, the CRUD pages were scaffolded using EntityFramework. The hardest part in this step was making sure to select the appropriate items/checkboxes. There were a handful of foreign items but this is where that newfound comfort with the unknown kicked in knowing if it was wrong I would have to get that figured out. After a couple tries, I was able to get everything up and running.


### styling the CRUD pages
There were two stories that involved styling pages. The Create and Edit pages needed a cleaner UI which included adding headers, styling buttons, adding placeholders to the input fields, centering the form, a subtle touch border for an active input field, and a method for users to upload images. 

![image](https://user-images.githubusercontent.com/92490029/156861620-028eef45-9458-48b3-a1d8-81d5fcb6a91c.png)

The second styling story was a great exercise in research and recognizing a dead end of sorts in my approach. It was fun to try to implement what I had envisioned as far as a solution, but the execution was not there. Ultimately I achieved one of the desired outcomes in 4 different parts. When the image was hovered over, the title, edit, and delete buttons needed to appear and the image needed to have a greyed overlay. I learned a lot about CSS, nesting, children, inheritance, and believe I was close to a working solution but it would have been a lot more convoluted than it needed to be. The next step for this would be to get more familiar and comfortable with Bootstrap, which is what was being used to style the pages. After this live project and the Python live project, I feel more comfortable with wed development than I thought I would when I began the bootcamp.    


### Photo storage and retrieval 
This was a tough story where I needed to store the uploaded image to the database, retrieve it, and display it on the Index, Edit, and Delete pages. A good chunk of the 2 week sprint was spent on this story. This was probably the story that most strengthened my discernment over the relevance of an article/solution to my given issue. This made use of some JavaScript I found that allowed an upload to be registered from a click, or a change. That upload was then displayed for confirmation to the user. In order to save it to the database I had to convert the image to a byte and vice versa in order to display it to the page.


#### Taking in uploaded image: JavaScript
function readURL(input) {
    if (input.files && input.files[0]) {
        var reader = new FileReader();

        reader.onload = function (e) {
            $('#imageResult')
                .attr('src', e.target.result);
        };
        reader.readAsDataURL(input.files[0]);
    }
}

$(function () {
    $('#upload').on('change', function () {
        readURL(input);
    });
});

#### Converting to a byte: model
  public byte[] ConvertToByte(HttpPostedFileBase file)
        {
            byte[] Photo = null;
            if (file != null)
            {
                BinaryReader rdr = new BinaryReader(file.InputStream);
                Photo = rdr.ReadBytes(file.ContentLength);
            }
            return Photo;
        }

#### Displaying image: cshtml

@foreach (var item in Model)
{


    string text = "";
    if (item.Photo != null)
    {
        text = Convert.ToBase64String(item.Photo);
    }
 }


### Final state of the project
The project ended for me with the styling being incomplete. The styling in question was to position buttons, the title, and general image container properly on the page. This one really threw me for a loop but it seemed to be due to pursuing the wrong approach for too long. I look forward to improving my approach to learning and executing what I learn and achieve the desired outcomes! Perhaps one day I can look back and quickly pick out what I did "wrong" or could have done better. My tech journey's version of looking back and laughing at it once its over. Here's to the beginning of a career in tech!
