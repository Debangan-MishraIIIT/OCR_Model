## Generic Model

The model is primarily trained on a custom dataset from Europena Newspapers dataset, which has ground truth model available. To create your own datasets, it is recommended to download the image (tif files) from the official website, along with the FRE11 result on original image (xml files) which is going to be used as a ground truth for our images. Running the code through data_preparation notebook will prepare the dataset in the required format. Note that I have not uploaded the processed images due to size restrictions.

The parts of the model and some of the helper functionalities are inspired by https://www.kaggle.com/code/gokulkarthik/captcha-text-recognition-using-crnn-in-pytorch and the paper "An End-to-End Trainable Neural Network for Image-based Sequence Recognition and Its Application to Scene Text Recognition".

The model achieves fairly high accuracy, and the loss reduces drastically with good results being observed within 10-15 epochs and the results consistently improving with an increase in the number of epochs. The metric used for loss is CTC loss which is a standard in OCR model loss calculations. For further analysis, a weighted levenshtein distance is used, provided by https://github.com/zas97/ocr_weighted_levenshtein which uses preset weights based on character visual similarity and previous OCR model trainings.
