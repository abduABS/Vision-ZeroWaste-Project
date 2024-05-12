# ZeroWaste Project: Using RetinaNet
#
## Description
The prime objective of this project is to replicate the results made by Bashkirova et al. [1] in terms of the progress they made in detecting waste in the wild as well as comparing their derived models with SOTA models in object detection. The scope of the research falls within the ZeroWaste dataset and the utilization of box-bounded object detection for classification of waste items into recycling categories for automated recycling systems. The limitation of the research lies in the size of the dataset, while large is only around 6k for the largest variation as well as foreground-background imbalances in the dataset itself.

One of the models we used to achieve our objective is RetinaNet. We trained, tested, and validated our model using the ZeroWaste-f dataset. In this model we used Detectron2 [2] for object detection.

## Installing & Running the Model
There are two ways to run this model: Using Google Colab or using a GPU machine. We ran this model on Google Colab.

### Install & Run on a GPU Machine
To install and run this model on a GPU machine follow the steps below:
1. Create your environment
2. Use conda to navigate to your environment through the terminal (conda activate {YOUR_ENV})
3. Ensure the machine has the most up-to-date python version
4. Install the following libraries:
   - open-cv
   - PyTorch
   - TorchVision
   - fvcore library from Facebook using github (!pip install git+https://github.com/facebookresearch/fvcore.git)
5. Setup Detectron2
   - Clone it from github (!git clone https://github.com/facebookresearch/detectron2 detectron2_repo)
   - Install it's libary (detectron2_repo) in editable mode
6. Upload the dataset in your working directory
   - Ensure that you update the dataset path in the code for training, testing, and validating.
7. Upload the model code as a .py file in your working directory
8. Run the model through the terminal using the pyhton3 command (python3 "{YOUR}/{FILE}/{PATH}/RetinaNet-Code.py")

### Install & Run on Google Colab
To install and run this model on Google Colab follow the steps below:
1. Connect to Google Drive where you would have your dataset downloaded
   
   {from google.colab import drive

   drive.mount('/content/drive')}
2. Ensure you are using a GPU resource unit not a CPU
3. Install the following python libraries:
   - open-cv
   - PyTorch
   - TorchVision
   - fvcore library from Facebook using github (!pip install git+https://github.com/facebookresearch/fvcore.git)
4. Setup Detectron2
   - Clone it from github (!git clone https://github.com/facebookresearch/detectron2 detectron2_repo)
   - Install it's libary (detectron2_repo) in editable mode
5. Then proceed to run the code
   
## How to Use the Model
1. Ensure all the necessary libraries are installed (as mentioned above)

    Using the GPU machine - You can just run the code file as mentioned in step 8

    Using Google Colab - You can just run the code blocks
2. The code runs as follows:
   - First, the detectron logger as well as some other common libraries are imported
   - Next, detectron2 is using to train the custome COCO dataset (registering the dataset, retriving the metadata and dataset dictionary)
   - (Optional) you can then verify that the data loading was done correctly
   - Next is finetuning the training. Here the configurations (through which the model is specified as well) are all set up and hyperparameters can be adjusted
   - Next, a predictor is created to test the model trained
   - Next, we can validate the test results by visualizing some of the prediction results randomly
   - Finally, we benchmarked the inference speed 
3. You can tune the hyperparameters and the number of epochs in the training section as you see fit

## Dataset
The ZeroWaste-f dataset created by Bashkirova et al. [1] is intended for supervised detection and evaluation. It is a fully annotated dataset that is composed of 4661 frames of which 1805 frames were annotated with a subsampling rate of 10 and 2616 frames were annotated with a subsampling rate of 100.

## References
[1] D. Bashkirova et al., “ZeroWaste dataset: Towards deformable object segmentation in cluttered scenes,” IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), pp. 21147–21157, Jun 2022, doi: 10.1109/cvpr52688.2022.02047.

[2] J. Solawetz, “How to train DetectRoN2 on custom Object Detection Data,” Roboflow Blog, Apr. 09, 2024. https://blog.roboflow.com/how-to-train-detectron2/
