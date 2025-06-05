# Web-Scrapper
This professional interactive web scraper offers a robust, user-friendly tool for quick data extraction from static web pages
1. Overview
This file is a complete interactive web scraping application created using only HTML, CSS, and JavaScript within a single HTML document. It enables users to enter a website URL and a CSS selector to scrape textual data from that website and present it in a visually appealing format, all client-side in the browser.

No external dependencies or backend services are required, except for reliance on a third-party public CORS proxy to bypass cross-origin restrictions.
2. File Structure
The file is organized into the following main sections:
<!DOCTYPE html>
<html lang="en">
<head> ... </head>
<body>
  <header> ... </header>
  <main> ... </main>
  <footer> ... </footer>
  <script> ... </script>
</body>
</html>

3.Detailed Breakdown
a) DOCTYPE and HTML Element
The document starts with <!DOCTYPE html> indicating HTML5.
The root <html> element specifies the language as English with lang="en" attribute.
b) Head Section (<head>)
Contains:

Character encoding declaration: <meta charset="UTF-8">.
Responsive meta viewport for mobile: <meta name="viewport" content="width=device-width, initial-scale=1">.
The page <title> "Professional Interactive Web Scraper".
An embedded <style> block defines all CSS styles, including:
Root CSS variables for colors, background, shadows.
Styling for body, header, form elements, buttons, messages, result cards.
Responsive design via media queries.
Accessibility-focused visual styling.
The CSS ensures a professional, modern UI with distinct color schemes, clean layout, comfortable spacing, and responsive behavior.

c) Body Section (<body>)
Header (<header>)

Contains the app title "Professional Interactive Web Scraper".
Styled with a bold background color and centered white text.
Main Content (<main>)

Inside the <main>, three groups:

Input Form (<form id="scrapeForm">)

Two labeled inputs:
Website URL: A required URL input field with placeholder and accessibility attributes.
CSS Selector: A required text input for any valid CSS selector string.
A submit button labeled "Scrape".
Instructional helper texts for both inputs below the form.
The form uses CSS grid layout for alignment.
Status Message (<div id="message">)

Displays success or error messages dynamically.
Uses ARIA live region attributes for screen readers.
Results Section (<section id="results">)

Displays scraped elements in a grid of styled "cards", one card per matched element.
Each card shows the element index and text content or limited HTML snippet.
Footer (<footer>)

Provides copyright.
Mentions use of a public CORS proxy.
d) Script Section (<script>)
Embedded JavaScript drives the functionality:

Constants and UI Element References:

Stores references to form fields, button, message display, results container.
Defines the public CORS proxy URL: https://api.allorigins.win/get?url=
Helper Functions:

clearOutput(): Clears messages and results.
showMessage(msg, type): Shows a message in the message area with optional error/success style.
createCard(title, content): Creates DOM card elements representing scraped items.
Main Scraping Logic (scrape function):

Performs URL encoding and fetches the proxied HTML.
Parses the HTML string using DOMParser into a DOM document.
Uses the user-provided CSS selector to find matching elements in the document.
If no matches, shows an error message.
Otherwise, creates and appends card elements for each matched item showing its text or snippet.
Provides success message with count of elements.
Handles network or parsing errors with user-friendly messages.
Event Handling:

Registers a submit event listener on the form.
Validates inputs.
Calls the scrape function.
Manages button enabled state and label to give user feedback during scraping.
4. How it Works
The user enters a full URL and a CSS selector.
When the form is submitted, the app fetches the webpage HTML through the CORS proxy.
Parsing the fetched HTML, it finds the elements matching the selector.
Displays results dynamically in nicely styled cards.
Errors like network issues or no matches are communicated clearly.
The app runs fully in the browser—no server-side code or installation required.
5. Usage Notes
Since this runs in the browser and relies on a public proxy, some websites may be inaccessible due to restrictions.
JavaScript-heavy sites (SPA’s) may not render data visible in the raw HTML, so those contents won’t be scraped.
CSS selectors must be valid and specific to the desired content.
The app works well for most static content and simple scrapes for learning or quick testing.


