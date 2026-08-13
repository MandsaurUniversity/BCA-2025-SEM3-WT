# Lab 03: HTML Tables for Time-Table & Infrastructure Layouts, Frame Division

**Course:** Web Technology Lab & Cloud Computing Applications – I Lab  
**Course Code:** 25SACS070P / 25BCC100P  
**Covered Merged Exp:** Merged Exp 3 `[Covers: 25SACS070P Exp 5, 6, 8 | 25BCC100P Exp 5, 6, 8]`  
**Target Duration:** 2 Hours (120 Minutes Continuous Lab)  
**Scaffolding Method:** 100% Scratch Coding (Blank File)  

---

## 1. Lab Session Objectives & Target Output
By the end of this 2-hour lab session, students will be able to:
1. Construct structured HTML tables using `<table>`, `<tr>`, `<th>`, and `<td>`.
2. Apply `colspan` and `rowspan` attributes to merge cells in timetable grids.
3. Design a multi-column HTML page layout using tables describing university infrastructure.
4. Implement a 3-frame layout using `<iframe>` (20% left menu, 60% center body, 20% right remarks).

---

## 2. 120-Minute Lab Time Breakdown

| Time Range | Duration | Activity & Teaching Strategy |
|---|---|---|
| **00:00 - 00:15** | 15 Mins | **Visual Target & Wireframe Briefing:** Demonstrate timetable grid, table-based multi-column layout, and 3-panel iframe structure. |
| **00:15 - 00:45** | 30 Mins | **Guided Live-Coding Part I (Timetable):** Code `<table>` grid for class timetable with `rowspan` for Lunch Break and `colspan` for Labs. |
| **00:45 - 01:15** | 30 Mins | **Guided Live-Coding Part II (Layout & Frames):** Create multi-column infrastructure table and 3-panel `<iframe>` split. |
| **01:15 - 01:45** | 30 Mins | **Independent Student Challenge ("You Do"):** Add a Saturday timetable row and customize frame proportions (25%-50%-25%). |
| **01:45 - 02:00** | 15 Mins | **Troubleshooting & Viva Sign-off:** Fix mismatched `colspan`/`td` cell counts, conduct viva Q&A, sign lab record. |

---

## 3. UI Wireframe & Table Grid Matrix

```mermaid
graph TD
    subgraph 3-Panel Frame Layout (<iframe>)
        F1["Left Frame (20%)<br/>Navigation Links"]
        F2["Center Frame (60%)<br/>Main Timetable & Infrastructure"]
        F3["Right Frame (20%)<br/>Remarks & Notices"]
    end
```

---

## 4. Code Scaffolding Setup

> [!NOTE]
> Students will write `timetable.html` from a blank file and optionally embed it in a main `frames.html` file.

---

## 5. Step-by-Step Guided Implementation Code Walkthrough

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Class Timetable & Infrastructure - Lab 03</title>
</head>
<body>

    <h2 align="center">BCA III Semester Class Timetable</h2>

    <!-- Task 1: Class Timetable Grid -->
    <table border="1" cellpadding="8" cellspacing="0" width="100%">
        <tr bgcolor="#003366" style="color: white;">
            <th>Day / Time</th>
            <th>09:00 AM - 11:00 AM</th>
            <th>11:00 AM - 01:00 PM</th>
            <th>01:00 PM - 02:00 PM</th>
            <th>02:00 PM - 04:00 PM</th>
        </tr>
        <tr>
            <td><strong>Monday</strong></td>
            <td>Web Technology (Theory)</td>
            <td>Cloud Computing Applications</td>
            <td rowspan="3" align="center" bgcolor="#fff176"><strong>LUNCH<br>BREAK</strong></td>
            <td>Web Tech Lab (P1)</td>
        </tr>
        <tr>
            <td><strong>Tuesday</strong></td>
            <td colspan="2" align="center" bgcolor="#e0f7fa">
                <strong>Merged Stream Project Work (SACS + BCC)</strong>
            </td>
            <td>Cloud Computing Lab (P2)</td>
        </tr>
        <tr>
            <td><strong>Wednesday</strong></td>
            <td>System Administration</td>
            <td>Web Technology (Theory)</td>
            <td>Library & Seminar</td>
        </tr>
    </table>

    <br><hr><br>

    <!-- Task 2: Infrastructure Layout using Table -->
    <h2>University Infrastructure Overview</h2>
    <table border="1" cellpadding="12" width="100%">
        <tr bgcolor="#f2f2f2">
            <td width="33%">
                <h3>Computer Labs</h3>
                <p>5 High-Tech computer labs equipped with 200+ Intel i7 systems and high-speed LAN.</p>
            </td>
            <td width="33%">
                <h3>Central Library</h3>
                <p>Over 50,000 books, digital e-journals, and quiet study zones for students.</p>
            </td>
            <td width="33%">
                <h3>Sports Complex</h3>
                <p>Indoor sports hall, cricket ground, basketball courts, and gymnasium.</p>
            </td>
        </tr>
    </table>

</body>
</html>
```

---

## 6. Student Extension Challenge Task ("You Do")

**Task Requirements (Time: 30 Mins):**
1. Add a **Thursday** row to the timetable table where `09:00 AM - 11:00 AM` is reserved for "Cyber Security Lab".
2. Add a `<caption>` tag above the timetable table displaying `"Academic Session 2026-2027"`.
3. Create a secondary HTML file `frames.html` using `<iframe>` elements to divide the screen into 3 vertical panels: Left (20%), Center (60%), and Right (20%).

---

## 7. Common Bugs & Troubleshooting Guide

* **Bug 1: Table columns misalign and push borders out of alignment.**
  * *Cause:* Incorrect `colspan` value or adding extra `<td>` cells in a row where `colspan` was used.
  * *Fix:* Verify that the sum of `<td>` cells + `colspan` values equals the exact number of columns in `<th>`.
* **Bug 2: `rowspan` cell shifts cells in subsequent rows.**
  * *Cause:* Adding a cell in Row 2 for the column position occupied by Row 1's `rowspan`.
  * *Fix:* Omit the cell in Row 2 for the column position that is already spanned from Row 1.

---

## 8. Viva Voce Oral Questions & Answers

1. **Q: What is the difference between `colspan` and `rowspan` in HTML tables?**  
   *A:* `colspan` merges cells horizontally across multiple columns; `rowspan` merges cells vertically across multiple rows.
2. **Q: Why is `cellpadding` used in `<table>` tags?**  
   *A:* `cellpadding` specifies the space between the cell content and the inner cell borders.
