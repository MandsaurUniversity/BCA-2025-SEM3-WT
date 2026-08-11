# Lab 02: Hyperlinks, Image Links, Anchor Scrolling & Media Embedding

**Course:** Web Technology Lab & Cloud Computing Applications – I Lab  
**Course Code:** 25SACS070P / 25BCC100P  
**Covered Merged Exp:** Merged Exp 2 `[Covers: 25SACS070P Exp 2, 3, 4, 9 | 25BCC100P Exp 2, 3, 4, 9]`  
**Target Duration:** 2 Hours (120 Minutes Continuous Lab)  
**Scaffolding Method:** 100% Scratch Coding (Blank File)  

---

## 1. Lab Session Objectives & Target Output
By the end of this 2-hour lab session, students will be able to:
1. Create external hyperlinks (`<a>`) with `target="_blank"` pointing to Wikipedia references ("Wi-Fi", "LAN").
2. Wrap images (`<img>`) inside anchor tags (`<a>`) to make clickable navigation images.
3. Construct smoothly scrolling in-page anchor links (`href="#top"`) to jump back to page top.
4. Embed Audio (`<audio>`) and Video (`<video>`) media controls directly into HTML pages.

---

## 2. 120-Minute Lab Time Breakdown

| Time Range | Duration | Activity & Teaching Strategy |
|---|---|---|
| **00:00 - 00:15** | 15 Mins | **Visual Target & Wireframe Briefing:** Demonstrate clicking text/image links, back-to-top scrolling, and playing audio/video controls. |
| **00:15 - 00:45** | 30 Mins | **Guided Live-Coding Part I (Links & Images):** Code `<a>` tags for "Wi-Fi" & "LAN", insert `<img>` and wrap inside `<a>` link. |
| **00:45 - 01:15** | 30 Mins | **Guided Live-Coding Part II (Anchors & Media):** Set `id="top"`, create `<a href="#top">` link, and embed `<audio>` and `<video>` tags. |
| **01:15 - 01:45** | 30 Mins | **Independent Student Challenge ("You Do"):** Add a third link to "Cloud Computing" Wikipedia and embed a video with custom poster image. |
| **01:45 - 02:00** | 15 Mins | **Troubleshooting & Viva Sign-off:** Troubleshoot broken image/media file paths, conduct viva Q&A, sign lab record. |

---

## 3. UI Wireframe & Media Layout

```mermaid
graph TD
    subgraph Web Page Layout (id='top')
        NAV["Text Links: Wi-Fi | LAN (Opens Wikipedia in new tab)"]
        IMG_LINK["Clickable Banner Image -> Navigates to About Page"]
        SPACER["Page Content Body (Long height space)"]
        MEDIA["Media Player: <audio controls> & <video controls>"]
        TOP_LINK["Anchor Link: Back to Top ↑ (Jumps to #top)"]
    end
    NAV --> IMG_LINK --> SPACER --> MEDIA --> TOP_LINK
```

---

## 4. Code Scaffolding Setup

> [!NOTE]
> **Setup Requirement:** Have a sample image (`campus.jpg`), audio file (`sample.mp3`), and video file (`sample.mp4`) in your project folder.

---

## 5. Step-by-Step Guided Implementation Code Walkthrough

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Multimedia & Navigation Lab - Mandsaur University</title>
</head>
<body id="top" bgcolor="#eef2f5">

    <h1>Campus Network & Infrastructure</h1>
    
    <!-- Task 1: Hyperlinks on Wi-Fi and LAN to Wikipedia -->
    <p>
        Our campus is equipped with high-speed 
        <a href="https://en.wikipedia.org/wiki/Wi-Fi" target="_blank">Wi-Fi</a> 
        and high-capacity 
        <a href="https://en.wikipedia.org/wiki/Local_area_network" target="_blank">LAN</a> 
        connectivity for all students.
    </p>

    <!-- Task 2: Clickable Image Link -->
    <p>
        <em>Click the image below to view university main portal:</em><br>
        <a href="https://www.meu.edu.in" target="_blank">
            <img src="campus.jpg" alt="Mandsaur University Campus" width="500" height="280">
        </a>
    </p>

    <hr>

    <!-- Task 3: Embedded Audio and Video Controls -->
    <h2>Departmental Media Gallery</h2>
    
    <h3>1. University Anthem (Audio)</h3>
    <audio controls>
        <source src="sample.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

    <h3>2. Campus Tour (Video)</h3>
    <video width="480" height="270" controls poster="campus.jpg">
        <source src="sample.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

    <!-- Spacer to simulate long page -->
    <div style="height: 500px; margin-top: 20px;">
        <p><em>Scroll down to test in-page back-to-top anchor link...</em></p>
    </div>

    <!-- Task 4: In-page Anchor Jump to Top -->
    <p align="center">
        <a href="#top" style="font-weight: bold; font-size: 1.2rem;">Back to Top of Page ↑</a>
    </p>

</body>
</html>
```

---

## 6. Student Extension Challenge Task ("You Do")

**Task Requirements (Time: 30 Mins):**
1. Add a new hyperlink word `"Cyber Security"` pointing to its Wikipedia page with `target="_blank"`.
2. Add a `loop` attribute to the `<audio>` player so it replays automatically upon finishing.
3. Add a secondary image link at the bottom of the page that returns the user to `index.html`.

---

## 7. Common Bugs & Troubleshooting Guide

* **Bug 1: Video or Audio player shows "Format Not Supported".**
  * *Cause:* Incorrect file path or wrong `type="..."` attribute (e.g., `type="audio/mp3"` instead of `type="audio/mpeg"`).
  * *Fix:* Verify exact file path and use standard MIME types (`audio/mpeg`, `video/mp4`).
* **Bug 2: Clicking image does not open the target webpage.**
  * *Cause:* Nesting order mistake (`<img>` tag closed outside `<a>` tag).
  * *Fix:* Nest `<img ...>` completely inside `<a href="...">...</a>`.

---

## 8. Viva Voce Oral Questions & Answers

1. **Q: What is the purpose of `target="_blank"` in an `<a>` tag?**  
   *A:* It causes the linked webpage to open in a brand new browser tab/window instead of replacing the current page.
2. **Q: How does `<a href="#top">` navigate to the top of a page?**  
   *A:* The `#top` value matches the `id="top"` attribute on the `<body>` tag, instructing the browser to scroll directly to that element ID.
