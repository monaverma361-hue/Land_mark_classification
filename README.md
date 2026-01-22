# Landmark Classification using ConvNeXt (PyTorch)

This project implements a landmark image classification system using a Convolutional Neural Network (ConvNeXt) trained with PyTorch. The model classifies images into predefined landmark categories and demonstrates strong generalization on real-world images.

## Model Architecture
- Backbone: ConvNeXt (pretrained)
- Framework: PyTorch
- Task: Multi-class image classification

## Training Strategy
The model was trained in multiple stages to improve performance and stability:

1. Head Training  
   - ConvNeXt backbone frozen  
   - Only the classification head was trained  

2. Backbone Fine-Tuning  
   - Upper layers of the backbone were unfrozen  
   - Fine-tuned using a lower learning rate  

3. Final Backbone Training  
   - Full backbone trained after observing validation behavior  
   - Helped improve overall generalization  

## Final Performance
- Final Validation Accuracy: **95%**

## Project Structure
```
├── train.ipynb
├── predict.ipynb
├── requirements.txt
├── README.md
```

Dataset and trained weights are excluded due to size constraints.

## Installation
Install dependencies using:
```
pip install -r requirements.txt
```

## Inference
Use `predict.ipynb` to:
- Load the trained model
- Run predictions on custom images
- View top-k predictions with confidence scores

## Notes
- Dataset was split into train, validation, and test sets
- Class-wise behavior was analyzed during evaluation
- Model performance was verified on external real-world images

## Future Improvements
- Grad-CAM visualizations
- Stronger data augmentation
- Model deployment as a web app or API

Author: Mona Verma  
Domain: Computer Vision | Deep Learning | CNNs
