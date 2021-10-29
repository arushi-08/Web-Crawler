# Web-Crawler

Introduction
------------

Extracts datasheets for Individual Parts from MAXIM, STMI and CUI manufacturer websites.


Usage
------------

Python 3.6+, Selenium frameworks, and rest of the libraries are listed in the Requirements.txt file.

Open terminal, activate virtual environment and start jupyter notebook:
```
.\env\Scripts\activate
jupyter notebook
```
Leave this command prompt open in the background. It starts the jupyter notebook in web browser automatically.
In jupyter notebook, open ‘WebCrawlingAutomation.ipynb’ file.

Provide input to program and run the cells.

Working
------------

1. DataSheet is opened in Pandas DataFrame, and divided into batches whose size is set to 20 parts. If this batch size is to be changed, the chunkSize inside ‘splitDFIntoSmalldf( )’ function should be changed.
2. Web Browser is launched using Selenium Driver, and this browser’s object is created. 
3. The object is used to call functions for interacting with the Manufacturer website. For the project, the object is only for navigating through website and finding datasheet.
4. For MAXIM and STMI: Once relevant PDF file of a part opens using the browser object, the PDF’s url is saved in a Python list.
After a batch completes and we have PDF urls of 20 parts in the list, then for each PDF’s url, an HTTP request is sent to the server and the pdfs are saved using Requests library.
5. For CUI: wkhtmltopdf library is used to convert urls into PDF files. pdfkit library interacts 	with wkhtmltopdf in python.
