# Thai Handwritten Character Recognition (HCR) using Few-shot Learning Approach
## Summary

The objective is to develop a deep learning model that can solve Offline Thai Handwritten Character Recognition (HCR) task. Since the Thai HCR dataset is too small for a conventional training approach, few-shot learning is adopted for the model training.

ResNet18 trained on ImageNet is used to meta-train with Omniglot dataset with 5-way-5-shot classification tasks. Evaluated by KVIS Thai OCR dataset, the model achieved around 80% accuracy. In addition, it is found that pre-processing of the Thai HCR dataset significantly helps in improving the performance.

## Settings
- Dataset
    - Train
        - [Omniglot](https://github.com/brendenlake/omniglot): contains 1623 characters from 50 different alphabets
    - Test
        - [KVIS Thai OCR Dataset](https://data.mendeley.com/datasets/8nr3pbdk5c/1): contains 1024 images of 44 Thai consonants (classes)
- Preprocessing
    - Centering character (crop + add padding)
    - convert to black and white
- Model Design
    - Backbone model: ResNet18 pretrained on ImageNet, with its head layer replaced with a Flatten layer
    - Few-shot learning method: Prototypical Network