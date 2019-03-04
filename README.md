# Deep Learning Web Application with Python

## 1. Install requirements and clone this repository
Requirements include: 
- Flask 1.0.2
- Flask-Cors 3.0.6
- h5py 2.8.0
- Keras 2.2.4
- Keras-Applications 1.0.6
- numpy 1.15.4
- opencv-python 3.4.3.18
- Pillow 5.3.0
- tensorflow 1.12.0

`git clone https://github.com/ltephanysopez/deep-learning-web.git`  
`pip install -r requirements.txt`

## 2) Train model 

Use the Jupyter notebook train_your_model.ipynb to train a model

### 2.1 Place your own image folder structure according to the given structure:
```
data/ 
  train/
    
    class #/ 
        img001.jpg
        img002.jpg
        ...
    
    class #/ 
        img001.jpg
        img002.jpg
        ...

  validation/
    
    class #/ 
        img001.jpg
        img002.jpg
        ...
    
    class #/
        img001.jpg
        img002.jpg
        ...
```  
### 2.2 Enter the number of classes according to the number of image classes you are using
```
classes = <your classes>
```   

### 2.3 Enter the number of training and validation samples accoridng to your dataset
```
number_of_images_training = <your number of training images>
number_of_images_validation = <your number of validation images>
```  

### 2.4 Decide on which image size to train on
```
image_size = (<your size>,<your size>)
```  

### 2.5 Save model and architecture
```
model_json = model.to_json()
with open("model.json", "w") as json_file:
    json_file.write(model_json)
```
```
model.save_weights('your_model.h5')
```  

### 2.6 Evaluate the model by predicting on a new unseen image
```
prediction = loaded_model.predict(img_for_prediction)
```  

## 3. Set up backend in app.py with the trained model from saved model.json

### 3.1 Define classes according to the classes you are using
```
classes = {'our_class_name_1': 0, 'our_class_name_2': 1, 'our_class_name_3': 2 ... }
```  

### 3.2 Define same image size as network is trained on
```
image_size = (<your size>,<your size>)
```  

## 5. Run the backend for predicitions
`python app.py`

## 4. Run frontend
`cd /frontend`  
`npm install`  
`npm start`  

### 4.1 Visit `http://localhost:3000` to test the newly trained model by uploading an image


