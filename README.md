# 🧾 Small Business GST Invoicing & Compliance Engine 📊

A statutory tax utility designed to automate place-of-supply tax classification (CGST + SGST vs. IGST) and calculate exact base values for inclusive or exclusive pricing structures under Indian GST law.

🔗 **[Live Demo](https://ng410782-cell.github.io/gst-invoice-engine/)**

---

## 🌟 Key Features

- **Automated Place of Supply Logic:** Automatically detects whether a transaction is Intrastate (same state $\rightarrow$ CGST + SGST) or Interstate (different state $\rightarrow$ IGST).
- **Inclusive vs. Exclusive Pricing Engine:** Computes exact base prices and tax components whether tax is added on top or extracted from a lump-sum amount.
- **Compliance Output:** Generates a structured tax invoice breakdown complete with HSN/SAC code tracking and tax slab splits (5%, 12%, 18%, 28%).
- **Indian Currency Formatting:** Displays all figures using standard Indian numbering format (`₹`).

---

## 📐 Statutory Logic & Formulas

### 1. Tax-Exclusive Computation
$$\text{Base Amount} = \text{Input Price}$$
$$\text{GST Amount} = \text{Base Amount} \times \left( \frac{\text{Rate}}{100} \right)$$

### 2. Tax-Inclusive Computation (Tax Extraction)
$$\text{Base Amount} = \frac{\text{Total Inclusive Price}}{1 + \left( \frac{\text{Rate}}{100} \right)}$$
$$\text{GST Amount} = \text{Total Inclusive Price} - \text{Base Amount}$$

### 3. Tax Classification Rule
$$\text{Supply Type} = \begin{cases} \text{CGST } \left(\frac{\text{Rate}}{2}\right) + \text{SGST } \left(\frac{\text{Rate}}{2}\right), & \text{if Seller State} = \text{Buyer State} \\ \text{IGST } (\text{Rate}), & \text{if Seller State} \neq \text{Buyer State} \end{cases}$$

---

## 🛠️ Built With

- **HTML5 & CSS3** – Clean, responsive UI layout
- **JavaScript (ES6)** – Statutory tax logic and DOM rendering
- **GitHub Pages** – Automated continuous deployment
