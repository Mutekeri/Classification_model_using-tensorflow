# Classification_model_using-tensorflow
This are codes for any classification problem, using tensorflow

# Platform

Anaconda, jupyter notebook

# Notice

I give credit to https://github.com/MicrocontrollersAndMore
who had a simple tutorial which actually worked, but it works for only pictures under 500, so you will comment the errors and
you can still run many images without errors. His code was only limited to the flowers and the bikes he provided. As long as yo have the 
.jpg smaller pictures. This code should be able to run. Make sure you are using tensorflow version 1..probably the last one. Even though 
they are pushing to version 2.0 The models are still running in version 1, you will have many errors, until they announce the models have been updated, we can all migrate. I certified in version 2.0 and using the google collab version, and struggled to even get on program running in my own machine. Also being to use the models already available. 

# Steps
1. Download images
2. Download Google flower images
3. Download your own images
4. Separate out some test images
5. Run the upload.ipynb, edit it to your file location
6. Run retrain.ipynb
7. Run test.ipynb

# Download your own images

If you’d like to use your own images, create a directory “(repository_location)\training_images”, then create a directory for each classification you’d like, then download at least 105 images of each type.

For example, if you’d like to classify a... vs b..., create the directories “(repository_location)\training_images\...” and “(repository_location)\training_images\....”, then download at least 105 images of each and save them to the applicable directories.

The images can be different sizes, but should be roughly square, and not especially large or small (i.e. substantially bigger than 50 x 50 and substantially smaller than 4000 x 4000).

The retrain.ipynb script we will run in the next few steps may encounter an error is there are other files or directories inside each training directory that contains images, so take care to assure that only .jpg images are in each training images directory.  In other words, for example, “(repository_location)\training_images\road_bikes” and “(repository_location)\training_images\...” should only contain .jpg images, not other file types or other directories.

# Separate out some test images

Create a directory “(repository_location)\test_images”.  For each of the directories for the classifications in your (repository_location)\training_images directory, choose at least 2 images and move (don’t copy) them into (repository_location)\test_images.  Note that we are separating out the images we will use before training (the next step) so the images we test on will not have been used for training.

# Loading files to jupyter notebook

There are 2 ways to load the files:
1. Open jupyter notebook and create a file, change it to a name of your liking. Then load the 3 files or codes to your folder (upload.ipynb, retrain.ipynb, test.ipynb). Edit the upload.ipynb to your zipped files (training_images and test_images). Make sure you remove extra folders after extracting. By using the move function in jupyter notebook until you can only click once on the folder and get the intended content.
2. You can open the C:\Users\name\folder\project folder and literally load the training_images and test_images without using zip files. Run jupyter notebook again. The files will appear.


# Run retrain.ipynb

The file (repository_location)\retrain.py is a refactored version of this file from the TensorFlow GitHub:

https://github.com/tensorflow/tensorflow/blob/master/tensorflow/examples/image_retraining/retrain.py

The refactorings are for improved readability and also to make using the command line not necessary.

Open (repository_location)\retrain.py in your chosen Python editor and give it a quick skim.  I moved the parameters that can be specified from the  if __name__ == '__main__':  statement at the very bottom of the script to the “module level variables” section at the top.  This should make things more user-friendly for Windows users who may not be used to using the command line.  Note that there are more than 20 parameters that can be specified, which allows for a great variety of customization options, however the defaults that I’ve chosen should be good to start with.

retrain.py is more than 1,000 lines long so it’s not necessary to read the entire file, but at a minimum it would be recommended to verify the TRAINING_IMAGES_DIR and TEST_IMAGES_DIR variables correctly matches your image directories locations.  When you’re ready, go ahead and run retrain.ipynb.

Depending on your computer’s horse power, the training process will probably take 20-30 minutes.

Take a quick glance at (repository_location), note that many files will have been downloaded/created from running retrain.ipynb

# Run test.ipynb

In (repository_location) open test.ipynb in your chosen jupyter notebook.  Verify the file and directory paths at the top are correct for your computer, then run the script.  The script will open each image in TEST_IMAGE_DIR in an OpenCV window and show the classification results on standard out.

Done!!

# Extra

If you’d like to make the accuracy better, the 2 general steps to accomplish this would be:
1) Use more training images.  500-1,000 may seem like a lot, but considering the variety of these images, more would be better.  10,000+ images would not be too many.
2) In retrain.ipynb, set the how_many_training_steps parameter to something higher than 500.  Google’s default is 4000.  This will make the training take longer, however.






