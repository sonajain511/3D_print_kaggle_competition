# 3D_print_kaggle_competition

## Goal

The goal of this competition is to label test images as containing under extrusion (1) or not (0). 

## My Code (4/16)

I have uploaded three different notebooks to this repo: new_notebook (1), validation (2), and validation (3). 

My test1.csv was produced from the new_notebook (1). It produced a relatively high F1 score (0.78956), but was rather inconsistent. On the other hand, the two validation notebooks produced lower scores, but seemed to have more consistency. 

I thought then that even though the test1 csv did well, maybe there were images that the new_notebook mislabelled that the validation notebooks labelled correctly. Therefore, I came up with a new csv called combo. I took the highest scoring csv produced from each of the two validation notebooks (validation (2) with the validation_test1 (2) csv, validation (3) with the validation_test4.csv). For each image in the test set, I took the average has_under_extrusion label and rounded it to the nearest integer. For example, let's say the new_notebook assigned the 1st test image 0, but the validation notebooks assigned it 1s. The average would be 2/3, so the has_under_extrusion value would be assigned 1 in the combo.csv. 

When I uploaded the combo.csv to kaggle, it produced a higher F1 score (0.8134). Granted, most of the time, averaging did not produce higher F1 scores than the test1.csv did. Perhaps there would need to be some more advanced metrics for evaluating whether or not averaging between different methods produces better results.    

## 4/17 Update to My Code

I ran my validation notebook again last night two times, which resulted in the validation_test4 (2).csv and validation_test4 (3).csv submissions. The submission with validation_test4 (2).csv produced a f1 score of 0.52948 while the (3) csv received a 0.59639 f1 score. 

I decided to then try averaging the has_under_extrusion labels from test1.csv, validation_test1 (2).csv, and validation_test4 (2).csv and obtained a 0.85422 score. I then replaced validation_test4 (2).csv with the (3) csv and got a 0.8154 result. 

It still makes me think though what we can do to tell whether or not averaging results from different runs of the same model or even from different models is a good idea/produces even better results. 

## 4/18 Update to My Code 

My apologies. I realized that my validation (3) and validation (4) notebooks are identical. Anyway, I averaged the results from the test1.csv, validation_test1 (2).csv, and validation_test4 (1).csv and got an f1 score of 0.85564. 

Just to make some clarification though. new-notebook generated test1.csv, validation (2) generated validation_test1 (2).csv, and validation (3)/validation (4) generated validation_test4 (1).csv. I took the average has_under_extrusion score from those three files, put that average into a combo1.csv, and submitted the combo1.csv to the competition.   
