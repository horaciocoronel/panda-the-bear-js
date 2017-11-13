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


====== Day 2 ========
Removing Elements from the DOM

1) Panda the Bear is lying about their skills! Take the "time travel" skill off the page to satisfy your personal sense of justice. Use your googling and docs-skimming skillz to find a jQuery function that will allow you to remove elements from the DOM. (hint: there are multiple ways of doing this, but the parent() function might be useful when it comes to selecting the right element)

(document.querySelector('.bar-default:nth-child(3n)')).remove();

===== Adding Elements to the DOM =====
1) That drawing of Pikachu is really cute. Let’s duplicate it using cloneNode() and insert it at the bottom of the .portfolio-container using insertAdjacentHTML() or appendChild().

var pikachu = document.querySelector("#right-image img");
var clone = pikachu.cloneNode(true);
var portfolioContainer = document.querySelector('.portfolio-container');

portfolioContainer.appendChild(clone);

2) Wow, that was so satisfying I think we should do it 10 more times. Use a for loop to help you do this.

for(var i = 0; i <= 9; i++){
  portfolioContainer.appendChild(clone.cloneNode(true));
}

3) Let’s add a message about when the page was last updated. We'll do this by appending a new <li> element to the <ul> in the sidebar (you might need to refresh the page to bring back the list items that we emptied out earlier).

i) First we need to construct a new <li> tag.
var listItem = document.createElement('li');

ii) Now we need a new <span> tag to go inside the <li> we just made. This span will eventually go in the left column below 'Phone'.
var leftSpan = document.createElement('span');

iii) Next we need to make a "text node" in order to put text inside our new span. A text node is a chunk of plain text that lives inside some HTML tag in the DOM.
var lastUpdated = document.createTextNode('Page last updated on');

iv) We're ready to put that new text node inside our new <span> using appendChild.
leftSpan.appendChild(lastUpdated);

v) And we'll put the <span> inside the <li>, again using appendChild.
listItem.appendChild(leftSpan);

vi) I select the bioSection and save it to a variable
var bioSection = document.querySelector('.bio-info');

vii) Append the listItem to the bioSection
bioSection.appendChild(listItem);

viii) Create a new right span
var rightSpan = document.createElement('span');

ix) Save date to a variable
var date = new Date();

x) Create a new text with the date we saved before
var dateHTML = document.createTextNode(date);

xi) Append the dateHTML node to the rightSpan
rightSpan.appendChild(dateHTML);

xii) Append lastChild to rightSpan
bioSection.lastChild.appendChild(rightSpan);
