# 3D_print_kaggle_competition

## Goal

The goal of this competition is to label test images as containing under extrusion (1) or not (0). 

## My Code 

I have uploaded three different notebooks to this repo: new_notebook (1), validation?, and validation?. 

My test1.csv was produced from the new_notebook (1). It produced a relatively high F1 score (0.78956), but was rather inconsistent. On the other hand, the two validation notebooks produced lower scores, but seemed to have more consistency. 

I thought then that even though the test1 csv did well, maybe there were images that the new_notebook mislabelled that the validation notebooks labelled correctly. Therefore, I came up with a new csv called combo. I took the highest scoring csv produced from each of the two validation notebooks. For each image in the test set, I took the average has_under_extrusion label and rounded it to the nearest integer. For example, let's say the new_notebook assigned the 1st test image 0, but the validation notebooks assigned it 1s. The average would be 2/3, so the has_under_extrusion value would be assigned 1 in the combo.csv. 

When I uploaded the combo.csv to kaggle, it produced a higher F1 score (0.8134). Granted, most of the time, averaging did not produce higher F1 scores than the test1.csv did. Perhaps there would need to be some more advanced metrics for evaluating whether or not averaging between different methods produces better results.    
