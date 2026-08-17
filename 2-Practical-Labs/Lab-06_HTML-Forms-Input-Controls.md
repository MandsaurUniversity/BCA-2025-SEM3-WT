# Lab 06: HTML Forms, Form Elements & Input Controls

**Course:** Web Technology Lab & Cloud Computing Applications – I Lab  
**Course Code:** 25SACS070P / 25BCC100P  
**Covered Merged Exp:** Merged Exp 6 `[Covers: 25SACS070P Exp 12, 14, 15, 16 | 25BCC100P Exp 12, 13]`  
**Target Duration:** 2 Hours (120 Minutes Continuous Lab)  
**Scaffolding Method:** Scaffolded Starter Template (`TODO:` Comment Placeholders)  

---

## 1. Lab Session Objectives & Target Output
By the end of this 2-hour lab session, students will be able to:
1. Construct HTML forms using `<form action="..." method="POST">`.
2. Utilize text inputs (`text`, `password`, `email`), textareas, radio buttons, checkboxes, dropdown selects, and submit/reset buttons.
3. Group input fields logically using `<fieldset>` and `<legend>`.
4. Apply HTML5 input validation attributes (`required`, `pattern`, `placeholder`, `minlength`).

---

## 2. 120-Minute Lab Time Breakdown

| Time Range | Duration | Activity & Teaching Strategy |
|---|---|---|
| **00:00 - 00:15** | 15 Mins | **Visual Target & Wireframe Briefing:** Show the completed Student Registration Form wireframe with fieldsets. |
| **00:15 - 00:45** | 30 Mins | **Guided Live-Coding Part I (Text & Password Inputs):** Code `<form>`, `<fieldset>`, text inputs, email inputs, and password fields. |
| **00:45 - 01:15** | 30 Mins | **Guided Live-Coding Part II (Controls & Selects):** Add radio buttons for gender, checkboxes for courses, and `<select>` dropdowns. |
| **01:15 - 01:45** | 30 Mins | **Independent Student Challenge ("You Do"):** Add a phone number input with `pattern="[0-9]{10}"` and a reset button. |
| **01:45 - 02:00** | 15 Mins | **Troubleshooting & Viva Sign-off:** Fix missing `name="..."` attributes, conduct viva Q&A, sign lab record. |

---

## 3. UI Wireframe & Form Grouping

```mermaid
graph TD
    subgraph HTML Form (<form action='process.php' method='POST'>)
        subgraph Fieldset 1: Personal Information
            T1["Text Input: Full Name (required)"]
            T2["Email Input: Email Address (required)"]
            T3["Password Input: Account Password"]
            R1["Radio Buttons: Gender (Male / Female / Other)"]
        end
        subgraph Fieldset 2: Academic Details
            S1["Select Dropdown: Stream (SACS / BCC)"]
            C1["Checkboxes: Interests (Web Tech / Cloud / Security)"]
            TA1["Textarea: Permanent Address"]
        end
        BTN["Submit Button & Reset Button"]
    end
```

---

## 4. Code Scaffolding Setup

> [!NOTE]
> Provide students with this starter file (`form_starter.html`).

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Student Registration Form - Lab 06 Starter</title>
</head>
<body>

    <h2>BCA Student Portal Registration</h2>

    <form action="process.php" method="POST">
        
        <!-- TODO 1: Create Fieldset for Personal Information -->

        <!-- TODO 2: Create Fieldset for Academic Details -->

        <!-- TODO 3: Add Submit and Reset Buttons -->

    </form>

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
    <title>BCA Student Registration Form - Lab 06</title>
</head>
<body style="font-family: Arial, sans-serif; background-color: #f4f6f9; padding: 20px;">

    <div style="max-width: 600px; margin: 0 auto; background: white; padding: 25px; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
        
        <h2 style="color: #003366; text-align: center;">Student Portal Registration</h2>

        <form action="process.php" method="POST">
            
            <!-- Personal Info Fieldset -->
            <fieldset style="border: 1px solid #003366; padding: 15px; margin-bottom: 20px; border-radius: 4px;">
                <legend style="color: #003366; font-weight: bold; padding: 0 5px;">Personal Details</legend>
                
                <p>
                    <label for="fullname">Full Name:</label><br>
                    <input type="text" id="fullname" name="fullname" placeholder="John Doe" required style="width: 100%; padding: 8px; box-sizing: border-box;">
                </p>

                <p>
                    <label for="email">Email Address:</label><br>
                    <input type="email" id="email" name="email" placeholder="student@meu.edu.in" required style="width: 100%; padding: 8px; box-sizing: border-box;">
                </p>

                <p>
                    <label for="password">Password:</label><br>
                    <input type="password" id="password" name="password" minlength="6" required style="width: 100%; padding: 8px; box-sizing: border-box;">
                </p>

                <p>
                    <label>Gender:</label><br>
                    <input type="radio" id="male" name="gender" value="Male" checked> <label for="male">Male</label>
                    <input type="radio" id="female" name="gender" value="Female"> <label for="female">Female</label>
                </p>
            </fieldset>

            <!-- Academic Details Fieldset -->
            <fieldset style="border: 1px solid #003366; padding: 15px; margin-bottom: 20px; border-radius: 4px;">
                <legend style="color: #003366; font-weight: bold; padding: 0 5px;">Academic Profile</legend>

                <p>
                    <label for="stream">Specialization Stream:</label><br>
                    <select id="stream" name="stream" style="width: 100%; padding: 8px;">
                        <option value="SACS">System Administration & Cyber Security (25SACS070T)</option>
                        <option value="BCC">Cloud Computing Applications (25BCC100T)</option>
                    </select>
                </p>

                <p>
                    <label>Technical Interests:</label><br>
                    <input type="checkbox" id="web" name="interests[]" value="WebTech"> <label for="web">Web Technology</label>
                    <input type="checkbox" id="cloud" name="interests[]" value="Cloud"> <label for="cloud">Cloud Infrastructure</label>
                    <input type="checkbox" id="security" name="interests[]" value="Security"> <label for="security">Cyber Security</label>
                </p>

                <p>
                    <label for="address">Permanent Address:</label><br>
                    <textarea id="address" name="address" rows="3" style="width: 100%; padding: 8px; box-sizing: border-box;"></textarea>
                </p>
            </fieldset>

            <!-- Action Buttons -->
            <p style="text-align: center;">
                <button type="submit" style="padding: 10px 20px; background: #28a745; color: white; border: none; border-radius: 4px; cursor: pointer;">Submit Application</button>
                <button type="reset" style="padding: 10px 20px; background: #dc3545; color: white; border: none; border-radius: 4px; cursor: pointer; margin-left: 10px;">Reset Form</button>
            </p>

        </form>

    </div>

</body>
</html>
```

---

## 6. Student Extension Challenge Task ("You Do")

**Task Requirements (Time: 30 Mins):**
1. Add a Mobile Number input `<input type="tel">` with regex validation pattern `pattern="[0-9]{10}"` and placeholder `"10-digit phone"`.
2. Add a Date of Birth input `<input type="date" name="dob">`.
3. Verify that submitting the form with an invalid email or short password triggers native HTML5 browser validation popups.

---

## 7. Common Bugs & Troubleshooting Guide

* **Bug 1: Form data fails to reach server script upon submission.**
  * *Cause:* Student forgot to add the `name="..."` attribute to input tags (e.g. `<input type="text">` without `name`).
  * *Fix:* Ensure every input element has a unique `name="..."` attribute.
* **Bug 2: Multiple radio buttons can be selected simultaneously.**
  * *Cause:* Radio buttons have different `name="..."` attributes.
  * *Fix:* Give all radio buttons in the same group the exact same `name="gender"` attribute.

---

## 8. Viva Voce Oral Questions & Answers

1. **Q: What is the purpose of the `<fieldset>` and `<legend>` tags in HTML forms?**  
   *A:* `<fieldset>` visually and semantically groups related form controls together inside a box border; `<legend>` provides a caption title for the box.
2. **Q: Why must radio buttons share the exact same `name` attribute value?**  
   *A:* Sharing the same `name` attribute groups them together so the browser allows only one option to be selected at a time.
