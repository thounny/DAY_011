# Responsive Overlay Navigation Menu | Responsive Menu

This project is part of my **Daily Code Challenge** series, where I recreate and build captivating web elements. This project focuses on building a **Responsive Overlay Navigation Menu** using **HTML**, **CSS**, and **JavaScript (GSAP)** for smooth animations. The design is inspired by the Awwwards website [Rejouice](https://rejouice.com/).

## Rejouice

Inspired by the beautifully smooth interactions on **Rejouice**, I aimed to implement an overlay navigation with similar visual and functional principles.  
Check it out here: [Rejouice](https://rejouice.com/).

---

## Inspiration

![Inspiration](./assets/DAY_011_1.gif)

---

## Visual Demo

![Visual Demo](./assets/DAY_011_2.gif)

## Features

- **Overlay Navigation**: A modern, full-screen overlay navigation that appears smoothly from the top with a click of a button.
- **Responsive Design**: The menu adapts to all screen sizes, ensuring a consistent user experience on mobile, tablet, and desktop.
- **GSAP Animations**: Smooth transitions and animations are powered by **GSAP** for a polished, professional feel.
- **Phosphor Icons**: The project includes vector icons provided by Phosphor Icons, a flexible and easy-to-use icon library.

---

## Project Structure

```bash
Responsive-Overlay-Menu/
│
├── assets/
│   ├── DAY_011_1.gif
│   ├── DAY_011_2.gif
│   ├── favicon.ico
│   ├── index_dwn.gif
│   ├── logo1.png
│   ├── miku.gif
│   └── tone.webp
├── styles.css
├── index.html
└── script.js
```

---

## Features Breakdown

- **Overlay Menu Animation**: The navigation opens and closes with a smooth transition using GSAP (GreenSock Animation Platform).
- **Responsive Layout**: The layout is optimized to look great on all screen sizes, from small mobile devices to large desktop screens.
- **Interactive Hover Effects**: Links and buttons feature subtle hover animations for an enhanced user experience.
- **Phosphor Icons**: Easily scalable and customizable icons used within the menu.

---

## Phosphor Icons Integration

This project uses **Phosphor Icons** to display scalable vector icons that are customizable via CSS. The icons are loaded through the following script:

```html
<script src="https://unpkg.com/@phosphor-icons/web"></script>
```

Phosphor Icons is a flexible icon library that provides a wide range of icons, allowing for easy customization. The icons can be styled using CSS properties, making them adaptable to various designs. Here's an example of its usage:

```html
<i class="ph-fill ph-play-circle"></i>
```

The Phosphor Icons library ensures that all icons are scalable and visually appealing across different screen sizes, maintaining consistency in the overall design.

You can check out Phosphor Icons [here](https://phosphoricons.com/).

---

## How to Run

1. **Clone the repository**:

   ```bash
   git clone https://github.com/thounny/DAY_011.git
   ```

2. **Navigate to the project directory**:

   ```bash
   cd DAY_011
   ```

3. **Open the `index.html` file** in your web browser:

   - You can double-click the file in your file explorer, or
   - Serve it using a local development server (e.g., Live Server in VSCode).

---

## JavaScript Breakdown

This project uses **GSAP** to control the opening and closing of the overlay menu, as well as the staggered animations for each of the menu items.

```javascript
document.addEventListener("DOMContentLoaded", function () {
  let tl = gsap.timeline({ paused: true });

  tl.to(".menu-overlay", {
    duration: 0.5,
    clipPath: "polygon(0 0, 100% 0, 100% 100%, 0 100%)",
    ease: "power2.out",
  });

  tl.from(
    ".menu-link, .btn",
    {
      opacity: 0,
      y: 60,
      stagger: 0.05,
      duration: 0.9,
      ease: "power1.inOut",
    },
    "<"
  );

  function openMenu() {
    document.querySelector(".menu-overlay").style.pointerEvents = "all";
    tl.play();
  }

  function closeMenu() {
    document.querySelector(".menu-overlay").style.pointerEvents = "none";
    tl.reverse();
  }

  document.querySelector(".menu-open-btn").addEventListener("click", openMenu);
  document.querySelector(".menu-close-btn").addEventListener("click", closeMenu);
  tl.reverse();
});
```

- **GSAP Timeline**: Handles the smooth animations for the menu overlay and staggered animations for each of the navigation links.
- **Menu Toggle**: The JavaScript listens for the "open" and "close" button clicks to trigger the timeline animations.

---

## Technologies Used

- **HTML5**: For the structure of the navigation menu and layout.
- **CSS3**: For the design, layout, and responsiveness of the menu.
- **JavaScript (ES6)**: For managing the interactivity and triggering the animations.
- **GSAP (GreenSock Animation Platform)**: For creating the smooth menu transitions and animations.
- **Phosphor Icons**: For easily customizable and scalable icons.

---

![Logo](./assets/index_dwn.gif)

## Author

**Thounny Keo**  
Frontend Development Student | Year Up United

![miku](./assets/miku.gif)
