![SIQ Matrix Banner](assets/SIQ_Matrix_Banner.png)

# SIQ Matrix

> A custom Power BI Matrix visual with hierarchical headers, flexible sorting, cell gradients, in-cell data bars, and drillthrough.

**Current version: 1.0.4.3** — Adds cell background gradients and fixes blank rows and columns reappearing when a colour measure is added. See the [Changelog](CHANGELOG.md) for release details.

---

## 📦 Installation

1. Download the latest `SIQ_Matrix.pbiviz` file from the [Releases](https://github.com/gabechisholm/BetterMatrix/releases) page.
2. Open **Power BI Desktop** or **Power BI Service**.
3. In the **Visualizations** pane, click **···** (More options) -> **Import a visual from a file**.
4. Choose the downloaded `.pbiviz` file.

---

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

* **Hierarchical Headers**: Expand and collapse row/column groups with inline indicators.
* **Field Order / Model Sort**: Keep the column order supplied by Power BI, including the order of measures in Values and model-defined category sorting.
* **Date/Time Formatting**: Display standard date/time formats such as `G` and `g` correctly, including the time component, alongside custom date formats and dynamic cell format strings.
* **In-Cell Data Bars**: Visualise magnitude directly inside cells with positive/negative colouring and zero-axis lines.
* **Cell Background Gradients** — Shade numeric cells by their relative value within each row, each column, or the whole matrix.
* **Row Selection and Drillthrough** — Select rows with the mouse or keyboard and open Power BI's drillthrough menu from a row.
* **5 Style Presets**: Instantly apply `Default`, `Minimal`, `Bold Header`, `Alternating Rows`, or `Contrast` layouts.
* **Specific Column Overrides** — Choose a column by name and customise its header, values, or both. Use fixed colours or DAX colour measures.
* **Built-in Search Controllers**: Independent toggles for row keyword search and value-based query filtering (e.g. `>100`, `<=500`).
* **Blank Row Control**: Toggle whether to show or hide blank/empty data rows.
* **Alternate Row Colors**: Stripe colouring with custom background color picker.
* **Multi-Format Exports**: Export pivoted layout or unpivoted raw summaries to CSV or Excel directly from the UI.

---

## 🎨 Formatting Options

Access the following settings inside the **Format visual** pane:

* **Layout and style presets**: Set the overall look (`Default`, `Minimal`, `Bold Header`, `Alternating Rows`, `Contrast`).
* **Grid**: Toggle horizontal/vertical gridlines, configure line weight/color, separator styling, and adjust row padding.
* **Values**: Adjust font family, size, colors, alignments, and set numeric display units and decimal places.
* **Column & Row Headers**: Adjust typography, custom header labels, stepped layout indent depth, and expand/collapse icon colors.
* **Column Header Sorting**: Choose ascending or descending sorting for the smallest category tier, or enable **Use field order / model sort** to preserve Power BI's supplied order.
* **Column & Row Grand Totals**: Toggle subtotals/totals, change position (left/right/top/bottom), customize labels, and format fonts and colors.
* **Cell elements**: Configure positive/negative data bar colors and zero-axis lines.
* **Gradient** — Set **Gradient mode** to **Row by row**, **Column by column**, or **Whole matrix**. The start and end colours map to the lowest and highest visible numeric values in that scope. Blank cells and totals keep their existing styling. Choose **Off** to disable the gradient.
* **Row Search**: Style the search inputs, background, border colors, text size, and adjust layout offsets.

---

## 🖱 Row Selection and Drillthrough

The **Drill through** and **Clear selection** buttons are hidden by default. Enable either independently under **Drill Through**. Both buttons share the font, background and border settings in **Function Button**.

Click a row to select it, Ctrl/Cmd-click to select multiple rows, or use Enter/Space on a focused row. Use **Clear selection** to reset. With one row selected, click **Drill through** to open Power BI's native menu, or right-click a row. Configure a destination report page with drillthrough fields matching the matrix's Rows fields; Power BI controls which destinations appear. Selection also supports report drillthrough buttons.

Under **Drill Through**, enable **Open drillthrough menu on row click** to open the destination menu immediately, even with both buttons hidden.

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
