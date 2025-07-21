# INFO-2201 Final Project: ENT Imaging and Concordance Analysis by Jonah Schwartz & Jeshua Dimawea
<br><br>
# Overview

This project focuses on the analysis of pre-operative imaging modalities, including 4D CT, SPECT/CT, Ultrasound, Sestamibi, and MRI, and compares them to surgical findings in order to assess localization accuracy and clinical value. The goal is to evaluate how well different imaging techniques align with surgical outcomes, and identify patterns in anatomical measurements that may influence side concordance.

This project used a dataset that was organized and cleaned from raw imaging data. It has metrics for anatomical positioning, laterality (left/right), and matching real surgical results.

<br><br>

# Data Source Reflection - Week 4

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
---
### What choices did we make?

We started by cleaning up the column names in the dataset, specifically fixing a space issue in the `'Age '` column. Then, we checked for missing values across all columns and found that a few rows were missing age data, while many others were missing values for certain imaging modalities (like MRI or Ultrasound).

We decided to drop the rows where the age was missing, since age is important for any future analysis. For the imaging modality columns, we left the missing values in place because not all patients received every type of scan — so the missing data actually means those scans weren’t done, which is still useful to keep.

---
### What was selected or deleted?

- Identified 2 rows where `Age` was null  
- Removed whitespace from column headers  
- Did not delete any imaging modality columns — even though they had missing data, we kept them to show which tests were or weren’t performed
---
### Why?

We cleaned the dataset so that:
- All column names are properly formatted
- Key fields like `Age` don’t have nulls that could cause issues
- We kept important context in the data

After cleaning, we saved the dataset as `cleaned_data.xlsx`.


<br><br>
# Visualizations Reflection – Week 6
## Our Visualizations

### 



---
### 



<br><br>
# Presentation Reflection – Week 7
## Our Presentation

### We're Done!

We’ve officially wrapped up our presentation on parathyroid imaging after several weeks of research, data cleaning, analysis, and design. The goal was to explore how well different medical scans (like SPECT/CT, 4D CT, Sestamibi, Ultrasound, and MRI) help doctors detect parathyroid issues before surgery.

---
### What We Did

Our story was built around a simple but important question:

> “Which imaging scan gives the most accurate and useful information for parathyroid surgery?”

To answer that, we:
- Pulled real hospital imaging data spanning over 13 years
- Cleaned and organized it for analysis
- Evaluated each imaging type based on five key things:
  - **PPV** (how often the scan is right when it says there's a problem)
  - **Sensitivity** (how well it detects problems when they exist)
  - **Concordance** (how well the scan matched what surgeons found)
  - **Localization** (whether it found the problem at all)
  - **Success rate** (overall usefulness of each scan)

We created clear visuals to help tell the story, showing where each scan type performed well and where it didn’t.

---

### What We Learned

No scan is perfect. Some scans (like Sestamibi) are super reliable when they say something’s there, but they miss a lot of cases. Others (like SPECT/CT) catch more cases but sometimes make mistakes. The best strategy? Combine scans. That gives doctors the best chance of success in surgery.

---

### Why This Matters

Our visual storytelling helps doctors, patients, and even data scientists understand the strengths and weaknesses of these scans. In the real world, this kind of insight can lead to better healthcare decisions and better outcomes for patients.

---

### Final Thoughts

This project helped us practice data storytelling from start to finish finding a story in the data, building the visualizations, and wrapping it all together into a meaningful presentation. We're proud of how it turned out.



<br><br>
# Daily Progress Logs
## Daily Progress Log #1 – Data Preparation

### What We worked on today:

- Loaded the raw imaging dataset into a pandas DataFrame
- Inspected the column names and fixed an issue with whitespace in the `'Age '` column
- Identified rows and found age data was missing
- Checked for other missing values across imaging modality columns
- Cleaned up the dataset and saved a cleaned version

### Notes:
- Will move on to making visualizations and doing analysis in a new notebook to keep this one focused on just pulling and cleaning
---

## Daily Progress Log #2

### What We Worked On Today:

- Reviewed our cleaned imaging dataset (`Clean_imaging_data.xlsx`) and realized it only showed what each scan found, but **not** how that matched up with actual surgical results.
- Discussed that to do analysis like PPV (Positive Predictive Value) and Sensitivity, we need to know **if** each modality (e.g. 4D CT, SPECT, Sestamibi, etc.) correctly matched the surgical findings.
- Decided that we needed to **create new columns** that compare each modality's result to the surgical outcome, like whether it was an **exact match**, **side match**, or **incorrect**.
- Switched focus from just using the cleaned raw data to building a **Modality Concordance** file that adds those comparisons.
- Created a new file `modality_concordance.ipynb` where we generate the match columns for each modality.
- Commented out the save command in `DataPreparation.ipynb`:
  ```python
  # df.to_excel("Data/Clean_imaging_data.xlsx", index=False)

- Instead, we planned to save the final version (with modality comparisons) after building it in the modality concordance notebook.

### Notes:
- We stopped saving the cleaned version right away because it didn’t include the columns that compare scan results to surgery.
- All the analysis (like PPV and Sensitivity) now needs the updated data that shows whether each scan matched what was found in surgery.
