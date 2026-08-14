# Lab 05: Inline CSS Styling & Centralized External CSS Containers

**Course:** Web Technology Lab & Cloud Computing Applications – I Lab  
**Course Code:** 25SACS070P / 25BCC100P  
**Covered Merged Exp:** Merged Exp 5 `[Covers: 25SACS070P Exp 10, 11, 13 | 25BCC100P Exp 10, 11]`  
**Target Duration:** 2 Hours (120 Minutes Continuous Lab)  
**Scaffolding Method:** 100% Scratch Coding (Blank File)  

---

## 1. Lab Session Objectives & Target Output
By the end of this 2-hour lab session, students will be able to:
1. Apply inline CSS (`style=""`) to format text colors, background colors, and paragraph styling.
2. Extract inline styles into a centralized external stylesheet (`style.css`) linked via `<link>`.
3. Group paragraphs under shared CSS class selectors (`.highlight-card`).
4. Construct a centered `<div>` container rule set to set background color to `#f2f2f2`, center content horizontally/vertically, and restrict width to 80% `[Covers: SACS Exp 13]`.

---

## 2. 120-Minute Lab Time Breakdown

| Time Range | Duration | Activity & Teaching Strategy |
|---|---|---|
| **00:00 - 00:15** | 15 Mins | **Visual Target & Wireframe Briefing:** Show unstyled page vs page styled with external CSS and centered container. |
| **00:15 - 00:45** | 30 Mins | **Guided Live-Coding Part I (Inline to External):** Code inline styled page, then create `style.css` and link via `<link>`. |
| **00:45 - 01:15** | 30 Mins | **Guided Live-Coding Part II (Centered Container Rule):** Write the exact `#f2f2f2` centered div rule set taking 80% parent width. |
| **01:15 - 01:45** | 30 Mins | **Independent Student Challenge ("You Do"):** Add a second CSS class `.alert-box` and apply it to a new container. |
| **01:45 - 02:00** | 15 Mins | **Troubleshooting & Viva Sign-off:** Troubleshoot broken CSS file paths and class syntax, conduct viva Q&A, sign lab record. |

---

## 3. UI Wireframe & Centered Container Layout

```mermaid
graph TD
    subgraph Viewport (Browser Window)
        subgraph Centered Container div (width: 80%, margin: 0 auto, bg: #f2f2f2)
            H1["Heading: Centered Container Box"]
            CARD1["Div Class: .highlight-card (Light blue box)"]
            CARD2["Div Class: .highlight-card (Light blue box)"]
        end
    end
```

---

## 4. Code Scaffolding Setup

> [!IMPORTANT]
> Students will create two files from scratch: `index.html` and `style.css` in the same directory.

---

## 5. Step-by-Step Guided Implementation Code Walkthrough

#### File 1: External CSS Stylesheet (`style.css`)
```css
/* style.css - Centralized External Stylesheet */

/* Global Body Styling */
body {
    font-family: Arial, sans-serif;
    background-color: #eef2f5;
    margin: 0;
    padding: 20px;
}

/* Centered Container Rule Set (Exp 13 Task) */
.centered-container {
    background-color: #f2f2f2;
    width: 80%;
    margin: 40px auto; /* Centered horizontally */
    padding: 30px;
    border: 1px solid #cccccc;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    text-align: center; /* Centered text content */
}

/* Shared Paragraph Class Rule */
.highlight-card {
    background-color: #ffffff;
    border-left: 5px solid #008CBA;
    padding: 15px;
    margin: 15px 0;
    text-align: left;
}

.bold-text {
    font-weight: bold;
    color: #003366;
}
```

#### File 2: HTML Web Page (`index.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>External CSS & Centered Container - Lab 05</title>
    
    <!-- Task: Link External CSS File -->
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Task: Centered 80% Width Div Container -->
    <div class="centered-container">
        
        <h1>Centralized CSS Styling Demo</h1>
        <p class="bold-text">Department of Computer Science & Applications</p>

        <!-- Grouped Class Paragraphs -->
        <div class="highlight-card">
            <h3>Web Technology Module</h3>
            <p>
                This card demonstrates <span style="color: red; text-decoration: underline;">inline CSS overrides</span> 
                combined with shared external class styling.
            </p>
        </div>

        <div class="highlight-card">
            <h3>Cloud Computing Module</h3>
            <p class="bold-text">
                Modifying the style.css file instantly updates all cards sharing the .highlight-card class!
            </p>
        </div>

    </div>

</body>
</html>
```

---

## 6. Student Extension Challenge Task ("You Do")

**Task Requirements (Time: 30 Mins):**
1. Add a new class `.alert-card` in `style.css` with a light red background (`#f8d7da`) and dark red left border (`#721c24`).
2. Add a third `<div>` container in `index.html` using the `.alert-card` class displaying `"Notice: Practical Exam Registration Deadline is Friday"`.
3. Verify that changes saved in `style.css` instantly reflect on `index.html` upon browser refresh.

---

## 7. Common Bugs & Troubleshooting Guide

* **Bug 1: External CSS styles do not apply to the HTML page at all.**
  * *Cause:* Incorrect filename in `<link href="...">` tag (e.g. `styles.css` instead of `style.css`) or missing `rel="stylesheet"`.
  * *Fix:* Check filename spelling and ensure `<link rel="stylesheet" href="style.css">` is inside `<head>`.
* **Bug 2: Centered container fails to center horizontally.**
  * *Cause:* Missing `margin: 0 auto;` or element does not have a defined `width` (e.g., width 100% cannot be centered).
  * *Fix:* Set explicit `width: 80%;` combined with `margin: 0 auto;`.

---

## 8. Viva Voce Oral Questions & Answers

1. **Q: How does `margin: 0 auto;` center a block element horizontally?**  
   *A:* The `auto` value instructs the browser to calculate equal left and right margins automatically based on the remaining viewport space.
2. **Q: What is the main advantage of External CSS over Inline CSS?**  
   *A:* External CSS allows styling rules to be reused across hundreds of HTML pages from a single `.css` file, separate from HTML structure.
