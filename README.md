# INFO 2201 Final Project: ENT Imaging and Concordance Analysis by Jonah Schwartz & Jeshua Dimawea

## Overview

This project focuses on the analysis of pre-operative imaging modalities, including 4D CT, SPECT/CT, Ultrasound, Sestamibi, and MRI, and compares them to surgical findings in order to assess localization accuracy and clinical value. The goal is to evaluate how well different imaging techniques align with surgical outcomes, and identify patterns in anatomical measurements that may influence side concordance.

This project used a dataset that was organized and cleaned from raw imaging data. It has metrics for anatomical positioning, laterality (left/right), and matching real surgical results.

<br><br>

## Data Source Reflection

## Data Pulling
### Where are we getting this data from?

For our final project, we are using a dataset created as part of an ENT (ear, nose, throat) imaging analysis project. The data was originally collected and cleaned by our group using raw measurements and imaging results. This dataset focuses on measurements and comparison values from head CT scans, including variables related to side concordance, imaging angles, and anatomical distances between specific points in the head.

The data was accessed and processed through Jonah's Github, where it was organized across multiple `.xlsx` files. These files include both raw imaging data and cleaned versions with derived metrics and categorizations.

---

### What data type is it?

The dataset is in Excel (.xlsx) format and contains organized tables with numbers and categories. Each sheet includes columns like patient ID, anatomical measurements, side classification (left/right), and concordance labels, all suitable for statistical analysis and visualization using Python (mainly pandas and matplotlib).

---

### What are the restrictions of our data type?

Some challenges of working with `.xlsx` files include:
- Needing to **manually inspect and understand multiple sheets** to piece together the complete picture
- Making sure data types are consistent across sheets (e.g., ensuring numeric values weren’t stored as strings)
- **Handling missing or inconsistent values**, especially in the raw imaging sheet
- Having to manually track derived columns that were added post-collection, since metadata or documentation is limited

---

### Pros and cons in terms of accessibility

**Pros**:
- We have full access and permission to use the data, since it was developed within our group.
- The dataset is pretty clean and well organized, which makes it simple to use Python to examine.
- We know exactly what each variable means and how it was found because it was collected and cleaned by hand.

**Cons**:
- This dataset isn't open to the public or housed on a data portal like Kaggle or the CDC, so outside users can't directly replicate the process of collecting it.
- Some insights may need domain knowledge to be interpreted properly because they involve medical imaging data.

<br><br>

## Data Cleaning
<br><br>

## Daily Progress Log #1 – Data Preparation

### What We worked on today:
- Loaded the raw imaging dataset into a pandas DataFrame
- Inspected the column names and fixed an issue with whitespace in the `'Age '` column
- Identified rows and found age data was missing
- Checked for other missing values across imaging modality columns
- Cleaned up the dataset and saved a cleaned version

### Notes:
- Will move on to making visualizations and doing analysis in a new notebook to keep this one focused on just pulling and cleaning
