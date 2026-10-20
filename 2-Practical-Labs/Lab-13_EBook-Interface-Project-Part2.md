# Lab 13: Interactive E-Book Interface Development Project (Part 2)

**Course:** Web Technology Lab & Cloud Computing Applications – I Lab  
**Course Code:** 25SACS070P / 25BCC100P  
**Covered Merged Exp:** Merged Exp 11 (Session 2 of 2) `[Covers: 25SACS070P Exp 26 | 25BCC100P Exp 23]`  
**Target Duration:** 2 Hours (120 Minutes Continuous Lab)  
**Scaffolding Method:** Skeleton Project Template  

---

## 1. Lab Session Objectives & Target Output
By the end of this 2-hour lab session, students will be able to:
1. Construct a split-screen E-Book reader web application layout (Left Chapter Navigation Panel, Right Content Display Panel).
2. Utilize JavaScript event listeners to dynamically load and display chapter text when chapter names are clicked.
3. Manage active chapter highlight states visually using CSS `.active-chapter` classes.
4. Implement an interactive E-Book Web Interface `[Covers: SACS Exp 26 | BCC Exp 23]`.

---

## 2. 120-Minute Lab Time Breakdown

| Time Range | Duration | Activity & Teaching Strategy |
|---|---|---|
| **00:00 - 00:15** | 15 Mins | **Visual Target & Project Briefing:** Demonstrate clicking left chapter list items to instantly load chapter text on the right panel without page reload. |
| **00:15 - 00:45** | 30 Mins | **Guided Live-Coding Part I (Layout):** Build split-screen CSS layout (`#chapter-menu` 30% width, `#content-display` 70% width). |
| **00:45 - 01:15** | 30 Mins | **Guided Live-Coding Part II (JS Chapter Switching):** Create JavaScript object/array holding chapter data and write `loadChapter(chapterId)` function. |
| **01:15 - 01:45** | 30 Mins | **Independent Student Challenge ("You Do"):** Add Chapter 4 ("Server-Side PHP Scripting") and Chapter 5 ("MySQL Database Connectivity"). |
| **01:45 - 02:00** | 15 Mins | **Troubleshooting & Viva Sign-off:** Fix JS object lookup errors, conduct viva Q&A, sign lab record. |

---

## 3. UI Wireframe & Data Interaction

```mermaid
graph LR
    subgraph E-Book Reader Interface
        subgraph Left Menu (#chapter-menu - 30%)
            CH1["Chapter 1: Internet Architecture"]
            CH2["Chapter 2: HTML5 & CSS3"]
            CH3["Chapter 3: JavaScript Programming"]
        end

        subgraph Right Panel (#content-display - 70%)
            TEXT["Dynamic Chapter Title & Text Content rendered via JavaScript"]
        end

        CH1 -->|onclick='loadChapter(1)'| TEXT
        CH2 -->|onclick='loadChapter(2)'| TEXT
        CH3 -->|onclick='loadChapter(3)'| TEXT
    end
```

---

## 4. Code Scaffolding / Project Skeleton

> [!NOTE]
> Provide students with `ebook_reader.html` containing layout structure.

---

## 5. Step-by-Step Guided Implementation Code Walkthrough

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Interactive E-Book Reader - Web Technology</title>
    <style>
        body { font-family: 'Segoe UI', Arial, sans-serif; margin: 0; padding: 0; background-color: #f4f6f9; }
        .ebook-header { background: #003366; color: white; padding: 15px 25px; text-align: center; }
        .ebook-container { display: flex; height: calc(100vh - 80px); }
        
        /* Left Menu Panel */
        #chapter-menu { width: 30%; background: #ffffff; border-right: 2px solid #e0e0e0; overflow-y: auto; }
        #chapter-menu h3 { padding: 15px; margin: 0; background: #e9ecef; border-bottom: 1px solid #ddd; }
        .chapter-item { padding: 15px 20px; border-bottom: 1px solid #f0f0f0; cursor: pointer; transition: 0.2s; }
        .chapter-item:hover { background: #e3f2fd; }
        .chapter-item.active { background: #008CBA; color: white; font-weight: bold; }
        
        /* Right Display Panel */
        #content-display { width: 70%; padding: 40px; background: #ffffff; overflow-y: auto; }
        #content-display h1 { color: #003366; border-bottom: 2px solid #003366; padding-bottom: 10px; }
        #content-display p { line-height: 1.8; font-size: 1.1rem; color: #444; }
    </style>
</head>
<body>

    <div class="ebook-header">
        <h2>Web Technology & Cloud Computing Interactive E-Book</h2>
    </div>

    <div class="ebook-container">
        
        <!-- Left Panel: Chapter Names List -->
        <div id="chapter-menu">
            <h3>Table of Contents</h3>
            <div class="chapter-item active" onclick="loadChapter(1, this)">Chapter 1: Internet Architecture</div>
            <div class="chapter-item" onclick="loadChapter(2, this)">Chapter 2: HTML5 & CSS3 Styling</div>
            <div class="chapter-item" onclick="loadChapter(3, this)">Chapter 3: JavaScript Interactivity</div>
        </div>

        <!-- Right Panel: Dynamic Content Display -->
        <div id="content-display">
            <h1 id="chapter-title">Chapter 1: Internet Architecture</h1>
            <div id="chapter-text">
                <p>The Internet is a global network of interconnected computers communicating via the TCP/IP protocol suite...</p>
            </div>
        </div>

    </div>

    <!-- JavaScript Dynamic Chapter Loading Logic -->
    <script>
        // Data Store holding E-Book Chapter Content
        const ebookData = {
            1: {
                title: "Chapter 1: Internet Architecture & Protocols",
                text: "<p>The Internet is a global network of interconnected computers communicating via the TCP/IP protocol suite. Key protocols include HTTP, HTTPS, DNS, and IP addressing.</p><p>Packet switching ensures high data throughput and network resilience across global routers.</p>"
            },
            2: {
                title: "Chapter 2: HTML5 & CSS3 Layout Design",
                text: "<p>HTML5 provides modern semantic structure using elements like header, nav, section, and article. CSS3 styling enhances presentation through classes, flexbox, and responsive grid layouts.</p>"
            },
            3: {
                title: "Chapter 3: Client-Side JavaScript Programming",
                text: "<p>JavaScript brings dynamic behavior to static web pages. Through Document Object Model (DOM) manipulation, JS handles user click events, validates input forms, and alters page styles in real time.</p>"
            }
        };

        // Function to Load Selected Chapter
        function loadChapter(chapterId, element) {
            const data = ebookData[chapterId];

            if (data) {
                // Update Title and Content
                document.getElementById("chapter-title").innerText = data.title;
                document.getElementById("chapter-text").innerHTML = data.text;

                // Update Active Menu Highlight State
                const items = document.querySelectorAll(".chapter-item");
                items.forEach(item => item.classList.remove("active"));
                element.classList.add("active");
            }
        }
    </script>

</body>
</html>
```

---

## 6. Student Extension Challenge Task ("You Do")

**Task Requirements (Time: 30 Mins):**
1. Add Chapter 4 (`"Chapter 4: Server-Side Scripting with PHP"`) to the `ebookData` object and left menu.
2. Add a `"Next Chapter ->"` button inside the right panel that advances to the next sequential chapter automatically.

---

## 7. Common Bugs & Troubleshooting Guide

* **Bug 1: Clicking a chapter menu item does not update right panel text.**
  * *Cause:* Incorrect array key lookup or typo in `onclick="loadChapter(1, this)"`.
  * *Fix:* Verify that the numerical ID passed to `loadChapter()` matches the key inside the `ebookData` object.

---

## 8. Viva Voce Oral Questions & Answers

1. **Q: How does `innerHTML` differ from `innerText` when updating element content?**  
   *A:* `innerText` treats input strictly as plain text, escaping HTML tags; `innerHTML` parses HTML tags, allowing dynamic rendering of formatted HTML markup.
2. **Q: How does `classList.remove("active")` help manage active states in navigation menus?**  
   *A:* It clears the active highlight class from all menu items before applying it exclusively to the clicked element.
