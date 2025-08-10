# Diff-Gantt

**Diff-Gantt** is a web-based tool for **visualizing row-level changes between two dataset versions** in CSV format. It generates a **timeline (Gantt-style) visualization** of inserts, updates, and deletions, making it easier to understand data evolution over time.

---

## 🚀 Features

* **CSV File Comparison**
  Upload *old* and *new* dataset versions to detect changes.

* **Change Detection**
  Automatically categorizes changes into:

  * **Insert** (New records)
  * **Update** (Modified records)
  * **Delete** (Removed records)

* **Timeline Visualization**
  Interactive Gantt chart showing changes over time.

* **Detailed Change View**
  Click on chart items to view **row details** or **specific field updates**.

* **Automatic Column Detection**
  Attempts to auto-detect primary key and timestamp columns.

* **Accessibility & Responsiveness**

  * Keyboard navigation support
  * Works across light/dark modes
  * Mobile-friendly layout

---

## 📂 Project Structure

```
home.html
```

The entire project is contained in a **single HTML file** with embedded CSS and JavaScript:

* **HTML** – Structure for upload areas, configuration section, results panel, and detail drawer.
* **CSS** – Responsive layout, light/dark theme variables, animations, and component styling.
* **JavaScript** – Core logic for:

  * File upload & validation
  * CSV parsing
  * Diff calculation
  * Interactive Gantt chart rendering
  * Event handling and UI updates

---

## 🛠️ How It Works

1. **Upload Old & New Datasets**
   Drag and drop or select `.csv` files for both the *old* and *new* versions.

2. **Select Columns**
   Choose:

   * **Primary Key Column** (Required) — used to match rows between datasets.
   * **Timestamp Column** (Optional) — used for timeline plotting.

3. **Generate Diff**
   The app:

   * Parses CSV files.
   * Detects inserts, updates, and deletes.
   * Counts changes.
   * Displays a Gantt chart of changes over time.

4. **Inspect Changes**
   Click on chart bars to:

   * View all column values for inserts/deletes.
   * View only changed fields for updates.

---

## 📋 Requirements

* Modern web browser with JavaScript enabled (Chrome, Firefox, Edge, Safari).
* CSV files under **10 MB** each.
* Matching column headers between datasets.

---

## 📦 Installation

This is a client-side app — no server required.

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-username/diff-gantt.git
   cd diff-gantt
   ```

2. **Open in Browser**

   * Simply open `home.html` in your browser.

---

## 🖱️ Usage Example

1. **Old Dataset**

   ```
   id,name,value,date
   1,Apple,10,2024-01-01
   2,Banana,15,2024-01-02
   ```

2. **New Dataset**

   ```
   id,name,value,date
   1,Apple,12,2024-01-01
   3,Cherry,20,2024-01-03
   ```

**Detected Changes:**

* `id=2` → Deleted
* `id=1` → Updated (`value: 10 → 12`)
* `id=3` → Inserted

---

## 🎨 Color Legend

| Change Type | Color  |
| ----------- | ------ |
| Insert      | Green  |
| Update      | Yellow |
| Delete      | Red    |

---

## 🧩 Code Highlights

* **DiffGanttApp Class**

  * Handles file uploads, parsing, diff calculation, and UI updates.

* **GanttChart Class**

  * Draws the interactive timeline.
  * Handles click detection on chart items.

CSV Parsing**

  * Supports quoted fields, escaped quotes, and trimming.
  * Detects duplicate headers and column mismatches.

## 🔒 File Size & Format Validation

Max size: 10 MB
Formats: `.csv`
Primary key uniqueness is validated in both datasets before diff generation.
