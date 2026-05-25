# Task 8: CSS Hamburger Menu in Mobile: (Pseudo Classes and elements)

## What I Learned About CSS Focus & Toggling Menus
For this task, the rules said we were absolutely not allowed to use any JavaScript to make the mobile menu open. I had to find a trick to make the sidebar appear only when a user clicks the hamburger button:
* **The :focus Selector:** I put the three-line hamburger icon inside a normal HTML `<button>`. By using the `:focus` selector in CSS, I can target the exact moment someone clicks or taps that button.
* **The Sibling Selector (~):** In the HTML code, I placed the black menu `div` right after the button. In my CSS, I used the general sibling selector (`.menu-toggle-btn:focus ~ .sidebar-drawer`). This tells the browser: "Whenever the button is clicked and has focus, instantly show the hidden menu box right next to it."

## Fixing the Layout Heights and Stopping the Scroll
To pass the strict requirement where the layout has to fit perfectly on a single screen without creating annoying vertical scrollbars on desktop, I used a basic height budget:
1. The entire parent box is locked at `100vh` (viewport height) and `100vw` (viewport width). I added `overflow: hidden` to make sure any layout spills get chopped off instead of creating scrollbars.
2. I split the screen space strictly: the top navbar gets exactly `12vh` of height, and the main hero content section gets the leftover `88vh`.
3. To stop the laundry machine icon from growing too huge on shorter screens and pushing the text down past the bottom edge of the monitor, I put a strict limit on the image using `max-height: 60vh`.

## Reworking the Mobile Screen Views (Media Queries)
* **Tablet View (Under 1024px):** I used media queries to make the font sizes on the main header text smaller (dropping it from `46px` to `32px`) and shrunk the image max-height to `45vh` so the page doesn't feel cramped.
* **Mobile View (Under 768px):** * I hid the standard horizontal menu links entirely using `display: none` because they were overlapping on small screens.
  * I turned on the hamburger button (`display: block`).
  * **Full-Screen Menu Overlay:** To match the assignment example, I changed the sidebar drawer to `position: fixed` with `top: 0` and a height of `100vh`. This lets the black menu pop out and completely cover the entire screen height, including masking over the white navbar. I set the hamburger lines to turn white when clicked so you can still see the button on top of the black menu background.
  * **Stacking the Columns:** I used `flex-direction: column` on the hero section so the laundry illustration drops neatly directly underneath the text panel instead of breaking sideways.

## How to Test and Run This
1. Make sure both `index.html` and `style.css` are saved inside your `task-8/` folder.
2. Double-click the `index.html` file to run it in Google Chrome or any browser.
3. Open the browser's developer inspect tool (press F12), switch to the mobile phone layout, and click on the three-line hamburger button. The black sidebar menu will pop open over the full screen height immediately, and the page will still stay perfectly contained without scrolling.