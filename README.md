# EE4211 Group Project

CD into Kaggle Folder:
1. Running generate.ipynb (should've been just a script) to convert pascal VOC format of the given csv file to a YOLO format file for each image's labeling.

2. Then generate test.txt and train.txt which is also from the generate.ipynb

3. obj.data and obj.names just google how to make it lol

4. List of things to copy:
/kaggle/data/obj to /darknet/data/
yolov4-obj.cfg to /darknet/cfg
obj.data and obj.names to /darknet/data
test.txt and train.txt to /darknet/data

Then CD into the darknet folder:
1. Run ./darknet detector train data/obj.data cfg/yolov4-obj.cfg yolov4.conv.137 -dont_show -mjpeg_port 8040 -map > output.txt
in the terminal

you can open "insert-machine-ip:8040" to see the realtime chart training with the image

this part took me ~4 hours

2. You can put an image in the /darknet folder to test the detection rate with the command below
./darknet detector test data/obj.data cfg/yolov4-obj.cfg yolov4.conv.137 > output-test.txt

then it will ask you to input the image's name including the file format