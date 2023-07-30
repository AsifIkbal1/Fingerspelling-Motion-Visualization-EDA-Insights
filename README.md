# Fingerspelling-Motion-Visualization-EDA-Insights
Fingerspelling Motion Visualization:EDA + Insights

## What is American Sign Language Fingerspelling Recognition ?

American Sign Language Fingerspelling Recognition is a technology that uses computer vision and machine learning algorithms to recognize and interpret the hand gestures used in American Sign Language (ASL) fingerspelling. It can be used to create tools and applications that help people with hearing impairments to communicate more effectively with others. The technology involves comparing the input image of the hand gesture to a pre-defined set of templates, extracting relevant features from the input image, or training a neural network on a large dataset of ASL fingerspelling images to learn the patterns and features that are most important for recognition. Despite some challenges, ASL Fingerspelling Recognition has the potential to greatly improve the lives of people with hearing impairments.

## Data Overview

### Files
#### [train/supplemental_metadata].csv


* path - The path to the landmark file.
* file_id - A unique identifier for the data file.
* participant_id - A unique identifier for the data contributor.
* sequence_id - A unique identifier for the landmark sequence. Each data file may contain many sequences.
* phrase - The labels for the landmark sequence. The train and test datasets contain randomly generated addresses, phone numbers, and urls derived from components of real addresses/phone numbers/urls. Any overlap with real addresses, phone numbers, or urls is purely accidental. The supplemental dataset consists of fingerspelled sentences. Note that some of the urls include adult content. The intent of this competition is to support the Deaf and Hard of Hearing community in engaging with technology on an equal footing with other adults.

### character_to_prediction_index.json

#### [train/supplemental]_landmarks/ 
The landmark data. The landmarks were extracted from raw videos with the MediaPipe holistic model. Not all of the frames necessarily had visible hands or hands that could be detected by the model.
The landmark files contain the same data as in the ASL Signs competition (minus the row ID column) but reshaped into a wide format. This allows you to take advantage of the Parquet format to entirely skip loading landmarks that you aren't using.

* sequence_id - A unique identifier for the landmark sequence. Most landmark files contain 1,000 sequences. The sequence ID is used as the dataframe index.
* frame - The frame number within a landmark sequence.
* [x/y/z]_[type]_[landmark_index] - There are now 1,629 spatial coordinate columns for the x, y and z coordinates for each of the 543 landmarks. The type of landmark is one of ['face', 'left_hand', 'pose', 'right_hand']. Details of the hand landmark locations can be found here. The spatial coordinates have already been normalized by MediaPipe. Note that the MediaPipe model is not fully trained to predict depth so you may wish to ignore the z values. The landmarks have been converted to float32.
