# Face-Detection
## Steps:
1. Open the necessary_files.txt and go to the drive link. Download input.zip and LICT _YOLO.zip, face_detection.ipynb, prediction_test.ipynb in yoyr latop/pc and unzip then.
2. Go to LICT_YOLO and open data converstion 
3. Open cmd in that folder and type 'pip install -r requirements.txt'
4. Go to main. Open the input folder of main and paste all the files given in the input. 
5. Change the content of class_list.txt to face (Here I have detected face, you can add whatever you want to detect).
6. Open cmd in that folder, type 'python main.py' and press enter.
7. A window will pop up showing the input images.
8. Time to annote the data. Click on the top left corner of the object you want to detect and then click on the bottom right corner of the object,  do not need to drag it.
9. Select all the objects in the image. Here i have annoted 13 faces in the first image. To go to next image press d.
10. Do this for all the input images. When it is done press q to quit.  
11. Go to the output folder and open PASCAL_VOC. Here you will see some xml file generated for every image. 
12. Go back and open YOLO_darknet. Here you will see some .txt file. Copy all the txt files and paste it in the data folder. 
13. Also paste all the input images in the data folder. So your data file will have input images and corresponding .txt file.
14. Now open train_test_conversion and run cmd in that folder. Type 'python process.py' and press enter. You will see two folder generated called train.txt and test.txt 
15. Now go back and go to anchors_calculation and open anchors.py in sublime text. In line 108 give the path of your train.txt file in the format shown there. Example:  '/Users/X/Documents....'.
16. In line 110 give the path of your anchors folder in the previous format where the annotation will be saved.  Save the file and exit. 
17. Run cmd in the anchors_calculation folder, type 'python anchors.py' and press enter. Go to the anchors folder you will see a .txt file is generated. 
18. Now go back and copy the data folder into data_for_colab. 
19. Copy train.txt and test.txt from train_test_conversion and paste into data_for_colab. 
20. Open custom.names and obj.names and change the content to face.
21. Open train.txt file with sublime text. You will see the default path of your input images that you have given is there. But we have to change it to /content/darknet/data_for_colab/data/. Copy it
22. To do this first select the path upto '/User/....data/'. Then press Ctrl+f and then press find all. You will see all the path are now in a single cursor. Replace that with  /content/darknet/data_for_colab/data/. 
23. Do the same thing with test.txt file 
24. Go to  anchors_calculation>anchors>anchor>anchors6.txt and open it. Copy only the first line of the txt file.
25. Go to data_for_colab and open yolov3-tiny-obj.cfg file. In line 134 and 176 paste the coppied anchors deleting the previous ones.
26. Now you have to zip the data_for_colab folder. 
27. Go to your google drive and open a folder called face. 
28. In that folder upload data_for_colab.zip
29. Open face_detection.ipynb with google colaboratory.
30. Run the code cells one by one. 
31. In cell 8 you have to upload the train.txt and test.txt file from your data_for_colab folder. 
33. Continue running the code. 
34. Train the data for 2000 epoch and you can stop it after 2000. 
35. In the flies section you will see a file named darknet. If you press the play button you will see a file name backup open it and you will see some weights file. Download them in the same location you have downloaded input.zip, LICT_YOLO.zip. Also open a text file in the same directory called custom.names.txt and edit the content to face and save it.
36. Run the prediction_test.ipynb file in your jupyter notebook. 
37. The image you want to test has to be in the same path as the prediction_test.ipynb file or you have to change the path in the code.
38. Run all the cells and hopefully you have detected some faces!
