# Dataset

This folder contains data versioned using Dvc.

DO NOT ADD THE CONTENT OF THIS FOLDER TO GIT

ONLY README IS TRACKED


# How to Use

Inside Dataset you have a dummy example on how you need to configure your Data disposition. For classification

Dataset/\
-------->cls1\
------------->img1.jpg\
-------->cls2\
------------->img1.jpg\
-------->clsN\
------------->img1.jpg

Remove example folder with your own images


N.B 

For training, train e val dataset are splitted automatically using k-fold cross validation. Default split is 5 means 80% train e 20% validation
