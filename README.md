# Cosmoss Educations - 3D Web Design

## Overview
Cosmoss Educations is a 3D-styled website designed for an online learning platform. It features an interactive navigation bar, a rotating 3D image slider, a well-structured course section, and a responsive design that adapts to different screen sizes.

## Features
- **Navigation Bar**: Contains links to Home, Courses, About, Contact, and authentication buttons (Login/Sign Up).
- **3D Rotating Image Slider**: Uses CSS animations to create a 3D carousel of images.
- **Courses Section**: Displays featured courses with images, descriptions, and links.
- **Responsive Design**: Optimized for different screen sizes, including a mobile menu toggle.
- **Footer**: Contains quick links, contact information, and social media icons.

## Project Structure
```
/ (Root Directory)
|-- index.html (Main HTML File)
|-- style.css (CSS Stylesheet)
|-- images/ (Folder containing images)
    |-- bg.png (Background Image)
    |-- model.png (3D Model Image)
    |-- dragon_1.jpg - dragon_10.jpg (Images for the slider)
    |-- course1.jpg - course3.jpg (Course images)
```

## Code Explanation

### **HTML (index.html)**
1. **Head Section**:
   - Includes meta tags for responsiveness.
   - Links external stylesheets (`style.css`).

2. **Body Section**:
   - **Navigation Bar**: Displays the logo, menu links, and buttons.
   - **3D Image Slider**: Uses `div` elements with images and CSS `perspective` for 3D rotation.
   - **Courses Section**: Showcases available courses with images and descriptions.
   - **Footer**: Contains contact details, quick links, and social media icons.

### **CSS (style.css)**
1. **Global Styles**: Sets default font, margin, and padding.
2. **Navigation Bar**:
   - Uses flexbox for alignment.
   - Implements a dropdown menu for mobile responsiveness.
3. **3D Rotating Slider**:
   - Uses CSS animations (`@keyframes autoRun`) to rotate images in 3D.
   - `transform-style: preserve-3d` is used to maintain depth.
4. **Courses Section**:
   - Uses `flexbox` for layout.
   - Each course card includes an image, title, description, and a button.
5. **Footer**:
   - Contains structured sections with quick links and contact info.

## How to Run
1. Download the project files.
2. Place all images in the `images/` folder.
3. Open `index.html` in a web browser.

## Future Enhancements
- Add backend functionality for authentication.
- Improve animations with JavaScript.
- Enhance the course section with dynamic content from a database.

## Author
**Cosmoss Innovations** - mr anonymous

## License
This project is open-source and can be modified for educational purposes.


## **Detailed Explanation of the HTML Program**
---

## **1. Basic HTML Structure**
```html
<!DOCTYPE html>
<html lang="en">
```
- `<!DOCTYPE html>` declares that this is an HTML5 document.
- `<html lang="en">` sets the language to English.

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3d</title>
```
- `<meta charset="UTF-8">` ensures proper character encoding.
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` makes it responsive.
- `<title>3d</title>` sets the page title.

---

## **2. CSS Styling**
The `<style>` section defines the **background, navbar, and other visual effects**.

### **Global Reset**
```css
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```
- Removes default padding and margin for all elements.
- Uses `box-sizing: border-box;` so padding and border are included in the element’s width.

### **Background Styling**
```css
body {
    background-color: #D2D2D2;
    background-image:
    repeating-linear-gradient(
        to right, transparent 0 100px,
        #25283b22 100px 101px
    ),
    repeating-linear-gradient(
        to bottom, transparent 0 100px,
        #25283b22 100px 101px
    );
}
```
- The body has a light gray `#D2D2D2` background.
- A **grid-like pattern** is created using `repeating-linear-gradient()`.

### **Overlay Image**
```css
body::before {
    position: absolute;
    width: min(1400px, 90vw);
    top: 10%;
    left: 50%;
    height: 90%;
    transform: translateX(-50%);
    content: '';
    background-image: url(images/bg.png);
    background-size: 100%;
    background-repeat: no-repeat;
    background-position: top center;
    pointer-events: none;
}
```
- Adds an **image overlay (`bg.png`)**.
- Uses `absolute` positioning to center it.

---

## **3. Navigation Bar**
```html
<nav class="navbar">
    <div class="logo">Cosmoss Educations</div>
    <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">Courses</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
        <li><a href="#" class="btn-login">Login</a></li>
        <li><a href="#" class="btn-signup">Sign Up</a></li>
    </ul>
    <div class="menu-toggle" onclick="toggleMenu()">☰</div>
</nav>
```
- The **logo and navigation links** (`Home, Courses, About, Contact`).
- **Login & Sign Up** buttons.
- A **hamburger menu (`☰`)** for mobile users.

### **Mobile Menu Toggle (JavaScript)**
```html
<script>
    function toggleMenu() {
        document.querySelector(".nav-links").classList.toggle("active");
    }
</script>
```
- When clicked, the menu **toggles visibility**.

---

## **4. Image Slider (3D Effect)**
```html
<div class="banner">
    <div class="slider" style="--quantity: 10">
        <div class="item" style="--position: 1"><img src="images/dragon_1.jpg" alt=""></div>
        <div class="item" style="--position: 2"><img src="images/dragon_2.jpg" alt=""></div>
        <div class="item" style="--position: 3"><img src="images/dragon_3.jpg" alt=""></div>
        <div class="item" style="--position: 4"><img src="images/dragon_4.jpg" alt=""></div>
        <div class="item" style="--position: 5"><img src="images/dragon_5.jpg" alt=""></div>
        <div class="item" style="--position: 6"><img src="images/dragon_6.jpg" alt=""></div>
        <div class="item" style="--position: 7"><img src="images/dragon_7.jpg" alt=""></div>
        <div class="item" style="--position: 8"><img src="images/dragon_8.jpg" alt=""></div>
        <div class="item" style="--position: 9"><img src="images/dragon_9.jpg" alt=""></div>
        <div class="item" style="--position: 10"><img src="images/dragon_10.jpg" alt=""></div>
    </div>
```
- Displays **10 images in a slider effect**.
- Uses `--position` for controlling the image order.

### **Banner Text**
```html
<div class="content">
    <h1 data-content="CSS ONLY">cosmic educations</h1>
    <div class="author">
        <h2>cosmoss</h2>
        <p><b>Web Design</b></p>
        <p>cosmoss innovations</p>
    </div>
    <div class="model"></div>
</div>
```
- Displays **Cosmic Educations’ title and author details**.

---

## **5. Course Section**
```html
<section class="courses">
    <h2>Our Courses</h2>
    <div class="course-container">
        <!-- Course 1 -->
        <div class="course-card">
            <img src="course1.jpg" alt="Course 1">
            <h3>Artificial Intelligence</h3>
            <p>Learn AI concepts, neural networks, and deep learning.</p>
            <a href="#" class="btn">Learn More</a>
        </div>
```
- Three **courses are listed**: AI, Cybersecurity, and Python.
- Each **course has an image, title, description, and a button**.

---

## **6. Footer Section**
```html
<footer>
    <div class="footer-container">
        <div class="footer-section about">
            <h3>Cosmoss Educations</h3>
            <p>Empowering learners with AI, Cybersecurity, and Programming courses.</p>
        </div>

        <div class="footer-section links">
            <h3>Quick Links</h3>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Courses</a></li>
                <li><a href="#">About Us</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </div>

        <div class="footer-section contact">
            <h3>Contact Us</h3>
            <p>Email: support@cosmossedu.com</p>
            <p>Phone: +91 98765 43210</p>
        </div>

        <div class="footer-section social">
            <h3>Follow Us</h3>
            <a href="#"><i class="fab fa-facebook"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-linkedin"></i></a>
        </div>
    </div>

    <div class="footer-bottom">
        <p>© 2025 Cosmoss Educations. All Rights Reserved.</p>
    </div>
</footer>
```
- Includes **about information, quick links, contact details, and social media icons**.

---

## **Conclusion**
This HTML program creates a **modern educational website** with:
✅ A **navbar** with mobile toggle  
✅ A **background with a 3D grid effect**  
✅ A **slider showcasing images**  
✅ A **course section with details**  
✅ A **footer with contact info & links**  

Sure! I'll explain each and every line of your CSS file in **detail**, so you understand what each part does.

---

## **1. Importing Fonts**
```css
@import url('https://fonts.cdnfonts.com/css/ica-rubrik-black');
@import url('https://fonts.cdnfonts.com/css/poppins');
```
- These lines **import fonts** from an external website (cdnfonts.com).
- The `@import` rule allows us to use custom fonts in our webpage.
- `"ICA Rubrik Black"` and `"Poppins"` fonts will now be available for styling.

---

## **2. Global Styles**
```css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}
```
- `font-family: Arial, sans-serif;` → Uses **Arial** as the primary font, and **sans-serif** as a backup.
- `margin: 0;` → Removes any **default** margin around the webpage.
- `padding: 0;` → Removes any **default** padding inside the webpage.

---

## **3. Navbar (Navigation Bar) Styles**
### **Styling the Navbar**
```css
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #1a1a2e;
    padding: 15px 50px;
    color: white;
}
```
- `display: flex;` → Makes the navbar **flexible**, so items (like logo & links) can be placed easily.
- `justify-content: space-between;` → Spaces out navbar items **evenly** across the screen.
- `align-items: center;` → Aligns all items **vertically centered** in the navbar.
- `background: #1a1a2e;` → Sets the **dark blue background** color for the navbar.
- `padding: 15px 50px;` → Adds **vertical padding (15px)** and **horizontal padding (50px)**.
- `color: white;` → Sets the text color to **white**.

### **Styling the Logo**
```css
.logo {
    font-size: 24px;
    font-weight: bold;
}
```
- `font-size: 24px;` → Increases the logo **text size**.
- `font-weight: bold;` → Makes the logo **bold**.

### **Styling Navbar Links**
```css
.nav-links {
    list-style: none;
    display: flex;
    gap: 20px;
}
```
- `list-style: none;` → Removes **default bullets** from the list.
- `display: flex;` → Makes the links **align in a row**.
- `gap: 20px;` → Creates **space (20px)** between links.

```css
.nav-links li {
    display: inline;
}
```
- `display: inline;` → Ensures each link is displayed **inline** (side by side).

```css
.nav-links a {
    text-decoration: none;
    color: white;
    padding: 8px 15px;
    transition: 0.3s;
}
```
- `text-decoration: none;` → Removes **underline** from links.
- `color: white;` → Sets text color to **white**.
- `padding: 8px 15px;` → Adds **padding** to each link for better clickability.
- `transition: 0.3s;` → Makes the hover effect **smooth**.

```css
.nav-links a:hover {
    background: #0f3460;
    border-radius: 5px;
}
```
- `background: #0f3460;` → Changes background color when hovered.
- `border-radius: 5px;` → Adds **rounded corners** to the hover effect.

---

## **4. Button Styles**
### **Login Button**
```css
.btn-login {
    background: #e94560;
    padding: 8px 15px;
    border-radius: 5px;
}
```
- `background: #e94560;` → Sets a **red color** for the login button.
- `padding: 8px 15px;` → Adds padding inside the button.
- `border-radius: 5px;` → Makes the button **rounded**.

```css
.btn-login:hover {
    background: #d63447;
}
```
- Changes **background color** on hover.

### **Signup Button**
```css
.btn-signup {
    background: #007bff;
    padding: 8px 15px;
    border-radius: 5px;
}
```
- `background: #007bff;` → Sets a **blue color** for the signup button.

```css
.btn-signup:hover {
    background: #0056b3;
}
```
- Changes **background color** on hover.

---

## **5. Mobile Menu (For Smaller Screens)**
```css
.menu-toggle {
    display: none;
    font-size: 24px;
    cursor: pointer;
}
```
- `display: none;` → Hides the menu icon **by default**.
- `font-size: 24px;` → Increases **icon size**.
- `cursor: pointer;` → Makes the cursor **change to a pointer** when hovered.

### **Mobile Menu Activation**
```css
@media screen and (max-width: 768px) {
    .nav-links {
        display: none;
        flex-direction: column;
        background: #1a1a2e;
        position: absolute;
        top: 60px;
        right: 0;
        width: 200px;
        padding: 10px;
    }

    .nav-links.active {
        display: flex;
    }

    .menu-toggle {
        display: block;
    }
}
```
- When **screen size is below 768px**, the navbar turns into a **mobile-friendly menu**.
- `.menu-toggle { display: block; }` → Makes the menu icon **visible**.
- `.nav-links { display: none; }` → Hides links **until menu is clicked**.
- `.nav-links.active { display: flex; }` → When activated, the menu appears.

---

## **6. Banner Section (Main Section)**
```css
.banner {
    width: 100%;
    height: 100vh;
    text-align: center;
    overflow: hidden;
    position: relative;
}
```
- `width: 100%;` → Makes the banner **full width**.
- `height: 100vh;` → Makes the banner **full screen height**.
- `text-align: center;` → Centers the text.
- `overflow: hidden;` → Prevents **extra scrolling**.
- `position: relative;` → Allows positioning **inside the banner**.

### **Rotating Image Slider**
```css
@keyframes autoRun {
    from {
        transform: perspective(1000px) rotateX(-16deg) rotateY(0deg);
    }
    to {
        transform: perspective(1000px) rotateX(-16deg) rotateY(360deg);
    }
}
```
- Creates a **3D rotation effect**.
- The `.slider` will rotate **continuously**.
Absolutely! Let's break down this statement in **detail**:

```css
transform: perspective(1000px) rotateX(-16deg) rotateY(0deg);
```
to
```css
transform: perspective(1000px) rotateX(-16deg) rotateY(360deg);
```

This is part of a **CSS animation** that creates a **3D rotation effect**. It uses three key transformations:

1. **perspective(1000px)** → Adds depth to the 3D effect.
2. **rotateX(-16deg)** → Tilts the element along the X-axis.
3. **rotateY(0deg) → rotateY(360deg)** → Spins the element **fully around** the Y-axis.

---

## **1. `perspective(1000px)` (Depth Effect)**
- The `perspective()` function **creates a sense of depth** by simulating a **vanishing point**.
- `1000px` means the viewer's **eye is 1000 pixels away** from the element.
- A **lower value** (e.g., `300px`) makes objects appear **more dramatic and distorted**.
- A **higher value** (e.g., `2000px`) makes objects appear **flatter**.

Think of it like holding a **book close to your eyes** vs. **far away**—the closer it is, the more perspective distortion you see.

---

## **2. `rotateX(-16deg)` (Tilt on X-Axis)**
- `rotateX()` **rotates the element along the X-axis** (horizontal line).
- `-16deg` means the **top part tilts slightly backward**.
- Positive values (`rotateX(16deg)`) tilt it **forward**.

### 🔹 Example:
- `rotateX(90deg);` → Flips the element **completely flat (horizontal)**.
- `rotateX(0deg);` → Keeps the element **upright**.

---

## **3. `rotateY(0deg) → rotateY(360deg)` (Full Rotation on Y-Axis)**
- `rotateY(0deg);` → Starts with **no rotation**.
- `rotateY(360deg);` → Spins the element **one full turn** (360°).

### 🔹 How it works:
- At the **start** (`from`), the element is at **0 degrees**.
- At the **end** (`to`), the element **rotates 360°** and completes **one full spin**.

---

## **How It Works Together**
### **At the Start (`from`)**
```css
transform: perspective(1000px) rotateX(-16deg) rotateY(0deg);
```
- The element has a **3D depth effect** (`perspective(1000px)`).
- It is slightly **tilted backward** (`rotateX(-16deg)`).
- It is **not rotated yet** (`rotateY(0deg)`).

### **At the End (`to`)**
```css
transform: perspective(1000px) rotateX(-16deg) rotateY(360deg);
```
- The element **completes one full spin** (`rotateY(360deg)`).
- The **tilt remains the same** (`rotateX(-16deg)`, meaning it still leans back slightly).

### **Animation Result**
- The element **tilts slightly backward** and **rotates continuously** in 3D space.
- It looks like a **spinning cube or card**.

---

## **Final Example**
🔹 **Visualizing a Rotating 3D Card**
```css
@keyframes rotateEffect {
    from {
        transform: perspective(1000px) rotateX(-16deg) rotateY(0deg);
    }
    to {
        transform: perspective(1000px) rotateX(-16deg) rotateY(360deg);
    }
}

.animated-box {
    width: 200px;
    height: 200px;
    background: red;
    animation: rotateEffect 5s linear infinite;
}
```
**Explanation**:
- The `.animated-box` spins **every 5 seconds** (`5s`).
- The `linear` animation makes it **rotate at a constant speed**.
- `infinite` makes it **loop forever**.

---

## **Conclusion**
This CSS transformation creates a **3D rotating effect** by:
✅ **Adding depth** using `perspective(1000px)`.  
✅ **Tilting the element** slightly using `rotateX(-16deg)`.  
✅ **Spinning it fully** using `rotateY(0deg → 360deg'
---

## **7. Course Section**
```css
.courses {
    text-align: center;
    padding: 50px 20px;
    background: #f8f9fa;
}
```
- Creates a **course section** with a **light gray background**.

```css
.course-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
}
```
- **Flexbox** ensures courses are arranged neatly.

---

## **8. Footer Section**
```css
footer {
    background: #222;
    color: white;
    padding: 40px 0;
    font-family: Arial, sans-serif;
}
```
- Creates a **dark footer** with **white text**.

```css
.footer-bottom {
    text-align: center;
    background: #111;
    padding: 10px 0;
    font-size: 14px;
    color: #bbb;
}
```
- Bottom section of the footer with **lighter text**.

---

This CSS file builds a **responsive, modern website** with a **navbar, buttons, rotating banner, course section, and footer**.

Let me know if you need **more details** or **modifications**! 🚀 
