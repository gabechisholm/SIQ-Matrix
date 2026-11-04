<div align="center">

<img src="assets/SIQ_Matrix_Banner.png" alt="SIQ Matrix banner">

# SIQ Matrix

**A custom Power BI matrix that puts column sorting within easy reach.**

![Version 1.0.4.3](https://img.shields.io/badge/version-1.0.4.3-2563EB)
![Power BI custom visual](https://img.shields.io/badge/Power%20BI-custom%20visual-F2C811?logo=powerbi&logoColor=black)
![MIT licence](https://img.shields.io/badge/licence-MIT-64748B)

[**Download the visual**](https://github.com/gabechisholm/BetterMatrix/releases) · [Quick start](#-try-it-with-monthly-sales) · [Features](#-features) · [Formatting](#-formatting-options) · [Changelog](CHANGELOG.md)

</div>

---

Put months, products, or any other column category in the order your report needs. Sort the innermost column categories from the visual's header menu, or follow the order defined in your Power BI model. When a reader wants to know who led in March, they can click **March** to sort the rows by that month's values.

| When you want to… | Use… |
|---|---|
| Compare each product against its own monthly results | A **row-by-row gradient** with your choice of start and end colours |
| Find the rows that matter | **Row search** for labels and **value search** for queries like `>=1000` |
| Investigate an outlier | **Drillthrough** from a row to a detail page |
| Share the grid or analyse it elsewhere | **CSV or Excel export** of the current pivoted layout or an unpivoted summary |

> [!NOTE]
> **New in 1.0.4.3** — Cell gradients support row, column, and whole-matrix scales. Colour measures can format cells without bringing back blank rows or columns.

---

## 📦 Installation

1. Download the latest `SIQ_Matrix.pbiviz` file from the [Releases](https://github.com/gabechisholm/BetterMatrix/releases) page.
2. Open **Power BI Desktop** or **Power BI Service**.
3. In the **Visualizations** pane, click **···** (More options) -> **Import a visual from a file**.
4. Choose the downloaded `.pbiviz` file.

---

## 🚀 Try it with monthly sales

| **Rows** | **Columns** | **Values** |
| :---: | :---: | :---: |
| Product | Month | Sales |

1. Add the fields above in **Build visual**.
2. In the visual's **…** menu, enable **Use Field Order / Model Sort** to follow your model's month order. Click a month header to sort products by sales for that month.
3. Open **Format visual → Gradient**, choose **Row by row**, and set the start and end colours. Each product gets its own colour scale, so you can see its strongest and weakest months.

> [!TIP]
> Use **Column by column** to compare products within each month. Use **Whole matrix** when the same sales value should have the same gradient colour everywhere.

## 🗂 Adding Data

Add your fields in the **Build visual** pane. **Function Value** and **Colour measures** are optional.

| Role | Description |
|---|---|
| **Rows** | Category fields that form the row hierarchy (supports multiple levels) |
| **Columns** | Category fields that form the column hierarchy (supports multiple levels) |
| **Values** | Numeric measures to display in the cells |
| **Function Value** | Alternate measures to display using the Function Value button |
| **Colour measures** | DAX measures that supply font or background colours for headers and cells |

---

## ⚡ Key Sorting Features (How to Sort)

SIQ Matrix supports two independent, powerful sorting modes:

| Goal | Control |
|---|---|
| Put the columns themselves in order | Open **… → Sort Columns Ascending** or **Sort Columns Descending** |
| Rank rows by the values in one column | Click that column's leaf header |
| Follow your model's column order | Enable **Use Field Order / Model Sort** |

1. **Sort Rows by Individual Column Values** (Click Column Headers):
   * Click on any individual leaf column header (e.g., a specific date or category) to sort all rows based on the values in that column.
   * Click once to sort **Ascending (▲)**, click again for **Descending (▼)**, and click a third time to clear the sort.
   * Click the row header column to sort alphabetically by row labels.
2. **Sort the Smallest Column Hierarchy Tier** (Header Menu):
   * Click the **…** (Options) button in the visual header bar and choose **Sort Columns Ascending** or **Sort Columns Descending**. Only the smallest category tier sorts within its parent group; parent groups and Values fields retain their order.
   * For example, with **Category → Subcategory** in Columns, Subcategories sort within each Category. Category A stays in its position while its Subcategories change between ascending and descending order.
   * Enable **Use Field Order / Model Sort** in the same menu to preserve the order supplied by Power BI, including Values field order and any model-defined category sort. Choosing ascending or descending disables this toggle. The toggle is also available under **Column headers** in the formatting pane.
   * Subtotals retain their positions, and headers stay aligned with their data cells as columns move.

---

## ✨ Features

### 🧭 Organise the grid

* **Hierarchical Headers**: Expand and collapse row/column groups with inline indicators.
* **Field Order / Model Sort**: Keep the column order supplied by Power BI, including the order of measures in Values and model-defined category sorting.
* **Blank Row Control**: Toggle whether to show or hide blank/empty data rows.

### 🎯 Make patterns stand out

* **Date/Time Formatting**: Display standard date/time formats such as `G` and `g` correctly, including the time component, alongside custom date formats and dynamic cell format strings.
* **In-Cell Data Bars**: Visualise magnitude directly inside cells with positive/negative colouring and zero-axis lines.
* **Cell Background Gradients** — Shade numeric cells by their relative value within each row, each column, or the whole matrix.
* **5 Style Presets**: Instantly apply `Default`, `Minimal`, `Bold Header`, `Alternating Rows`, or `Contrast` layouts.
* **Specific Column Overrides** — Choose a column by name and customise its header, values, or both. Use fixed colours or DAX colour measures.
* **Alternate Row Colors**: Stripe colouring with custom background color picker.

### 🔎 Explore and share

* **Row and Value Search**: Search row labels or filter by values with queries like `>100` and `<=500`.
* **Row Selection and Drillthrough** — Select rows with the mouse or keyboard and open Power BI's drillthrough menu from a row.
* **Multi-Format Exports**: Export pivoted layout or unpivoted raw summaries to CSV or Excel directly from the UI.

---

## 🎨 Formatting Options

| In **Format visual**, open… | To customise… |
|---|---|
| **Layout and style presets** | Choose `Default`, `Minimal`, `Bold Header`, `Alternating Rows`, or `Contrast`. |
| **Grid** | Set gridline visibility, weight and colour, separator styling, and row padding. |
| **Values** | Adjust fonts, colours, alignment, display units, and decimal places. |
| **Column & Row Headers** | Set typography, labels, stepped indentation, and expand/collapse icon colours. Under **Column headers**, sort the smallest category tier or follow model order. |
| **Column & Row Grand Totals** | Set subtotal and total visibility, position, labels, fonts, and colours. |
| **Cell elements** | Set positive and negative data bar colours and the zero-axis line. |
| **Gradient** | Choose **Row by row**, **Column by column**, **Whole matrix**, or **Off**. |
| **Row Search** | Style the search inputs, including backgrounds, borders, text size, and layout offsets. |

> [!TIP]
> The gradient's start and end colours map to the lowest and highest visible numeric values in the selected scope. Blank cells and totals keep their existing styling.

---

## 🖱 Row Selection and Drillthrough

| Action | Control |
|---|---|
| Select one row | Click it, or focus it and press <kbd>Enter</kbd> or <kbd>Space</kbd>. |
| Select multiple rows | Hold <kbd>Ctrl</kbd> or <kbd>⌘</kbd> while clicking. |
| Open the drillthrough menu | Right-click a row, or select one row and click **Drill through**. |
| Reset the selection | Click **Clear selection**. |

> [!IMPORTANT]
> Configure a destination report page with drillthrough fields matching the matrix's **Rows** fields. Power BI determines which destinations appear. Row selection also works with report drillthrough buttons.

<details>
<summary><strong>Show toolbar buttons or open drillthrough on row click</strong></summary>

The **Drill through** and **Clear selection** buttons are hidden by default. Enable either independently under **Drill Through**. Both share the font, background and border settings in **Function Button**.

Enable **Open drillthrough menu on row click** to open the destination menu immediately, even with both buttons hidden.

</details>

---

## 🎨 Column Conditional Formatting

Add a DAX measure returning a hex colour such as `"#FF0000"` or `BLANK()` to **Colour measures** in **Build visual**. These helper measures are hidden from the matrix and exports.

Under **Specific column**, select the target in **Apply to column (name)**. Set **Apply to** to **Header only**, **Values only**, or **Both**, then choose **Font color from measure**, **Background color from measure**, or both. Value cells use their row and column context. Headers use the column-level colour, or a consistent colour from the rows when Power BI omits the column-level result. A blank result keeps the existing colour. A background colour returned by a measure takes precedence over the cell gradient.

---

## 🏢 Author

Made by **[Gabe Chisholm](https://www.linkedin.com/in/gabe-chisholm/)** at [SynapsysIQ](https://www.synapsysiq.co.uk/)

---

## 📄 License

MIT

---

## 💬 Want a dashboard with this functionality and more?

Bring interactive tables like SIQ Matrix into a Power BI dashboard built around how your team works. From tracking key metrics to exploring trends and drilling into the detail, get in touch to discuss what your dashboard could do. [Visit SynapsysIQ](https://www.synapsysiq.co.uk/)
