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
This competition in a nutshell is an image multi-class classification problem consisting five classes in total. The train dataset contains roughly 21400 labelled images whereas the test set consists of ~15000 images of which 10000 images were provided and rest of the test images were added during submission.
In the early attempts, I experimented with simple CNNs consisting of ~10 layers each followed by pooling layers. Generated data pipeline manually by appending one image array to another
