# Lab 07: Responsive Web Design using Bootstrap Grid Layout & E-Commerce Page

**Course:** Web Technology Lab & Cloud Computing Applications – I Lab  
**Course Code:** 25SACS070P / 25BCC100P  
**Covered Merged Exp:** Merged Exp 7 (Part 1) `[Covers: 25SACS070P Exp 17 | 25BCC100P Exp 14]`  
**Target Duration:** 2 Hours (120 Minutes Continuous Lab)  
**Scaffolding Method:** Scaffolded Starter Template (`TODO:` Comment Placeholders)  

---

## 1. Lab Session Objectives & Target Output
By the end of this 2-hour lab session, students will be able to:
1. Link Bootstrap 5 CDN stylesheets and scripts into an HTML document.
2. Master Bootstrap Grid Container System (`container`, `row`, `col-md-4`, `col-sm-6`).
3. Build responsive product cards using Bootstrap `.card` components.
4. Construct a responsive Online Shopping / E-Commerce Product Listing Web Page `[Covers: SACS Exp 17 | BCC Exp 14]`.

---

## 2. 120-Minute Lab Time Breakdown

| Time Range | Duration | Activity & Teaching Strategy |
|---|---|---|
| **00:00 - 00:15** | 15 Mins | **Visual Target & Grid Briefing:** Show desktop 3-column shopping grid vs mobile 1-column responsive layout. |
| **00:15 - 00:45** | 30 Mins | **Guided Live-Coding Part I (Bootstrap Setup & Grid):** Open starter file. Link Bootstrap 5 CDN (`TODO: 1`) and create `.container` and `.row` (`TODO: 2`). |
| **00:45 - 01:15** | 30 Mins | **Guided Live-Coding Part II (Product Cards):** Complete `TODO: 3` building Bootstrap `.card` components with images, titles, prices, and buy buttons. |
| **01:15 - 01:45** | 30 Mins | **Independent Student Challenge ("You Do"):** Add a 4th product card to the grid and customize button colors (`btn-success`). |
| **01:45 - 02:00** | 15 Mins | **Troubleshooting & Viva Sign-off:** Fix broken grid column math (`col` total $> 12$), conduct viva Q&A, sign lab record. |

---

## 3. UI Wireframe & Responsive Grid System

```mermaid
graph TD
    subgraph Bootstrap Grid (.container -> .row)
        C1["Col 1 (.col-md-4)<br/>Product Card 1: Laptop"]
        C2["Col 2 (.col-md-4)<br/>Product Card 2: Smartphone"]
        C3["Col 3 (.col-md-4)<br/>Product Card 3: Headphones"]
    end
```

---

## 4. Code Scaffolding / Starter Template

> [!NOTE]
> Provide students with this starter file (`bootstrap_shopping_starter.html`).

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>E-Commerce Shopping Page - Lab 07 Starter</title>

    <!-- TODO 1: Link Bootstrap 5 CSS CDN -->

</head>
<body>

    <div class="text-center my-4">
        <h2>TechStore - E-Commerce Shopping</h2>
        <p class="text-muted">Responsive Bootstrap Shopping Layout</p>
    </div>

    <!-- TODO 2: Create Bootstrap Container and Row -->
    
    <!-- TODO 3: Create Responsive Product Cards using col-md-4 -->

    <!-- TODO 4: Link Bootstrap 5 JS Bundle CDN -->

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
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TechStore - E-Commerce Shopping Page</title>

    <!-- Step 1: Bootstrap 5 CSS CDN -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-light">

    <div class="container my-5">
        
        <div class="text-center mb-5">
            <h1 class="fw-bold text-primary">TechStore Electronics</h1>
            <p class="lead text-secondary">Discover top deals on laptops, smartphones & accessories</p>
        </div>

        <!-- Step 2: Bootstrap Grid Row -->
        <div class="row g-4">
            
            <!-- Step 3: Product Card 1 -->
            <div class="col-12 col-sm-6 col-md-4">
                <div class="card h-100 shadow-sm">
                    <img src="https://via.placeholder.com/300x200" class="card-img-top" alt="Laptop">
                    <div class="card-body">
                        <h5 class="card-title">Pro Developer Laptop</h5>
                        <p class="card-text text-muted">Intel i7, 16GB RAM, 512GB SSD. Perfect for Web & Cloud coding.</p>
                        <h6 class="text-success fw-bold">₹65,000</h6>
                        <button class="btn btn-primary w-100 mt-2">Add to Cart</button>
                    </div>
                </div>
            </div>

            <!-- Product Card 2 -->
            <div class="col-12 col-sm-6 col-md-4">
                <div class="card h-100 shadow-sm">
                    <img src="https://via.placeholder.com/300x200" class="card-img-top" alt="Smartphone">
                    <div class="card-body">
                        <h5 class="card-title">5G Smartphone Pro</h5>
                        <p class="card-text text-muted">6.7" AMOLED Display, 128GB Storage, Triple Camera.</p>
                        <h6 class="text-success fw-bold">₹28,999</h6>
                        <button class="btn btn-primary w-100 mt-2">Add to Cart</button>
                    </div>
                </div>
            </div>

            <!-- Product Card 3 -->
            <div class="col-12 col-sm-6 col-md-4">
                <div class="card h-100 shadow-sm">
                    <img src="https://via.placeholder.com/300x200" class="card-img-top" alt="Headphones">
                    <div class="card-body">
                        <h5 class="card-title">Wireless Headphones</h5>
                        <p class="card-text text-muted">Active Noise Cancellation, 30 Hours Battery Backup.</p>
                        <h6 class="text-success fw-bold">₹4,999</h6>
                        <button class="btn btn-primary w-100 mt-2">Add to Cart</button>
                    </div>
                </div>
            </div>

        </div>
    </div>

    <!-- Step 4: Bootstrap 5 JS Bundle CDN -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>

</body>
</html>
```

---

## 6. Student Extension Challenge Task ("You Do")

**Task Requirements (Time: 30 Mins):**
1. Add a 4th product card for `"Wireless Gaming Mouse"` with price `"₹1,499"`.
2. Add a Bootstrap Badge `<span class="badge bg-danger">HOT SALE</span>` inside the card title.
3. Change the button class on Product Card 1 to `btn-warning` (Yellow).

---

## 7. Common Bugs & Troubleshooting Guide

* **Bug 1: Grid columns do not align horizontally in a row.**
  * *Cause:* Student forgot to wrap column `<div>` elements inside a parent `<div class="row">`.
  * *Fix:* Ensure all `.col-*` elements are direct children of a `.row` container.
* **Bug 2: Cards have uneven heights across the row.**
  * *Cause:* Cards contain varying amounts of description text without flex stretch.
  * *Fix:* Apply class `h-100` (`height: 100%`) to the Bootstrap `.card` container.

---

## 8. Viva Voce Oral Questions & Answers

1. **Q: How many total column units exist in the standard Bootstrap Grid System?**  
   *A:* The Bootstrap grid system is based on a 12-column layout.
2. **Q: What does the class `col-md-4` mean in Bootstrap responsive grid design?**  
   *A:* On medium screen sizes ($\ge 768\text{px}$) and larger, the element occupies 4 out of 12 columns ($33.33\%$ width), creating a 3-column row layout.
