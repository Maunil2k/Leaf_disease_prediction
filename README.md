# Motivation 
As the second-largest provider of carbohydrates in Africa, cassava is a key food security crop grown by smallholder farmers because it can withstand harsh conditions. At least 80% of household farms in Sub-Saharan Africa grow this starchy root, but viral diseases are major sources of poor yields. With the help of computer vision, it may be possible to identify common diseases so they can be treated. <br /><br />
In this competition, a dataset of 21,367 labeled images was collected during a regular survey in Uganda. Most images were crowdsourced from farmers taking photos of their gardens and annotated by experts at the National Crops Resources Research Institute (NaCRRI) in collaboration with the AI lab at Makerere University, Kampala. This is in a format that most realistically represents what farmers would need to diagnose in real life.<br /><br />
The task was to classify each cassava image into four disease categories or a fifth category indicating a healthy leaf. This challenge would help farmers to quickly identify diseased plants, potentially saving their crops before they inflict irreparable damage.<br /><br />
<img src = "https://github.com/Maunil2k/Leaf_disease_prediction/blob/master/images/1000015157.jpg" height = "240" width = "240">
<img src = "https://github.com/Maunil2k/Leaf_disease_prediction/blob/master/images/1000910826.jpg" height = "240" width = "240">
<img src = "https://github.com/Maunil2k/Leaf_disease_prediction/blob/master/images/1003442061.jpg" height = "240" width = "240">
<img src = "https://github.com/Maunil2k/Leaf_disease_prediction/blob/master/images/100472565.jpg" height = "240" width = "240">
<br /><br /><br />
# Approach
1) This competition in a nutshell is an image multi-class classification problem consisting five classes in total. The train dataset contains roughly 21400 labelled images whereas the test set consists of ~15000 images of which 10000 images were provided and rest of the test images were added during submission. In the early attempts, I experimented with simple CNNs consisting of ~10 layers each followed by pooling layers. Generated data pipeline manually by appending one image array to another and training the model using callbacks like early stopping, reducing learning rate on plateau and model checkpoint.
2) As a next attempt a tried training resnet50 from scratch but ended up with a very low validation accuracy of 18.20% whereas the train accuracy was about 22%. 
3) In the final attempt I used a pretrained EfficientNetB4 model with imagenet weights to get a big jump in accuracy. <br /><br /><br />

# Final Word and Future Prospect (updated on 09/08/22)
1) I was a novice when I started with this competition, as a result my code lacked a proper struture/efficiency and poor coding practices. Hence, there are several changes that could be made to the original notebook to optimize the data pipeline, improve efficiency by using pretrained models.
2) One way to optimize the data pipeline is to use Dataset class that inherits Sequence module from tensorflow.keras.utils. This will generate an iterator that would loop over our entire dataset hence loading our data more efficiently into RAM. This is one safe way to do multi-processing.
3) Another way to improve the public score is to use pretrained models. This has two advantages: (i) It reduces computation time since less epochs will be required to attain a certain level of accuracy compared to training model from scratch and (ii) Training on GPUs for longer durations leaves a lot of carbon footprints. 
4) Although the training data is good enough to fine tune a pretrained model, one can definitely implement data augmentation. This is a simple process for producing synthetic data from the already present ones. It basically increases our dataset size hence we can go for finetuning models with more parameters which wouldn't have possible by using only the real data.<br /><br /><br />

# References
1) Competition Link: [Cassava Leaf Disease Prediction](https://www.kaggle.com/competitions/cassava-leaf-disease-classification)
2) Displayed images: [Cassava Leaf Disease Prediction-Train Images](https://www.kaggle.com/competitions/cassava-leaf-disease-classification/data?select=train_images)
