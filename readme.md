# Date Formatter

This project is a fun and interactive way to display the current date and time in different formats. It's built with HTML, CSS, and JavaScript.

## How it works

The JavaScript file `script.js` gets the current date and time using the JavaScript `Date` object. It then formats this date and time in three different ways:

1. Day-Month-Year
2. Year-Month-Day
3. Month-Day-Year Hours:Minutes

The user can select one of these formats from a dropdown menu, and the displayed date and time will update accordingly.

## Styling

The CSS file `styles.css` provides styling for the page. It uses CSS variables for colors, and it includes media queries to make the layout responsive.

## HTML Structure

The HTML file `DatePage.html` contains the structure of the page. It includes a dropdown menu for selecting a date and time format, and a paragraph where the formatted date and time is displayed.

## Code Snippet

Here's a snippet from `script.js` that shows how the date and time formatting is done:

```javascript
const date = new Date();

const day = date.getDate();
const month = date.getMonth() + 1;
const year = date.getFullYear();
const hours = date.getHours();
const minutes = date.getMinutes();
const formattedDate = `${day}-${month}-${year}`;

dateOptionsSelectElement.addEventListener('change', () => {
    switch (dateOptionsSelectElement.value) {
        case "yyyy-mm-dd":
        currentDateParagraph.textContent = formattedDate.split("-").reverse().join("-");
        break;
        case "mm-dd-yyyy-h-mm":
        currentDateParagraph.textContent = `${month}-${day}-${year} ${hours} Hours ${minutes} Minutes`;
        break;
        default:
            currentDateParagraph.textContent = formattedDate;
    }
})