# DMI Portfolio Website (Static HTML/CSS)

This repository contains a clean, professional-looking **static portfolio website** used in **DevOps Micro Internship (DMI)** Week 1 to practice:
- Linux basics
- Nginx hosting
- Deployment proof / ownership
- Production-style checks

✅ Students deploy this website on an Ubuntu VM using Nginx and keep it live for 24 hours.

---

## Who is this for?
- DMI students (beginner → intermediate)
- Anyone learning how to host a static site with Nginx on Linux

---

## What you will build
A portfolio-style website hosted on:
- **Ubuntu VM**
- **Nginx**
- Accessible via: `http://<public-ip>`

---

## Mandatory Ownership Proof (DMI Rule)
Before you deploy, you MUST edit the footer and add your details:

Original:

```html
<p>Crafted with <span>cloud</span> excellence by Pravin Mishra</p>
```

Add this line (example):

```html
<p><strong>Deployed by:</strong> DMI Cohort 2 | Rahul Sharma | Group 4 | Week 1 | 16-01-2026</p>
```

✅ This proof must be visible in your browser screenshot submission.

## Dynamic Date Footer Implementation

To ensure the webpage auto update deploy date, I replaced the static deployment date with a dynamic JavaScript implementation.

### Key Changes
* **Targeting:** Created a `<span>` with the ID `deployDate` in the footer.
* **Automation:** Prompted AI to generate a lightweight JavaScript solution to handle date fetching.
* **User Experience:** When a user visits the site, the date updates automatically to the current date.

### Technical Implementation

**JavaScript Code Used:**
The script uses `window.onload` to ensure the DOM is fully loaded before injecting the date, preventing object-reference errors.
```javascript
<script>
  window.onload = function() {
    const d = new Date();
    const day = String(d.getDate()).padStart(2, '0');
    const month = String(d.getMonth() + 1).padStart(2, '0');
    const year = d.getFullYear();

    document.getElementById("deployDate").textContent = `${day}-${month}-${year}`;
  };
</script>