Overview:

The fashion industry is going through a quick wave of trend alterations as a result of social media's effect in today's hyperconnected world. 

When it comes to effectively studying and forecasting trends, these ongoing changes in fashion tastes provide considerable difficulties for the apparel industry. 

Due to the manufacture of clothes that don't appeal to consumers, these difficulties result in an astounding amount of clothing waste.

Objective:

With the rise of fast fashion, it is difficult to keep track of ever changing trends.

Our project's main goal is to create a thorough methodology for fashion trend analysis that will enable businesses in the fashion industry to better navigate the always changing world of trends. 

Our initiative seeks to give fashion businesses the resources they need to make knowledgeable decisions, decrease garment waste, and improve industry sustainability by leveraging the power of data analytics and machine learning.

Trend Prediction

The first step is:

a. We gather pictures from Instagram, a social media site with enormous popularity.

b. An account is made that follows some of the most well-known fashion influencers of the present.

b. The Instagram algorithm makes sure that posts are shown in the feed in decreasing order of popularity.

d. Making use of this feature of Instagram, we created a model called "instagram_scraper1.py."

e. "instagram_scraper1.py," the scraper model, produces outputs in the formats "profile.txt," "profiles.csv," and "datetime.csv." The entire list of profile names and the associated timestamps for posts that appeared in the feed are provided by these outputs.

f. Next, we run the command "instagram-scraper -f profile.txt -u perc.eptrons -p Myntra2020 --template datetime--latest-stamps time.txt" from the command line. This operation downloads every image that has been posted since a specific latest timestamp that is given in "time.txt." The outcome is a folder with these downloaded pictures in it.

g. Following that, we execute the notebook "saveimages.py." This gives the open-source program we use a "profile.txt" file, allowing it to download photographs with the supplied custom timestamps and save them in the specified directory.

h. The following GitHub repository is where you may find the open-source software: GitHub Repository Link.

i. With this, the basic dataset needed for later stages has been created.

Semantic segmentation

Due to time restrictions, we choose to pretrain our Mask-RCNN model using COCO weights. We then used about 40,000 photos from the I-Materialist Dataset, which is accessible on Kaggle, to refine the model. Using the Matterport implementation, we put the Mask-RCNN into practice.

This stage results in a segmentation mask that successfully separates the clothing from its surroundings.

Attribute recognition

We use an encoder-decoder model for attribute recognition, where the encoder is the InceptionV3 model and the decoder is based on LSTM architecture.

The model receives these masks as input, creating a feature vector that is later decoded to retrieve the characteristics.

K-Means Clustering is employed to do color detection.

Users will have a choice from a list of the most popular colors and characteristics in the prototype's final output.

Results
A few examples of images obtained using the Mask-RCNN model for semantic segmentation are given below:



A few examples of images obtained after attribute detection using the encoder-decoder model are given below:





Technologies Used
python
OpenCV
Flask
SQL
Jupyter
References

Mask-RCNN original paper : https://arxiv.org/abs/1703.06870 
Matterpost implementation : https://github.com/matterport/Mask_RCNN 
Semantic segmentation model : https://github.com/manas3858/iMat-Fashion/ 
Algorithms: https://ieeexplore.ieee.org/document/9428602
Starter kernel for imat(Kaggle): https://www.kaggle.com/ramswaroopbhakar14/training-inception-v3-for-fashion-attributes
