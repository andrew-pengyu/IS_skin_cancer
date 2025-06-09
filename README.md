# YOLO-based classification of skin lesions

## Project Introduction
This project is based on four models of different sizes (Nano, Small, Medium, Large) of **YOLOv8** and **YOLOv11** to classify the **ISIC Skin Lesion Dataset**.

## Environmental dependencies
The following are the environmental dependencies required to run this project:
- **Python**: 3.10
- **scikit-learn**: 1.6.1
- **torch**: 2.7.1
- **torchvision**: 0.22.1
- **ultralytics**: 8.3.151
- **ultralytics-thop**: 2.0.14

## Description of the directory structure
<pre lang="markdown"> 
|--- .ipynb_checkpoints
|--- datasets                        # ISIC Skin Lesions Dataset
|    |--- Test
|    |    |--- actinic_keratosis                    
|    |    |--- basal_cell_carcinoma		
|    |    |--- dermatofibroma			
|    |    |--- melanoma				
|    |    |--- nevus						
|    |    |--- pigmented_benign_keratosis
|    |    |--- seborrheic_keratosis		
|    |    |--- squamous_cell_carcinoma	
|    |    |--- vascular_lesion				
|    |
|    |--- Train                      # The same category as Test
|         |--- actinic_keratosis
|         |--- ......
|
|--- models                          # Saved model structure
|
|--- ROC                             # Pictures of ROC curves for different models on a dataset
|
|--- skin_cls_yolo                  # Category Master Directory
|    |--- yolo_finetune
|         |--- yolov11l_cls_exp
|         |    |--- results
|         |    |    |--- model_complexity_yolo.xlsx     # Params(M), FLOPs(G), FPS
|         |    |    |--- summary_yolo_cls.xlsx          # Top1, Top5, F1_Score
|         |    |    |--- actinic_keratosis.xlsx
|         |    |    |--- basal_cell_carcinoma
|         |    |    |--- ......
|         |    |
|         |    |--- weights
|         |         |--- best.pt                         # Best model
|         |         |--- last.pt                         # Up-to-date models
|         |
|         |--- yolov11m_cls_exp             #Same structure as in the previous directory
|         |--- yolov11n_cls_exp
|         |--- yolov11s_cls_exp
|         |--- yolov8l_cls_exp
|         |--- yolov8m_cls_exp
|         |--- yolov8n_cls_exp
|         |--- yolov8s_cls_exp
|
|--- all_yolo_model_outputs.pkl      # The model outputs data
|
|--- Data augmentation.ipynb         # Data augmentation processing
|--- Testing.ipynb                   # Model testing and results saving
|--- ROC.ipynb                       # ROC curve plotting
|--- YOLO.ipynb                      # YOLO Training Script

</pre>
## Directions for use
To run this project, first download the dataset from the https://aistudio.baidu.com/datasetdetail/225795 (screenshot from the ISIC Skin Lesions Dataset).  

First, run the **Data augmentation.ipynb** file to augment the data (the data has been augmented in this project, so there is no need to repeat it).  

Then run **YOLO.ipynb** to train 8 different versions of the YOLO model (see code for details).  

Use **Testing.ipynb** and **ROC.ipynb** to output and save the corresponding results.  
