---
layout: post
title: EEG DATASET ABSTRACT
subtitle: The dataset of electroencephalogram project
---

**The dataset of this project consists of two parts:**

1. **Testing images**. This part contains two kinds of static images. All these images are used to generate confused/non-confused emotions by visually stimulating the volunteer's brain. One consists of 10 peaceful landscape pictures (Used to stimulate non-confusing emotion) and the other consists of 48 complicated reasoning problem pictures (Used to stimulate confusion emotion).
2. **EEG data**. When the volunteers are observing the testing images, eight sensors of the EEG headset collect their brainwave data at a frequency of 250Hz. The EEG data related to every image will be recorded in a single file. So there are 58 files in a experiment subject. Our project contains 25 subjects from 25 volunteers.





## Testing Images

The image set contains 58 pictures (10 **landscape pictures** and 48 **reasoning problem pictures**).

* The selection principle of the landscape picture is that the picture is wide vision, the color is moderate, the light color is brighter, making the volunteer comfortable and clam, like beach, sunset, mountain, river valley, lake and so on.

![Path](/img/path.jpg)

* The reasoning problem pictures are from Raven's Standard Progressive Matrices (SPM). Every picture has a hidden regular pattern. There are 12 standard-level problem pictures and 36 high-level problem pictures in this image set. The selection principle of these pictures is that the picture is clear and the test content is relatively complicated so the volunteer will take time to think about the solution and stay in confusion for a while.

![Logic](/img/logic.jpg)

The testing process takes about 15 minutes and is divided into three parts.

1. **Showing the landscape pictures**. Each picture lasts for 10s and no stop in the process.
2. **Showing the reasoning problem pictures**. When volunteer is ready, the experiment begins. Each picture lasts up to 10s. If the volunteer has already choose an answer, the next picture will appear immediately.
3. **Confidence test**. Replay the second part of the pictures, then the volunteer chooses the options that whether he or she comes up with the answer. So we can find out whether the volunteer is staying in confusion.

![Flow](/img/flow.png)



## EEG Data

* **Original data**. 

  Our project contains 25 subjects. In every file, data is recorded as rows, one record corresponds to one row. There are 250 records in every second (collecting frequency is 250Hz). In Original data, a record has 11 columns. The first column is the serial number of the record. The second column to ninth column record the data of 8 sensors. The tenth column records the trigger (When come to next picture, the EEG headset will send a trigger to the collecting computer). And the eleventh column records the time mark. 

* **Preprocessed data**

  For every row of record, we remove the first and the last column record (have no influence with the result). According to the trigger recorded in the tenth column, sperate the data as every picture. Every subject contains 58 files related to 58 pictures. The first file to the tenth file belong to the non-confusion group. As for other files, if the volunteer didn't choose an answer in 10 seconds, then put the file into the confusion group. Others which has an answer will divided to two group according the confidence test. The pictures that doesn't pass the confidence test will be discarded and the pictures that passed will be put into the confusion group. So that the confusion group and non-confusion is settled and we can use them to the next step like machine learning. 