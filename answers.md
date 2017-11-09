1) Select the element that contains the profile image (hint: look for the class). Change the src attribute so it points to a picture of your choosing instead.
PROTIP: use the inspector to learn the dimensions of the current profile image and use a placeholder image service such as Place Bear to get an image of the same size.

var profile = document.querySelector('img');
profile.src = "images/self-portrait-totoro.png";


1) Use the same approach to select the element that contains the photo of the sky and change the src attribute to another picture URL of your choosing.
var portfolioImage = document.querySelector('#left-image img');
portfolioImage.src = "https://loremflickr.com/325/225/sky";


2) Select the heading that says "Panda the Bear" and change it to your own name.
var title = document.querySelector('h1');
title.innerText = 'Horacio';

3) Select the heading that says "Employment" and change it to something else. (hint: use a descendant selector)
var employment = document.querySelector('#employment h3');
employment.innerText = "Experience"

4) Change the colour of the body.
body.style = 'background: #777777;';

5) Change the colour of each element using the highlight class. Use a for loop to do this.
highlight.forEach(function(element) {
    element.style = 'background-color: #2fcbd6;';
});

6) Change the font family of the h1 to 'monospace'.
var h1 = document.querySelector('h1');
h1.style = 'font-family: monospace; background-color: #2fcbd6;' ;

7) Find a way to select the round icons in the sidebar and then change their colour.
var greenIcon = document.querySelectorAll('.action-icon-bg');
greenIcon.forEach(function(element) {
    element.style = 'background-color: #2a9fa8;';
});

8) Scroll down to the contact form. Change the placeholder attribute of the name field to "identify yourself".

var name = document.getElementsByName('name')[0].placeholder;
name.innerText = 'Identify yourself';

9) Change the placeholder attribute of the message field to "state your business".

var message = document.getElementsByName('message')[0];
message.placeholder = 'state your business';

10) Give the name field a "value" attribute of "your nemesis".
var nameField = document.getElementsByName('name')[0];
nameField.value = 'your nemesis';

11) Change the value attribute of the email field to "koalathebear@gmail.com".
var emailField = document.getElementsByName('email')[0];
emailField.value = 'koalathebear@gmail.com';

12) Change the value of the submit button on the contact form to "En garde!".
var submitButton = document.getElementsByName('submit')[0];
submitButton.value = 'En garde!'

13) We should stop Koala from sending an email to Panda that they might regret! Find a way to disable the submit button (hint: familiarize yourself with the disabled attribute).

submitButton.disabled = true;


14) We should help Panda protect their privacy by erasing their personal details from the sidebar.
var parent = document.querySelector('aside');
var bioInfo = document.querySelector('.bio-info');
parent.removeChild(bioInfo);
