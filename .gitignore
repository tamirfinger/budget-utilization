# Step 1 - Upload files from local machine to Google Colab
from google.colab import files
uploaded = files.upload()
# 'uploaded' is a dictionary containing filenames as keys and file content as values

#Step 2 - Install required package
!pip install PyMuPDF
# Import PyMuPDF for PDF reading
import fitz # fitz is the module inside PyMuPDF used to handle PDFs

#Step 3 - Define the function to check required keywords in PDFs
def check_documents (pdf_path):
    required_keywords = [׳תבר׳, ׳התחייבות׳, ׳כרטיס פרויקט׳]
    found = {key: False for key in required_keywords}

#Step 4 - Iterate through pages and search for keywords
with fitz.open(pdf_path) as doc:
     for page in doc:
         text = page.get_text("text")
         for key in required_keywords:
             if key in text:
                found[key] = True
return found

#Step 5 - Save the uploaded file to Colab environment
file_name = list(uploaded.keys())[0]
with open(file_name.'wb') as f:
     f.write(uploaded[file_name])

#Step 6 - Run the check function on the uploaded file and print results
results = check_documents(file_name)
print(results)
