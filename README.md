# Household builder


## Overview

Please see [demo](https://github.com/rapicastillo/cto-hhbuilder/blob/master/household-builder.gif) for a full view of features.

A person should be able to add a relative and see the list as they update it. One will be able to delete and add relatives, as well as submit it to a server. In this code, the server is symbolized by printing it inside a hidden `<pre>` tag


## Coding Notes

This was coded in Javascript ES3, leveraging prototyping to define classes. All of the elements necessary for this application to work is in index.js. The Javascript is separated into three key elements:

* Relative class
* Household Manager
* FormManager


### Aspects 

#### Relative

This class manages the atomic entity of the application, the `Relative`. It stores individual information, manages its individual validity, and stores minute info about an individual

#### Household Manager

This entity manages the household per sé. Manages addition and deletion of the list of relatives a person has

#### FormManager

This entity manages the elements in the context of HTML and DOM. This manages event handles, elements, rendering, etc. 


### Prototype format

I opted for a prototype format to make the code more readable and allow for a more modular approach in handling data.
In this scenario, the form manager sets itself to be a singleton managing instances of the household.

### Use of `date.getTime` as identifier

Since  we don't have an identifier/incrementor available to manage deletion, i opted to use timestamp as our identifier. More or less it will keep the ID unique.

Because of this, I had to remove the temporary identifier upon submission so that the only elements being submitted are the age, relationship, and if the relative is a smoker.


# About the Task

This application needs a way to capture information about a household applying
for health insurance coverage. Develop a UI for building a household up from
individual people.

## Information 

You have been given an HTML page with a form and a placeholder for displaying
a household.

In the given index.js file, replace the "Your code goes here" comment with JavaScript that can:

- Validate data entry (age is required and > 0, relationship is required)
- Add people to a growing household list
- Remove a previously added person from the list
- Display the household list in the HTML as it is modified
- Serialize the household as JSON upon form submission as a fake trip to the server

## Notes

Don't modify the given index.html file in any way. You're of course still allowed to modify the DOM through Javascript.

You must write JavaScript, not a language that compiles down to JavaScript. You
must use ES3 or ES5/5.1 standard. Assume the capabilities of a modern
mainstream browser in wide use, i.e., no bleeding-edge features. No 3rd party
libraries — i.e., no jQuery.

The display of the household list is up to you.

On submission, put the serialized JSON in the provided "debug" DOM element and display that element.

After submission, the user should be able to make changes and submit the household again.

You don't need to add validations around anything other than the age and relationship requirements described above. It's ok for someone to add 35 parents.

The focus here is on the quality of your JavaScript, not the beauty of your design. The controls you add around viewing and deleting
household members should be usable but need not be much to look at.
