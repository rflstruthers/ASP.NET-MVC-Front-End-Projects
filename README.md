# Live Project

## Introduction
For the last two weeks of my time at the tech academy, I worked with my peers in a team developing a full scale MVC/MVVM Web Application in C#. Working on a legacy codebase was a great learning oppertunity for fixing bugs, cleaning up code, and adding requested features. I saw how a good developer works with what they have to make a quality product. Because much of the site had already been built, there were also a good deal of front end stories and UX improvements that needed to be completed, all of varying degrees of difficulty. I worked on several [front end stories](#front-end-stories) that I am very proud of and was abale to gain experience both adding a new feature for the application and updating existing code. Over the two week sprint I also had the opportunity to work on some other project management and team programming [skills](#other-skills-learned) that have made me a better developer.

Below are descriptions of the stories I worked on, along with code snippets and navigation links.

## Front End Stories
### Sidenav Edit
This story was to fix issues with the side navigation bar that displayed on all pages of the site. As it was, the navbar was not tall enough and it did not stay fixed when scrolling the page. The background color and icon spacing and color also needed to be changed. In the css file for the navbar, I changed the color and spacing between icons. I also set the navbar position to fixed and height to 100%. I made these edits in the css file for the sites mobile views as well.

### Chat Message View Edit
The Index View for Chat Messages needed to be changed to have a similar layout as the News Index View. I examined the News Index View and css file and compared it to the same files for Chat Messages. I found that the News Index View was using the Bootstrap table class to format the pages content. I edited the Chat Message Index View to use the same Bootstrap class, making the two pages follow the same layout and styles.

### Username Display Edit
The application had a container displayed the users name and image, along with a dropdown menu when the cursor was hovered over the container. The story was to make sure the user name and image displayed inline for larger screen sizes and to make sure the dropdown menu was aligned correctly with the container. I examined the existing code and determined that if the container was a certain width, the username and image would be inline, but at smaller widths, they would stack on top of each other. I changed the containers minimum width for larger screen sizes to make the username and image inline. I also adjusted the dropdown menus left margin so it would be properly aligned with the container. I had to have a maximum width for the dropdown menu for smaller screen sizes to ensure proper alignment.

### Mobile Friendly View
I had previously created a Cart Item Index View to display a shopping cart of selected products. This story was to look over a previous branch and determine how Mobile Views had been implemented for other pages, and then implement a Mobile view page for the Cart Item Index. I found that I needed to create a new cshtml file for the Mobile Cart and insert some logic in the Cart Item Index file. I added an IF statement to determine if the mobile or desktop viex should be displayed.

      @if (ViewContext.HttpContext.GetOverriddenBrowser().IsMobileDevice)
      {
          { Html.RenderAction("_CartMobile", "CartItem"); }
      }

I then edited the layout of the _CartMobile.cshtml file to display appropriately for a mobile device.

### Tooltip for Button
I was tasked with creating a tooltip that would display information to the user when the cursor was hovered over a Register button. I researched how to implement a tooltip and applied the following css to the Register button.

    .register {
    position: relative;
    width: 100%;
    }
        .register:before,
        .register:after {
            display: block;
            opacity: 0;
            pointer-events: none;
            position: absolute;
        }
        .register:after {
            border-right: 6px solid transparent;
            border-bottom: 10px solid #fbc2eb;
            border-left: 6px solid transparent;
            content: '';
            height: 0;
            top: 30px;
            left: 50%;
            width: 0;
            z-index: 3;
            /* expand */
            transform: translate3d(0,6px,0);
            transition: all .1s ease-in-out;
        }
        .register:before {
            background: #fbc2eb;
            border-radius: 5px;
            color: black;
            content: attr(data-title);
            font-size: 16px;
            padding: 10px 0px 10px 20px;
            top: 36px;
            line-height: 20px;
            text-align: left;
            z-index: 3;
            /* expand */
            transform: scale3d(.2,.2,1);
            transition: all .2s ease-in-out;
            box-shadow: 0 0 20px #9681c1;
        }
        .register:hover:before,
        .register:hover:after {
            opacity: 1;
            transform: scale3d(1,1,1);
        }
        .register:hover:after {
            transition: all .2s .1s ease-in-out;
        }
       
I added the information string as the data-title of the div tags that contained the Register buttons and made sure the buttons functionality still worked after my front-end edits.

## Other Skills Learned
* Working with a group of developers to identify bugs to the improve usability of an application.
* Improving project flow by communicating about who needs to check out which files for their current story.
* Learning new efficiencies from other developers by observing their workflow and asking questions.  
* Practice with team programming/pair programming when one developer runs into a bug they cannot solve.
* Participating in daily Stand-Up's to update the Project Manager and peers on my work.
* Planning how to complete a User Story and implementing that plan to satify the Story requirements.
* Producing results by a specified deadline.
  
*Jump to: [Front End Stories](#front-end-stories), [Page Top](#live-project)*
