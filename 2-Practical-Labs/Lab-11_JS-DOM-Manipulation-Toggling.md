# Lab 11: Dynamic DOM Manipulation (Interactive Text Styling & Toggling Hidden Elements)

**Course:** Web Technology Lab & Cloud Computing Applications – I Lab  
**Course Code:** 25SACS070P / 25BCC100P  
**Covered Merged Exp:** Merged Exp 10 `[Covers: 25SACS070P Exp 23, 24 | 25BCC100P Exp 20, 21]`  
**Target Duration:** 2 Hours (120 Minutes Continuous Lab)  
**Scaffolding Method:** Scaffolded Starter Template (`TODO:` Comment Placeholders)  

---

## 1. Lab Session Objectives & Target Output
By the end of this 2-hour lab session, students will be able to:
1. Access and manipulate Document Object Model (DOM) elements using `document.getElementById()`.
2. Program JavaScript functions to dynamically apply bold, italic, and underline styling based on user actions `[Covers: SACS Exp 23 | BCC Exp 20]`.
3. Create hidden `<div>` elements (`display: none`) and program toggle visibility functions `[Covers: SACS Exp 24 | BCC Exp 21]`.
4. Modify CSS classes dynamically using JavaScript `classList.toggle()`.

---

## 2. 120-Minute Lab Time Breakdown

| Time Range | Duration | Activity & Teaching Strategy |
|---|---|---|
| **00:00 - 00:15** | 15 Mins | **Visual Target & Script Briefing:** Demonstrate clicking formatting buttons to alter text in real time and toggling a hidden info box. |
| **00:15 - 00:45** | 30 Mins | **Guided Live-Coding Part I (Text Formatting):** Open starter file. Complete `TODO: 1` writing JS functions to toggle `fontWeight`, `fontStyle`, and `textDecoration`. |
| **00:45 - 01:15** | 30 Mins | **Guided Live-Coding Part II (Hidden Div Toggle):** Complete `TODO: 2` creating hidden `#secret-div` and toggling `display: block` / `display: none`. |
| **01:15 - 01:45** | 30 Mins | **Independent Student Challenge ("You Do"):** Add color picker buttons (Red, Green, Blue) that change text color dynamically. |
| **01:45 - 02:00** | 15 Mins | **Troubleshooting & Viva Sign-off:** Fix DOM element targeting bugs (`null` reference errors), conduct viva Q&A, sign lab record. |

---

## 3. UI Wireframe & DOM Event Interaction

```mermaid
graph TD
    subgraph User Interactive Dashboard
        TXT["Target Paragraph: 'Web Technology is Dynamic'"]
        BTN_B["Button: Bold"] -->|Triggers makeBold()| TXT
        BTN_I["Button: Italic"] -->|Triggers makeItalic()| TXT
        BTN_U["Button: Underline"] -->|Triggers makeUnderline()| TXT
        
        BTN_TOGGLE["Button: Show/Hide Hidden Div"] -->|Triggers toggleDiv()| HIDDEN["Hidden Div (display: none -> block)"]
    end
```

---

## 4. Code Scaffolding / Starter Template

> [!NOTE]
> Provide students with this starter file (`dom_manipulation_starter.html`).

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Dynamic DOM Manipulation - Lab 11 Starter</title>
</head>
<body>

    <h2>Interactive Text Formatting & Element Toggling</h2>

    <!-- Target Text Paragraph -->
    <p id="sample-text">Mandsaur University Department of CSA - Web Technology Lab</p>

    <!-- TODO 1: Add Formatting Buttons (Bold, Italic, Underline) -->

    <hr>

    <!-- TODO 2: Add Button to Toggle Hidden Div -->
    
    <!-- TODO 3: Create Hidden Div Container (display: none) -->

    <script>
        // TODO 4: Write JS functions for bold, italic, underline, and div toggling
    </script>

</body>
</html>
```

---

## 5. Step-by-Step Guided Implementation Code Walkthrough

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Dynamic DOM Manipulation - Lab 11 Completed</title>
    <style>
        body { font-family: Arial, sans-serif; padding: 30px; background-color: #f4f6f9; }
        .control-panel { background: white; padding: 25px; border-radius: 8px; max-width: 600px; margin: 0 auto; box-shadow: 0 4px 8px rgba(0,0,0,0.1); }
        .sample-box { padding: 15px; border: 1px solid #ddd; margin: 20px 0; font-size: 1.2rem; background: #fafafa; }
        .hidden-box { display: none; background: #d1ecf1; color: #0c5460; padding: 15px; border-radius: 4px; margin-top: 15px; }
        .btn { padding: 8px 15px; margin-right: 5px; cursor: pointer; border: 1px solid #003366; background: #003366; color: white; border-radius: 4px; }
    </style>
</head>
<body>

    <div class="control-panel">
        <h2>Dynamic DOM Styling & Visibility</h2>

        <!-- Target Text Paragraph Element -->
        <div class="sample-box">
            <p id="sample-text">Mandsaur University Department of CSA - Web Technology Lab</p>
        </div>

        <!-- Step 1: Formatting Control Buttons (Exp 23 / BCC Exp 20) -->
        <div>
            <button class="btn" onclick="toggleBold()">Bold</button>
            <button class="btn" onclick="toggleItalic()">Italic</button>
            <button class="btn" onclick="toggleUnderline()">Underline</button>
            <button class="btn" style="background:#dc3545; border-color:#dc3545;" onclick="resetText()">Reset Text</button>
        </div>

        <hr>

        <!-- Step 2: Hidden Div Toggle Button (Exp 24 / BCC Exp 21) -->
        <div>
            <button class="btn" style="background:#28a745; border-color:#28a745;" onclick="toggleHiddenDiv()">
                Toggle Hidden Info Panel
            </button>
        </div>

        <!-- Step 3: Hidden Div Container -->
        <div id="hidden-panel" class="hidden-box">
            <strong>Hidden Content Revealed!</strong> This division container was originally hidden using <code>display: none</code>.
        </div>
    </div>

    <!-- Step 4: DOM Manipulation JavaScript Logic -->
    <script>
        const targetText = document.getElementById("sample-text");
        const hiddenPanel = document.getElementById("hidden-panel");

        // 1. Toggle Bold
        function toggleBold() {
            if (targetText.style.fontWeight === "bold") {
                targetText.style.fontWeight = "normal";
            } else {
                targetText.style.fontWeight = "bold";
            }
        }

        // 2. Toggle Italic
        function toggleItalic() {
            if (targetText.style.fontStyle === "italic") {
                targetText.style.fontStyle = "normal";
            } else {
                targetText.style.fontStyle = "italic";
            }
        }

        // 3. Toggle Underline
        function toggleUnderline() {
            if (targetText.style.textDecoration === "underline") {
                targetText.style.textDecoration = "none";
            } else {
                targetText.style.textDecoration = "underline";
            }
        }

        // 4. Reset Formatting
        function resetText() {
            targetText.style.fontWeight = "normal";
            targetText.style.fontStyle = "normal";
            targetText.style.textDecoration = "none";
        }

        // 5. Toggle Hidden Div Visibility
        function toggleHiddenDiv() {
            if (hiddenPanel.style.display === "block") {
                hiddenPanel.style.display = "none";
            } else {
                hiddenPanel.style.display = "block";
            }
        }
    </script>

</body>
</html>
```

---

## 6. Student Extension Challenge Task ("You Do")

**Task Requirements (Time: 30 Mins):**
1. Add a dropdown menu `<select id="fontSizeSelect">` allowing the user to select font sizes (14px, 18px, 24px, 32px) and update the text size in real time using `onchange`.
2. Update the Toggle Hidden Div button text to dynamically read `"Hide Info Panel"` when visible and `"Show Info Panel"` when hidden.

---

## 7. Common Bugs & Troubleshooting Guide

* **Bug 1: `Uncaught TypeError: Cannot read properties of null (reading 'style')`.**
  * *Cause:* `getElementById("sample-text")` misspelled the ID or script executed before the DOM element loaded.
  * *Fix:* Verify exact ID spelling and ensure scripts are placed at bottom of `<body>` or inside `window.onload`.
* **Bug 2: Click button does not change text style.**
  * *Cause:* Forgotten inline `onclick` handler or spelling mistake in JS function name.
  * *Fix:* Check `onclick="functionName()"` spelling matching JS definition.

---

## 8. Viva Voce Oral Questions & Answers

1. **Q: What is the DOM (Document Object Model) in JavaScript?**  
   *A:* The DOM is an object-oriented tree representation of an HTML document that allows JavaScript to dynamically access, modify, and style web page elements and attributes.
2. **Q: How does toggling `display: none` vs `visibility: hidden` differ?**  
   *A:* `display: none` removes the element completely from layout flow; `visibility: hidden` hides the element visually while retaining its physical space in layout flow.
