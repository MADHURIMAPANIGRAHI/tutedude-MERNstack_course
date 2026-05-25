# Task 6: Split-Layout Login Interface

## 1. Project Overview & Layout Objectives
The objective of this task was to build a balanced, split-screen login layout featuring a decorative illustration panel on the left and an interactive form input panel on the right. 

The primary structural goal was to ensure the entire card fits cleanly onto a single screen across different monitor sizes without triggering browser scrollbars, while keeping the interface completely centered.


## 2. Technical Implementation Choices

### Programmatic Centering via CSS Flexbox
Rather than guessing coordinates or applying manual padding hacks to push the login window to the middle of the screen, I used Flexbox on the outer wrapper (`.page-wrapper`):


display: flex;
justify-content: center;
align-items: center;