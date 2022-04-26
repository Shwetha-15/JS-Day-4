// Intro to DOM - HTML - CSS - JavaScript

// DOM-Doc obj model - tree structure of whole HTML

// ELEMENT SELECTORS

// delete items
document.querySelector(".items");

document.querySelector(".item1");
let item1 = document.querySelector(".item1");
item.remove();
document.querySelector(".item2");
let item2 = document.querySelector(".item2");
item.remove();
document.querySelector(".item3");
let item3 = document.querySelector(".item3");
item.remove();
document.querySelector(".item4");
let item4 = document.querySelector(".item4");
item.remove();
document.querySelector(".item5");
let item5 = document.querySelector(".item5");
item.remove();

// update items
let item = document.querySelector(".item1");
item.textContent="Good Morning";


// change item2 to heading
let item = document.querySelector(".item2");
item.innerHTML="<h1>Hello</h1>";


// update button color to red
let button = document.querySelector(".btn");
button.style.background = "brown";


// EVENTS
let button = document.querySelector(".btn");
button.addEventListener("click",(e) =>
                        {
    console.log("click");
e.preventDefault();
});

// Keyboard Event
let nameInput = document.querySelector("#name");
nameInput.addEventListener("input",e =>
                           {
    document.querySelector(".container").append(nameInput.value);
});

let emailInput = document.querySelector("#email");
emailInput.addEventListener("input",e =>
                           {
    document.querySelector(".container").append(emailInput.value);
});

// Listen for form submit
function onSubmit(e) {
  e.preventDefault();
}
console.log(nameInput);
console.log(nameInput.value);
console.log(emailInput.value);

// Select entire form & addEventListener to FORM
let myForm = document.querySelector("#my-form");
myForm.addEventListener('submit', onSubmit);

// addEventListener to form on console via ALERT
if(nameInput.value === '' || emailInput.value === '')
{
  alert('Please enter all fields');
}
else
{
  console.log('success');
}

// addEventListener to form on console via Message on <div> selection
let msg = document.querySelector(".msg");


if(nameInput.value === '' || emailInput.value === '')
  {
    msg.classList.add('error');
    msg.innerHTML = 'Please enter all fields';
  }
  else
  {
    console.log('success');
  }

// Same as above - but remove alert msg after 3seconds
if(nameInput.value === '' || emailInput.value === '')
  {
    msg.classList.add('error');
    msg.innerHTML = 'Please enter all fields';
    setTimeout(() => msg.remove(), 3000);
  }
  else
  {
    console.log('success');
  }

  // As & when users get registered add into LIST
let userList = document.querySelector("#users");


  if(nameInput.value === '' || emailInput.value === '')
  {
    msg.classList.add('error');
    msg.innerHTML = 'Please enter all fields';
    setTimeout(() => msg.remove(), 3000);
  }
  else
  {
    // Create new list item with user
    let li = document.createElement('li');

    // Add text node with input values
    li.appendChild(document.createTextNode(`${nameInput.value}: ${emailInput.value}`));

    // Append to ul
    userList.appendChild(li);
    // Clear fields
    nameInput.value = '';
    emailInput.value = '';
  }
