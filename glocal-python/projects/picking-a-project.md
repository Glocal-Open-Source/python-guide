# Guide to Open Source Project Creation

Now that you have foundational and intermediate Python skills, it is time to put them to the test! We challenge all of our volunteers to shoot for the stars and build something universally useful. The goal of an open-source project isn't just to practice coding; it is to create a utility that helps real people solve real problems.

```{note}
Your script **does not** need to be overly complex! The best tools solve a real, recurring problem that people face, and do so in a way that others can realistically reuse or adapt. 
```

When building your project, try to use **only Python’s built-in libraries** (`os`, `csv`, `json`, `datetime`) to keep solutions accessible. If you *must* use external libraries like `pandas` or `requests`, ensure that your project clearly lists those requirements in a `requirements.txt` file or verifies they are installed upon the first run.

**How to create a `requirements.txt` file:**
The absolute easiest way to build one is to open your terminal (with your virtual environment activated) and run:
```bash
pip freeze > requirements.txt
```
This command automatically scans your project and generates the text file natively, locking in the exact versions of the libraries you used! Anyone who clones your project can then instantly install everything required to make it run by typing `pip install -r requirements.txt`.

---

## Identifying the Problem

If you aren't sure what to build, look for friction. The best scripts automate pain away.

**Common problems people face that could easily be automated:**
- Repeating the exact same manual administrative steps every week or month.
- Translating information that exists but is hard to organically interpret or summarize.
- Handling lists or records that become chronically outdated and difficult to maintain.
- Dealing with inconsistent formatting that constantly causes confusion or systemic errors.
- Simple operational processes breaking down at scale (more people, more entries, etc.).
- Wasting endless hours on copying, checking, or reorganizing rigid information.
- Non-technical users struggling to interact with structured data outputs.

## Project Brainstorming

If you still need a spark, here are some illustrative ideas to get you started!

**Example Ideas:**
- Automatically generating reminders, summaries, or checklists parsed from basic data files.
- Scripts that turn raw lists or CSVs into highly readable outputs (tables, text summaries, HTML reports).
- Standardizing inconsistent inputs across a dataset (aggregating names, standardizing dates, categories, labels).
- A diagnostic tool that automatically flags missing, duplicated, or suspicious entries across massive datasets.
- Translating hyper-structured data (like JSON blocks) into simple "at-a-glance" visual readouts to help administration make quick decisions.
- Reducing the overarching need for manual human oversight in routine workflows.
- **Building a brand new open-source dataset for others to use!** For example, writing a script that scrapes unformatted tables from civic government websites, using `pandas` to aggressively standardize the data into clean columns, and exporting the result natively as a beautifully formatted `.csv` file!

```{warning}
**Already Completed Projects**
Before you begin, check to make sure you aren't reinventing the wheel! The following utilities have already been built by our community:
- Automated file sorting and organization using Python.
- Universal PDF Converter (Translating to `.txt`, `.docx`, `.md`, `.html`, `.svg`, or images with an interface).
- Universal CSV data cleaning scripts.
```

---

## Sharing Your Work

Once you have built your tool or generated your new diagnostic dataset, it is time to deploy it!

### Sharing Scripts & Automation
Upload your Python script to a public GitHub repository so that others in the civic data space can view, reuse, or freely adapt your logic. Make sure your repository contains a `README.md` that includes a brief explanation of the problem it solves, how to run it, and how it might help others.

Upon completing your repository and receiving approval, your tool may be officially designated and featured on the **GLOCAL Open Source Library**: 
[https://github.com/dbiel-77/awesome-glocal](https://github.com/dbiel-77/awesome-glocal)

### Sharing Open Data
If your project revolved around building and exporting a highly structured dataset from scratch, consider uploading the final CSV/JSON artifact directly to an open research platform like **[Kaggle](https://www.kaggle.com/)** or **[HuggingFace Datasets](https://huggingface.co/datasets)** so that data scientists and civic analysts worldwide can ingest it into their models immediately!

### Log Your Impact
Finally, make sure your hard work is officially documented! Any time spent brainstorming, building, and deploying your project counts heavily towards your volunteer footprint. 

Please head to [volunteer.youcount.ca](https://volunteer.youcount.ca) and submit your project completion task directly here:
**[Submit Project Task #38465705](https://volunteer.youcount.ca/admin/tasks/38465705-d70f-4d32-b238-37233731ae31)**

```{tip}
Don't be afraid to document your code aggressively! The more comments you leave explaining *why* you wrote a block of logic a certain way, the easier it is for a beginner to adapt your tool to their local area!
```
