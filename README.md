# WBFlow: Few-shot White Balance for sRGB Images via Reversible Neural Flows
* Authors: Chunxiao Li, Xuejing Kang, Anlong Ming*
* Affiliation: School of Computer Science (National Pilot Software Engineering School), Beijing University of Posts and Telecommunications

This paper is proposed to build a model that not only performs superior white balance for sRGB images but also generalizes to multiple cameras well.. [paper link](https://github.com/ChunxiaoLe/WBFlow/blob/main/1152.ChunxiaoLi.pdf)

# Results presentation
<p align="center">
  <img src="https://github.com/ChunxiaoLe/WBFlow/blob/main/example_images/vis22.png" alt="Visualization 1 of cross-camera WB for sRGB images" width="89%">
</p>
<p align="center">
  <img src="https://github.com/ChunxiaoLe/WBFlow/blob/main/example_images/vis33.png" alt="Visualization 2 of cross-camera WB for sRGB images" width="89%">
</p>
<p align="center">
  <img src="https://github.com/ChunxiaoLe/WBFlow/blob/main/example_images/vis44.png" alt="Visualization 3 of cross-camera WB for sRGB images" width="89%">
</p>
Comparing with the state-of-the-art methods, our WBFlow has a stable and superior performance for the sRGB images from different cameras. 


# Framework
<p align="center">
  <img src="https://github.com/ChunxiaoLe/SWBNet/blob/master/example_images/figure4.png" alt="The framework of our SWBNet" width="90%">
</p>
A. The CTIF extractor and CT-contrastive loss work together to learn the color temperature-insensitive features for achieving stable WB performance. B. The CTS-oriented transformer corrects multiple color temperature shifts differently to improve WB accuracy, especially for the multi-illumination sRGB images.

# Experiment
## Requirements
* Python 3.8.3
* pytorch (1.8.0)
* torchvision (0.8.1)
* tensorboard (optional)
* numpy 
* Pillow
* tqdm
* matplotlib
* scipy
* scikit-learn

## Testing
* Pretrained models: [Net](https://drive.google.com/file/d/1_Io3ESglojAvWGaZGW88KOfnTtPs0PAt/view?usp=sharing)
* Please download them and put them into the floder ./model/
### Testing single image
* To test single image, changing '--input' in demo.sh and run it. The result is save in the folder 'result_images'.
```
demo.sh
python demo_single_image.py --input './example_images/1127_D.JPG' --output_dir './result_images'
```
### Testing multiple images
* Public datasets are available: [Rendered WB dataset (Set1, Set2, Cube)](https://cvil.eecs.yorku.ca/projects/public_html/sRGB_WB_correction/dataset.html)
* To test multiple images, changing '--input_dir', '--gt_dir' and '--output_dir' in demo_images.py and run it.
```
python demo_images.py --input_dir --gt_dir --output_dir
```

## Training
* Training fold is formed according to [Deep White-balance Editing (CVPR 2020)](https://openaccess.thecvf.com/content_CVPR_2020/papers/Afifi_Deep_White-Balance_Editing_CVPR_2020_paper.pdf)
* Training fold is available: [Training Fold](https://github.com/ChunxiaoLe/SWBNet/blob/master/utilities/train_all_12000_12.npy)
* Training data can be loaded from: [Rendered WB dataset-Set1](https://cvil.eecs.yorku.ca/projects/public_html/sRGB_WB_correction/dataset.html) 
* To train the model, changing '--training_dir', '--data-name' and '--test-name' in train.py and run it.
```
python train.py --training_dir --data-name --test-name
```

# Citation
* Paper is available: [paper link](https://github.com/ChunxiaoLe/SWBNet/blob/master/paper/9786.ChunxiaoLi.pdf)
* Citing format is coming soon...
