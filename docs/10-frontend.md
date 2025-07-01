# 10 – Frontend & 3D UI

## Technology

- **Three.js** for rendering 3D bubbles
- **Cannon.js** for physics (gravity, collisions)
- HTML/CSS for login and detail modals

## Bubbles

- Each wish is a bubble
- Size = upvotes
- Mass = net score (up - down)
- Position = physics-controlled
- On grant → pop animation
- On expire → dissolve or fade

## Interaction

- Users can drag, shake, and rotate view
- Bubbles clickable → opens wish detail
- Granting and voting done via modals

## Layout

- Scene loads all active wishes
- Polling checks for updates
- New bubbles animate in
