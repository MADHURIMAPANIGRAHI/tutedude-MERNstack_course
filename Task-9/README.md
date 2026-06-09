# Task 9: Custom Button Hover Effects (Transforms and Glows)

## How I Built and Figured Out the Animations
For this assignment, I designed a micro-interaction on the blue "Book a service today!" button using pure CSS transforms and transitions. 

Here is exactly how I chose the design values based on my browser tests:

* **Why I Chose -4deg for Rotation:** I originally tested a `-10deg` rotation, but it twisted way too far and made the text layout look completely broken and crooked. I dropped it down to `-2deg`, but you could barely notice it. Settling on `-4deg` gives it a visible, energetic tilt to the left without making it hard to read.
* **Why I Chose 1.25 for Scale:** I wanted the button to pop out noticeably when someone hovers their mouse pointer over it. A scale of `1.1` felt too small, but `1.25` expands the button size by 25%, making it clearly look bigger and clickable while staying inside the limits of the text column wrapper.
* **Why I Chose -12px for translateY:** Moving the button up on the Y-axis makes it feel like it is floating toward the cursor. Shifting it up by `-12px` perfectly matches the large `1.25` scale growth, so the button doesn't clip into elements below it.
* **How I Fixed the Blue Neon Glow:** My earlier submission layout left out the actual shadow properties. I fixed this by using the exact brand blue color with an opacity value of 65% (`rgba(28, 175, 246, 0.65)`) along with a broad `30px` blur radius. Now, the moment the button jumps up, a bright blue neon light bleeds out against the white canvas background.
* **Testing Cubic-Bezier Curve Values:** Instead of a basic, boring linear transition, I tested a fast-out curve using `cubic-bezier(0.25, 1, 0.5, 1)`. I tried an aggressive ease-in curve first, but it made the button lag behind the cursor. This specific setting makes the button snap upward and scale rapidly the second your mouse grazes it, then slide back down naturally when you move away.

## How to Verify behavior in the Browser
1. Save `index.html` and the updated `style.css` in your local `/task-9` directory.
2. Launch `index.html` in your web browser.
3. Move your mouse directly over the blue action button. You can verify that it expands cleanly by 25%, tilts exactly 4 degrees to the left, shifts upwards, and casts a wide blue glowing light shadow instantly underneath.