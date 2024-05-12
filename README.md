# Vision-ZeroWaste-Project
#
## Introduction
Detection of type of waste has been a critical issue in terms of sustainability; handling unsorted litter in recycling facilities. While the process could be laborious and time consuming, several researchers have proposed various models in order to detect types of waste, giving way for automated recycling facilities.

However, the technology still needs improvement as consideration of “in the wild” sorting of waste requires the models to diligently identify multiple waste items at the same time, categorize them properly, and assure this can happen on the clock with high accuracy. As such, the project will take a look at the ZeroWaste dataset by Bashkirova et al. [1] where they have collected and published the largest publicly available waste dataset to date to which they have applied various models to identify and categorize waste. The project would tackle concepts in computer vision related to the usage of deep neural networks in identifying objects in cluttered environments, taking in mind foreground-background imbalances as well as the Intersection over Union (IoU) scores of such models.

## Objective
The prime objective of this project is to replicate the results made by Bashkirova et al. [1] in terms of the progress they made in detecting waste in the wild as well as comparing their derived models with SOTA models in object detection. 
The scope of the research falls within the ZeroWaste dataset and the utilization of box-bounded object detection for classification of waste items into recycling categories for automated recycling systems.
The limitation of the research lies in the size of the dataset, while large is only around 6k for the largest variation as well as foreground-background imbalances in the dataset itself.

## Dataset
The dataset was designed by Bashkirova et al. [1] as a benchmark dataset that can be split into four different sub-datasets. First, the ZeroWaste-f dataset is intended for supervised detection and evaluation. It is a fully annotated dataset that is composed of 4661 frames of which 1805 frames were annotated with a subsampling rate of 10 and 2616 frames were annotated with a subsampling rate of 100. Second, The ZeroWaste-s dataset is intended for semi- and self-supervised learning and contains 6212 unlabeled images. Third, the ZeroWaste-w is intended for weakly supervised learning, so it has images before and after the presence of target objects on a conveyor belt. It consists of 1202 frames before the removal of the objects and 1208 frames after the removal of the objects. Finally, the ZeroWasteAug dataset is for all supervised datasets and is composed of multi-domain augmented waste objects. It is essentially another version of the ZeroWaste-f dataset; however, its focus is on the frames that contain rare metal and rigid plastic classes. According to the research needs, the paper will focus on the ZeroWaste-f dataset as it is the largest one out of the paper’s dataset which would allow us to explore the discussed models to their fullest form of accuracy. A subset of the dataset will be used for training while the rest will be used for testing with Stratified sampling being kept in mind.

## Methodology
To achieve our objectives we trained, tested, and validated six different models on the ZeroWaste-f dataset, and compared them to both each other and Bashkirova et al.'s results.
The models we used were:
1. RentinaNet
2. TridentNet
3. RT-DETR
4. Mask R-CNN
5. YOLOv6
6. YOLOv8

Their codes and README files are all included in this repository within their respective folders.

## Referernce
[1] D. Bashkirova et al., “ZeroWaste dataset: Towards deformable object segmentation in cluttered scenes,” IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), pp. 21147–21157, Jun 2022, doi: 10.1109/cvpr52688.2022.02047.
