# ZeroWaste Project: Using YOLOv8
#
## Description
The prime objective of this project is to replicate the results made by Bashkirova et al. [1] in terms of the progress they made in detecting waste in the wild as well as comparing their derived models with SOTA models in object detection. The scope of the research falls within the ZeroWaste dataset and the utilization of box-bounded object detection for classification of waste items into recycling categories for automated recycling systems. The limitation of the research lies in the size of the dataset, while large is only around 6k for the largest variation as well as foreground-background imbalances in the dataset itself.

One of the models we used to achieve our objective is YOLOv8. We trained our model using the ZeroWaste-f dataset. In this model we used ultralytics to train the model.

## Installing & Running the Model
There are two ways to run this model: Using Google Colab or using a GPU machine. We ran this model on Google Colab.

### Install & Run on a GPU Machine
To install and run this model on a GPU machine follow the steps below:
1. Create your environment
2. Use conda to navigate to your environment through the terminal (conda activate {YOUR_ENV})
3. Ensure the machine has the most up-to-date python version
4. Install the following libraries:
   - ultralytics
   - IPython
   - roboflow
   - Any other library as necessary (e.g. PyTorch, Torchvision)
5. Upload the model code as a .py file in your working directory
6. Run the model through the terminal using the python3 command (python3 "{YOUR}/{FILE}/{PATH}/YOLOv8_Ultra-Code.py")

### Install & Run on Google Colab
To install and run this model on Google Colab follow the steps below:
1. Ensure you are using a GPU resource unit not a CPU
2. Install the ultralytics, IPython, and roboflow libraries
3. Download the dataset as in YOLOv8 format using roboflow through the code
4. Then proceed to run the code
   
## How to Use the Model
1. Ensure all the necessary libraries are installed (as mentioned above)

    Using the GPU machine - You can just run the code file as mentioned in step 6

    Using Google Colab - You can just run the code blocks
2. The code runs as follows:
   - First, imports the necessary ultralytics packages (YOLO, checks, hub)
   - Next, a YOLOv6 model is created from scratch
   - Next, the imported model is trained on the custom COCO dataset (ensure that you have the correct dataset file path here) and using the specified number of epochs
   - Finally, it compresses the results and imports them in a zipped file
3. You can change the number of epochs in the training section as you see fit

## Dataset
The ZeroWaste-f dataset created by Bashkirova et al. [1] is intended for supervised detection and evaluation. It is a fully annotated dataset that is composed of 4661 frames of which 1805 frames were annotated with a subsampling rate of 10 and 2616 frames were annotated with a subsampling rate of 100.

## Reference
[1] D. Bashkirova et al., “ZeroWaste dataset: Towards deformable object segmentation in cluttered scenes,” IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), pp. 21147–21157, Jun 2022, doi: 10.1109/cvpr52688.2022.02047.

