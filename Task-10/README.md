# Task 10: Hero Image Animation (Fast Circle Orbit + Slow Squish)

## How It Works

The goal was to make the hero image move in a smooth, round orbit instead of cutting sharp corners, and then perform a distinct squeezing effect. To do this, I split the 2-second keyframe timeline (`fastOrbitSlowSqueeze`) into two simple steps:

1. **The Fast Orbit (0% to 75%):** Instead of just giving the browser 4 corner points (which makes it look like a rigid triangle or diamond), I manually mapped out the coordinates in 5% increments. By changing the X and Y coordinates smoothly at the same time, it forces the browser to glide the image in a clean, rounded circle. Since this entire path is packed into the first 75% of the time, the rotation happens really fast. The image size stays perfectly normal (`scale(1)`) while it's spinning.

2. **The Slower Squeezing (75% to 100%):** As soon as the image finishes the fast lap and returns to the center at 75%, it stops moving and starts the squish effect:
   * **At 80%**, it compresses down vertically and spreads out wider (`scale(1.25, 0.75)`) to look like a heavy downward impact.
   * **At 90%**, it bounces backward, stretching tall and skinny (`scale(0.85, 1.25)`) while lifting up slightly.
   * **At 100%**, it goes back to its normal shape just in time to start the fast circle orbit all over again.

## Testing
1. Open the project in your browser.
2. Watch the washing machine graphic on the right side of the hero section.
3. It should spin in a quick, smooth circle, stop in the middle to do a nice, clear squish-and-stretch bounce, and loop forever.