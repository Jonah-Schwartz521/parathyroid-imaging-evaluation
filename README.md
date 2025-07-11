# INFO 2201 Final Project: ENT Imaging and Concordance Analysis by Jonah Schwartz & Jeshua Dimawea

## Overview

This project focuses on the analysis of pre-operative imaging modalities — including 4D CT, SPECT/CT, Ultrasound, Sestamibi, and MRI — and compares them to surgical findings in order to assess localization accuracy and clinical value. The goal is to evaluate how well different imaging techniques align with surgical outcomes, and identify patterns in anatomical measurements that may influence side concordance.

The dataset used in this project was structured and cleaned from raw imaging data and includes metrics related to anatomical positioning, laterality (left/right), and concordance with actual surgical results.


## Week 4 – Data Source Reflection

### Where are we getting this data from?

For our final project, we are using a dataset created as part of an ENT (ear, nose, throat) imaging analysis project. The data was originally collected and cleaned by our group using raw measurements and imaging results. This dataset focuses on measurements and comparison values from head CT scans, including variables related to side concordance, imaging angles, and anatomical distances between specific points in the head.

The data was accessed and processed through Jonah's Github, where it was organized across multiple `.xlsx` files. These files include both raw imaging data and cleaned versions with derived metrics and categorizations.

---

### What data type is it?

The dataset is in **Excel (.xlsx)** format, containing structured, tabular numerical and categorical data. Each sheet includes columns like patient ID, anatomical measurements, side classification (left/right), and concordance labels, all suitable for statistical analysis and visualization using Python (mainly pandas and matplotlib).

---

### What are the restrictions of our data type?

Some challenges of working with `.xlsx` files include:
- Needing to **manually inspect and understand multiple sheets** to piece together the complete picture
- Making sure data types are consistent across sheets (e.g., ensuring numeric values weren’t stored as strings)
- **Handling missing or inconsistent values**, especially in the raw imaging sheet
- Having to manually track derived columns that were added post-collection, since metadata or documentation is limited

---

### ⚖Pros and cons in terms of accessibility

**Pros**:
- We have full access and permission to use the data, since it was developed within our group.
- The dataset is relatively clean and well structured, making it easy to analyze in Python.
- Since it was collected and cleaned directly, we know exactly what each variable means and how it was derived.

**Cons**:
- This dataset is not publicly available or hosted on a data portal like Kaggle or the CDC, so outside users can’t directly replicate the collection process.
- There's limited formal documentation, so some variable definitions had to be clarified manually.
- Because it involves medical imaging data, some insights may require domain knowledge to interpret correctly.
