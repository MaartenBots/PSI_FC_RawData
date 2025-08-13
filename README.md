# PSI\_FC\_RawData

**TAR File Sorting and Packaging Notebook**
This repository contains a Python notebook designed to help you sort .tar files from Google Drive, generate a CSV file with metadata, compress the results, and clean up temporary files. The workflow is intended to be run entirely in Google Colab, so you can process large datasets without installing anything locally.

**Workflow Overview**
The notebook follows four main steps:

**1. Mount Google Drive and Upload TAR Files**

* The first step mounts your Google Drive inside the Colab environment so that the notebook can access files directly from your storage.
* This method ensures that large files do not need to be uploaded directly into Colab’s limited temporary storage.

---

**2. Sort the TAR Files and Create a CSV Path List**

* The notebook automatically searches for .tar files in the specified folder.
* Each TAR file is opened, and relevant information is extracted.
* A CSV file is generated that contains the mapping between the TAR file names, their original locations, and their assigned categories/groups. This CSV acts as a record of the processing and allows quick reference later without re-extracting the files.

---

**3. Create a ZIP Archive of the Sorted Data and Download It**

* Once sorting is complete, the notebook packages all processed/sorted files into a single .zip archive.
* This archive can be downloaded directly from Colab to your local machine.

---

**4. Delete Temporary and Uploaded Files from Google Drive**

* To save storage space in Google Drive, the notebook includes a cleanup step.
* It automatically deletes all files that were uploaded and processed during the session.
* This keeps your Drive organized and ensures no unnecessary data is left behind after processing.
* Do make sure that the Trash/bin is emptied as well, else they will still take up space for your Google Drive.

---

**Why Use This Notebook?**

* No local setup needed – Run everything in Google Colab with just a browser.
* Handles large files – Works directly with Google Drive storage, avoiding Colab’s size limits.
* Automated sorting – Quickly categorizes files based on internal contents or naming patterns.

---

**Input Requirements**

* TAR archives (.tar, .tar.gz, .tgz) containing the files you want to process.
* Sufficient Google Drive storage space for both the uploaded files and the processed outputs.

---

**Output Files**

* sorted\_data.zip – The compressed archive containing all sorted files.
* file\_paths.csv – A CSV listing each TAR file, its original path, and its assigned category.

---

**Need Help?**
If you encounter any issues or have questions, feel free to open an issue or contact the author.

---
