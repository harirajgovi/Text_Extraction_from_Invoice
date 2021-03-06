                                                         Text-Extraction 

Problem_Statement-
    
    Prepare a model to extract Total amount, Tax amount(If available), Invoice Number, Invoice Date from Invoices
    

ABSTRACT:

    NLP[Natural language processing] is one of the important domain now-a-days, due to the amount of data generated by peoples. Here, we tried to extract the required data from the texts/pdf's by filtering the values we need, to solve the problem. came with two different models that takes input as pdf/text file that can able to extract the Total amount, Tax amount(If available), Invoice Number, Invoice Date .
    

METHOD_1:

  INPUT : 

      folder_name:Invoice_PDF -> Invoices in pdf format

  MODEL_STRUCTURE:

      Step 1:
          Converted the raw pdf files into image files in .jpg format and saved in a seperate directory.
      Step 2:
          Used OCR[Optical Character Recognition] to tranform image to text data.
      Step 3:
          Used regex pattern to search & filter out Invoice date, Invoice number, Total amount and Tax amount from the text data generated by OCR.
      Step 4:
         With the regex output used case statements to extract the required data and stored in a dictionary.
      Step 6:
         Then, Used Opencv to draw boundary boxes in the image for the values in the extracted data and the image is saved in output folder.
      Step 7:
         Finally the extracted data in the dictionary format are saved as json format in the output folder.
  
  OUTPUT:

      folder_name:invoice_image -> contains pdf to image converted files

      folder_name:output_image -> contains images having boundary boxes of the extracted values
      
      folder_name:output_json -> contains json files with the extracted data

  PROBLEM_FACED:
    
      1.Time Complexity, takes more time for converting pdf to image and OCR to get text data from image.
      
      2.OCR image to data tranformation gives poor acuuracy results for some invoices(15-20) even after trying some image preprocessing techniques.

METHOD_2:

  INPUT : 

      folder_name:invoice_TXT -> Invoices in text format

  MODEL_STRUCTURE:

      Step 1:
          Used file read to get the data in the text file as string
      Step 2:
          Used NLTK[Natural Language Tollkit] to tokenize the words in the string.
      Step 3:
          Used regex pattern to search & filter out Invoice date, Invoice number, Total amount and Tax amount from the word tokens.
      Step 4:
         With the regex output used case statements to extract the required data and stored in a dictionary.
      Step 5:
         Finally the extracted data in the dictionary format are saved as json format in the output folder.
  
  OUTPUT:

      folder_name:output_json -> contains json files with the extracted data

  PROBLEM_FACED:
    
      1. Text data contains few wrong representation of characters.
        
 

CONCLUSION:
    
    Over these two approaches. The method_2 works well with both accuracy and time complexity over method_1.

    
                      
