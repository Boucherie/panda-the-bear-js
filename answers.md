Hacking Panda the Bear's Resume

1. Select the element that contains the profile image (hint: look for the class). Change the src attribute so it points to a picture of your choosing instead.

var profileImage = document.querySelector('.profile-image')
undefined
profileImage
<img src=​"images/​self-portrait-grassbg.jpg" alt=​"Self Portrait" title=​"Self Portrait" class=​"profile-image">​

profileImage.src = "https://placebear.com/400/400";
"https://placebear.com/400/400"


PROTIP: use the inspector to learn the dimensions of the current profile image and use a placeholder image service such as Place Bear to get an image of the same size.

Use the same approach to select the element that contains the photo of the sky and change the src attribute to another picture URL of your choosing.

#####(https://unsplash.com/collections/385735/sky)

2. Select the heading that says "Panda the Bear" and change it to your own name.

var title = document.querySelector('h1')
undefined
title
<h1 class=​"highlight">​Panda The Bear​</h1>​
title.innerText = 'Emily Boucher';
"Emily Boucher"


3. Select the heading that says "Employment" and change it to something else. (hint: use a descendant selector)

var employmentTitle = document.querySelector('#employment > h3.info-title');
undefined
employmentTitle
employmentTitle.innerText = ("Panda Tasks");
"Panda Tasks"

4. Change the colour of the body.

body.style.backgroundColor = ('grey');
"grey"

5. Change the font family of the h1 to 'monospace'.

body.style.fontFamily  = ('monospace');
"monospace"

6. Find a way to select the round icons in the sidebar and then change their colour.


buttons = document.querySelectorAll('.action-icon-container')
buttons.forEach(function(item) {(item.backgroundColor = "black") });

7. Scroll down to the contact form. Change the placeholder attribute of the name field to "identify yourself".

var textInputs = document.querySelector('input[name="name"]')
undefined
textInputs
<input type=​"text" name=​"name" class=​"contact-info" id=​"name" placeholder=​"Name">​
textInputs.placeholder = "identify yourself";
"identify yourself"


8. Change the placeholder attribute of the message field to "state your business".



9. Give the name field a "value" attribute of "your nemesis".

10. Change the value attribute of the email field to "koalathebear@gmail.com".

11. Change the value of the submit button on the contact form to "En garde!".

12. We should stop Koala from sending an email to Panda that they might regret! Find a way to disable the submit button (hint: familiarize yourself with the disabled attribute).

13. We should help Panda protect their privacy by clearing their personal details from the sidebar. You can use reset() to do this.
