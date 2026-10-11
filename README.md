# Feedback Form

A responsive course feedback form with a star rating, live character counter and a popup that shows the submitted review. On large screens the page splits into an image on the left and the form on the right. On phones, the image becomes the background and the form sits in the center.

**Live demo:** https://keerthika546.github.io/feedback_form/

## Features

- 5-star rating with a filled gold star for every star up to the one clicked
- A mood message that changes with the rating (for example "Poor", "Good", "Excellent")
- Review textarea with a live counter showing the characters remaining
- Warning when the limit is exceeded: the counter turns red and the message changes
- Validation before posting: a rating must be chosen and the review must not be empty or too long
- Popup that shows the rating and review, and closes with the Close button, a click outside, or the Escape key
- Split layout on desktop, full-screen background layout on mobile

## Tech Stack

- HTML5
- Tailwind CSS
- JavaScript (vanilla)
- Font Awesome icons

## Project Structure

```
feedback_form/
├── index.html
├── left.jpg        (image shown beside the form)
└── README.md
```

## How It Works

1. Each star is an `<i class="star ...">` element. Clicking one stores `index + 1` as the rating.
2. A loop fills every star up to the clicked one and empties the rest.
3. The `input` event on the textarea updates the counter on every keystroke.
4. Clicking **Post** checks the rating and the text. If both are valid, the popup is filled with the review and shown with `display: flex`.

## Run Locally

1. Clone the repository
   ```bash
   git clone https://github.com/Keerthika546/feedback_form.git
   ```
2. Open `index.html` in your browser, or use the VS Code Live Server extension.

## What I Learnt

### JavaScript
- Selecting many elements with `querySelectorAll` and looping with `forEach`
- How the loop `index` and the closure let each star remember its own position
- Using `classList.add`, `remove` and `toggle` (including `toggle(name, true/false)`) to change styles
- Why `classList.replace` and `toggle` take one class name at a time
- Storing state in a variable (`rating`) and checking it before posting
- Why code outside an event handler runs once at page load, and code inside a handler runs on every event
- The `input` event for live feedback while typing
- Off-by-one errors in loops (`i < rating`, not `i <= rating`)
- `"⭐".repeat(rating)` as a shorter alternative to a loop
- Showing text safely with `textContent` instead of `innerHTML`
- Reading Console errors such as `ReferenceError: MAX is not defined` to find the exact line

### HTML and CSS
- Why `maxlength` blocks typing, so an over-the-limit warning needs the limit checked in JavaScript
- Building a modal popup with `fixed inset-0` and centering it with Flexbox
- Closing a modal by clicking the backdrop (`event.target === modal`) and with the Escape key
- Responsive layouts: one column on mobile, two equal columns from the `lg` breakpoint
- Making an image fill a column with `object-cover`
- `absolute inset-0` for layering a background image under content, and a dark overlay for readable text
- Using `hidden` with breakpoint classes such as `xl:block`, and why the viewport width decides whether they apply
- Spotting invalid code: `colour` instead of `color`, a typo in a class name, `type` on a textarea

### Git and GitHub
- Adding a remote with `git remote add origin` and pushing with `git push -u origin main`
- Renaming a branch with `git branch -M main`
- Fixing "refusing to merge unrelated histories" with `--allow-unrelated-histories`
- Resolving a rejected push by pulling first

## Future Improvements

- Show all submitted reviews in a list, with the newest first
- Save reviews in `localStorage` so they stay after a refresh
- Show the average rating
- Replace the browser `alert` messages with error text inside the form
- Send reviews to a backend (Spring Boot) and store them in a database

## Author

**Keerthika Selvam**
- GitHub: [@Keerthika546](https://github.com/Keerthika546)
- LinkedIn: [keerthika-selvam-](https://linkedin.com/in/keerthika-selvam-/)