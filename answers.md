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

var messageInputs = document.querySelector('input[name="message"]')
undefined
messageInputs.placeholder = "State your business";


9. Give the name field a "value" attribute of "your nemesis".

var nemesisName = document.querySelector('#name')
nemesisName.value ='Your Nemesis'
"Your Nemesis"


10. Change the value attribute of the email field to "koalathebear@gmail.com".

var email = document.querySelector('#email')
undefined
email
<input type=​"email" name=​"email" class=​"contact-info" id=​"email" placeholder=​"Email">​
email.value = "koalathebear@gmail.com"

"koalathebear@gmail.com"



11. Change the value of the submit button on the contact form to "En garde!".

var button = document.querySelector('#submit')
undefined
button
<input type=​"submit" name=​"submit" id=​"submit" value=​"Submit">​
button.value = 'En garde!'
"En garde!"


12. We should stop Koala from sending an email to Panda that they might regret! Find a way to disable the submit button (hint: familiarize yourself with the disabled attribute).

button.disabled = 'disabled'
"disabled"

13. We should help Panda protect their privacy by clearing their personal details from the sidebar. You can use reset() to do this.

var privacy = document.querySelectorAll('span.bio-info-value')

privacy.forEach(function(item) {item.innerText=""})
undefined



######## PART 2 #########

##Removing Elements from the DOM

1. Panda the Bear is lying about their skills! Take the "time travel" skill off the page to satisfy your personal sense of justice. We'll remove it using removeChild().

var timeTravel = document.querySelector('#time-travel')
undefined
timeTravel.parentElement
timeTravel.parentElement.remove

timeTravel.parentElement.remove();

##Adding Elements to the DOM

1. That drawing of Pikachu is really cute. Let’s duplicate it using cloneNode() and insert it at the bottom of the .portfolio-container using insertAdjacentHTML() or appendChild().

imageClone = document.querySelector('#right-image img')
var pikaClone = imageClone.cloneNode();
undefined
container = document.querySelector('.portfolio-container')
<div class=​"portfolio-container">​…​</div>​

container.appendChild(pikaClone);


2. Wow, that was so satisfying I think we should do it 10 more times. Use a for loop to help you do this.

for (var i = 0; i < 10; i++) {container.appendChild(pikaClone.cloneNode())};

3. Let’s add a message about when the page was last updated. We'll do this by appending a new <li> element to the <ul> in the sidebar (you might need to refresh the page to bring back the list items that we emptied out earlier).


##document.createElement, document.createTextNode, and appendChild are the keys to this process.

#First we need to construct a new <li> tag.

#var listItem = document.createElement('li');

#It isn't part of the DOM yet, it's just floating in the void. We'll eventually attach it to the <ul> in the sidebar, below Panda's name, location, and phone number.

#Now we need a new <span> tag to go inside the <li> we just made. This span will eventually go in the left column below 'Phone'.

#var leftSpan = document.createElement('span');

#Next we need to make a "text node" in order to put text inside our new span. A text node is a chunk of plain text that lives inside some HTML tag in the DOM.

#var lastUpdated = document.createTextNode('Page last updated on');

#We're ready to put that new text node inside our new <span> using appendChild.

#leftSpan.appendChild(lastUpdated);

#And we'll put the <span> inside the <li>, again using appendChild.

#listItem.appendChild(leftSpan);

#At this point our new elements are attached to each other but are still floating in the void separate from our webpage's DOM.
var listItem = document.createElement('li');
undefined
var leftSpan = document.createElement('span');
undefined
var lastUpdated = document.createTextNode('Page last updated on');
undefined
leftSpan.appendChild(lastUpdated);
"Page last updated on"
listItem.appendChild(leftSpan);
<span>​Page last updated on​</span>​



var listItem = document.createElement('li');
var leftSpan = document.createElement('span');
var lastUpdated = document.createTextNode('Page last updated on'); leftSpan.appendChild(lastUpdated);
listItem.appendChild(leftSpan);

var rightSpan = document.createElement('span');
var now = newDate();
var bioinfo = document.querySelector('.bio-info');
bioinfo.appendChild(leftSpan);
rightSpan.innerHTML = now bioinfo.appendChild(rightSpan);




It's up to you to go through the same process for the second span that will go in the right-hand column of the <ul> (below Panda's phone number). Look up the docs for the Date class to find a way of displaying the current date inside your next text node.


After that, find a way of selecting the <ul> and append the new <li> to it. For bonus marks, apply the correct classes to these new elements of yours so the styling is consistent with the rest of the list items.
