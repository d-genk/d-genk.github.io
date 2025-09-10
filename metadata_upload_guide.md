---
layout: default
title: Metadata Upload Guide
---

## 📄 Metadata Upload Guide

You can improve the accuracy and relevance of automated processing by uploading a small JSON file with additional metadata about your documents. The fields below are optional — include only what you know.

> **Tip:** If you’re unsure about a field, you can leave it out. The system will use defaults automatically.

---

### 📝 `writing_style`

Describes the visual form of the text in the document.

* Options:

  * `"handwritten"`
  * `"printed"`
  * `"typed"`

This helps the system choose between transcription strategies (e.g., handwriting recognition vs. printed text).

---

### 🌍 `language`

The main language(s) used in the document.

* Options:

  * `"english"`
  * `"spanish"`
  * `"portuguese"`
  * `"french"`
  * `"german"`
  * `"mixed"`

---

### 📅 `time_period`

Gives a rough estimate of when the document was created. This can influence how the system interprets spelling, abbreviations, and writing style.

* Options:

  * `"contemporary"`
  * `"mid_20th_century"`
  * `"early_20th_century"`
  * `"19th_century_or_earlier"`

---

### ⚙️ `transcription_preferences`

Specify how you'd like the system to handle certain aspects of transcription. Each setting is optional — include only the ones you want to customize.

* `expand_abbreviations`: `true` to expand abbreviations like "Dr." to "Doctor"
* `preserve_line_breaks`: `true` to keep the original line formatting
* `retain_punctuation_and_spelling`: `true` to preserve original punctuation and spelling
* `normalize_to_modern_language`: `true` to modernize spelling and phrasing
* `ignore_marginalia`: `true` to skip notes in the margins

Defaults:

```json
{
  "expand_abbreviations": false,
  "preserve_line_breaks": true,
  "retain_punctuation_and_spelling": true,
  "normalize_to_modern_language": false,
  "ignore_marginalia": false
}
```

---

### 📐 `layout_structure`

Describes how the text is arranged on the page. This helps guide interpretation of complex layouts.

* Options:

  * `"free_form"`
  * `"paragraphs"`
  * `"lists"`
  * `"tables"`
  * `"forms"`
  * `"mixed"`

---

### 🎨 `non_textual_elements`

List any non-text content that appears in the document. This information can help avoid misinterpreting these as text.

* Options (use an array of values):

  * `"illustrations"`
  * `"stamps_or_seals"`
  * `"handwritten_notes"`
  * `"diagrams"`
  * `"charts_or_graphs"`

Example:

```json
"non_textual_elements": ["illustrations", "handwritten_notes"]
```

---

### 🌈 `color_format`

Indicates the color style of the scanned image. This helps the system calibrate processing.

* Options:

  * `"color"`
  * `"grayscale"`
  * `"black_and_white"`
  * `"mixed"`

---

### ↔️ `orientation`

Specifies how the page is oriented. This helps avoid mistakes when the image isn’t upright.

* Options:

  * `"portrait"`
  * `"landscape"`
  * `"square"`

---

### 🧾 `image_quality_notes`

List any known image quality issues so the system can adapt or flag the content.

* Options (use an array of values):

  * `"blurry"`
  * `"low_contrast"`
  * `"partial_page"`
  * `"includes_fingers"`
  * `"includes_color_checker"`
  * `"damaged_or_stained"`

Example:

```json
"image_quality_notes": ["blurry", "includes_fingers"]
```

---

### ✍️ `description`

A free-text description of the document set. This can provide general context to improve results for both transcription and metadata generation.

Example:

```json
"description": "These are scanned forms from a late 20th-century survey project on urban housing."
```