## Task 7: Responsive Hero Landing Page

### 1. Layout Overrides & Flexbox
Following the criteria to fix breaking desktop layouts on tablet and mobile viewports, the legacy layout structure was updated to leverage CSS Flexbox. 
* The navigation header and the main structural hero sections utilize `display: flex`. 
* By pairing this with `justify-content: space-between` and `align-items: center`, components automatically balance across the horizontal axis without relying on arbitrary pixel-padding shifts.

### 2. Viewport Sizing Logic (`vh` / `vw`)
To lock the landing page within the viewable bounds of any device monitor and explicitly forbid vertical scrolling, the height budget is calculated systematically:
* **The Master Canvas:** Bound strictly to `100vh` and `100vw`.
* **Navbar Height Block:** Allocated exactly `12vh`.
* **Hero Content Block:** Allocated exactly `88vh`.
* **Asset Prevention:** Inner layout illustration images are bound to `max-height: 60vh`. This ensures that nested content cannot physically push the container bounds past the bottom margin lip of the browser window.

### 3. Responsive Media Queries Strategy
* **Tablet Viewport (`max-width: 1024px`):** Typography scales down systematically (e.g., heading font sizes drop from `46px` to `32px`), padding handles tighten, and the primary illustration scales down to `45vh` to maintain clean visual whitespace.
* **Mobile Viewport (`max-width: 768px`):** * **Link Exclusion:** The structural link layout menu (`.nav-links`) switches to `display: none` to instantly remove text crowding, leaving only the corporate Logo and User profile identification pill visible in the top navbar.
  * **Vertical Stacking:** The main hero grid switches to `flex-direction: column`. This neatly drops the graphic illustration beneath the copy container in a single centralized vertical track.