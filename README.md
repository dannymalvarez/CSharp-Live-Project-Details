# C# / ASP.NET / MVC / Entity Framework Live Project Details
Topic: Software to assist end user in managing website content.

### Introduction
I have completed a second 2 week sprint in the Software Development bootcamp through The Tech Academy. I was assigned to a project where I added functionality to software intended to facilitate website management for end users with little or no technical knowledge. This project was created usingC#, ASP.NET, MVC, Entity Framework, JavaScript, HTML, and CSS. While I built upon a lot of what I had already been taught throughout the bootcamp, I learned a lot through research and new challenges. These new challenges improved my researching skills most notably how to discern between what was and was not relevant.

### Takeaway
The longer I spent in the project, the more comfortable and familiar I was with what was done and what I needed to add. I was also able to focus on my comfort level with the unknown which pushed me to research and learn. There were times I came across information that was not useful in that moment but was useful later on. My brain functions in such a way where I will remember, even if only vaguely, something similar. At which point I find myself thinking about it, consciously or otherwise, until it comes back to me like a crashing wave. Sometimes it's nothing useful but other times it's a home run and the ball gets rolling. 

There were times I needed to level with myself and recognize that I was going in circles. These circles I found were usually in how and what I was researching or my approach to problem solving. That was when I would take a step back and ask for help. Because at the end of the day I only know what I know but I know I'll learn and grow one way or another. 

### Sign-In Page - Listing a count for the number of developers that have worked on this project
This story was a continuation of the general project set up. I was able to piece together some code after some research and was able to get a count and display it in the correct spot. 

#### JavaScript:
window.onload = function devCounter() {
    let list = document.getElementById("PersonList");
    let names = list.getElementsByTagName('p').length;
    document.getElementById("NumPersons").innerHTML = names;
}

#### Cshtml:
<h1>Developers Of TheatreCMS &nbsp;<span id="NumPersons" class="badge badge-secondary" *onload="devCounter()"*></span></h1>

![image](https://user-images.githubusercontent.com/92490029/156861286-bdaf7449-0205-4069-a94d-f7e2b8478953.png)


### Creating the model and CRUD pages
This was mostly an exercise in creating and setting up a new application using ASP.NET/MVC/EF in Visual Studio. After creating the model, the CRUD pages were scaffolded using EntityFramework. The hardest part in this step was making sure to select the appropriate items/checkboxes. There were a handful of foreign items but this is where research and asking questions was helpful.


### Styling the CRUD pages
There were two stories that involved styling pages. The Create and Edit pages needed a cleaner UI which included adding headers, styling buttons, adding placeholders to the input fields, centering the form, adding a subtle border for an active input field, and adding a method for users to upload images. 

![image](https://user-images.githubusercontent.com/92490029/156861620-028eef45-9458-48b3-a1d8-81d5fcb6a91c.png)

The second styling story was a great exercise in research and recognizing when I was going in circles. It was fun to try to implement what I had envisioned as far as a solution, but the execution was not there. Ultimately I achieved one of the desired outcomes in 4 different parts. When the image was hovered over, the title, edit, and delete buttons needed to appear and the image needed to have a greyed overlay. I learned a lot about CSS, nesting, children, inheritance, and believe I was close to a working solution but it would have been a lot more convoluted than it needed to be. The next step for this would be to get more familiar and comfortable with Bootstrap, which is what was being used to style the pages. 


### Photo storage and retrieval 
This was a tough story where I needed to store the uploaded image to the database, retrieve it, and display it on the Index, Edit, and Delete pages. A good chunk of the 2 week sprint was spent on this story. This was probably the story that most strengthened my discernment over the relevance of an article/solution to my given issue. This made use of some JavaScript I found that allowed an upload to be registered from a click, or a change. That upload was then displayed for confirmation to the user. In order to save it to the database I had to convert the image to a byte and vice versa in order to display it to the page.


#### Taking in an uploaded image: JavaScript
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

#### Converting image to a byte: model
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
By the time my two weeks were up, I was unable to finish the second styling story. I did manage to accomplish proper positioning of the buttons, image title, and the image container. This story really threw me for a loop as I got caught up in creating custom CSS versus leveraging Bootstrap's functionality. I look forward to improving on my problem solving and researching skills in order to achieve project requirements. All in all this was a great opportunity to work on something that both challenged me and improve upon my coding foundation. 
