# RPA-EXPERIMENT-13
### Name: SARGURU K
### Reg No: 212222230134
## AIM:
   To automate the extraction of key information (Invoice Number, Date, and Total Amount) from a scanned invoice PDF using OCR technology in UiPath and store the extracted data into an Excel file.

## ALGORITHM:
Step 1: Prepare the Project Create a new project in UiPath Studio called InvoiceOCRBot.
* Place your Invoice PDF in the project folder for easy access.
Step 2: Read the Invoice using OCR Use the Read PDF with OCR activity (from UiPath.PDF.Activities).
* Set the file path to your invoice PDF.
* Use Tesseract OCR or Microsoft OCR engine.
* Output: ocrText (String variable)
Step 3: Extract Data Using Regex Use Assign activities to extract data:
invoiceNumber = System.Text.RegularExpressions.Regex.Match(ocrText, "Invoice Number[:\s]*([A-Za-z0-9\-]+)").Groups(1).Value  
invoiceDate = System.Text.RegularExpressions.Regex.Match(ocrText, "Date[:\s]*([0-9\/\-]+)").Groups(1).Value  
totalAmount = System.Text.RegularExpressions.Regex.Match(ocrText, "Total Amount[:\s]*([\d,]+\.\d{2})").Groups(1).Value
Step 4: Create and Write to Excel Use a Build Data Table activity to create a table with columns: Invoice Number, Date, Total Amount
* Use Add Data Row to insert extracted values.
* Use Write Range activity to save the data to InvoiceData.xlsx.
Step 5: Run and Verify Run the bot.
* Open the InvoiceData.xlsx file to check if the data is entered correctly.
  
## PROGRAM:
![image](https://github.com/user-attachments/assets/9c994a98-3a51-464d-a8cf-c11c90185d3d)
![image](https://github.com/user-attachments/assets/c6828a13-196c-468d-a7fe-315da265bfe0)

## OUTPUT:
![image](https://github.com/user-attachments/assets/0ba2ab75-cc5c-47b6-8eeb-6aba80316f17)

## RESULT:
The UiPath robot successfully extracted key data from an image-based PDF using OCR and saved it in an Excel file for further use.
