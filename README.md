# Skmwork
# Fast and Accurate Knee Tissue Segmentation in Magnetic Resonance Imaging

## Database
This experiment used a manually selected subset, not the whole data set:
https://drive.google.com/drive/folders/13_pWimNV1WM1LL6fSOKY8-Tw2nGtsMNA?usp=drive_link

## Declare
To make the code look concise and neat. We use several notebooks to present the code and running results. Therefore, due to the limitations of colab, I will introduce the steps of running the code in two ways:

### Normal operation:
(1)Make sure you download the v1-release file.

(2)Run all model files: unet, vnet, transunet.

(3)Run the Eval_skm file.

### Google colab：
It is recommended to use A100GPU.
Follow the sections below to integrate the above files into a Notebook file. Then follow the steps below to run them.
If you have doubts about this part, you can view the Supplement.PDF file, which will provide a rough format, but please note that this is our experimental result for a period and it has been abandoned.

#### Prepare folder
(1) The first cell of ipynb, you can download skm-tea with pip install

(2) Just put v1-release in the current running folder, run the cell of Prepare folder, and load the data set

#### Load Function
(3) Run all cells in Load Function and load related functions

#### Load Model
(4) In Load Model, select the cell corresponding to the model to run (such as U-Net/V-Net/TransNet)

#### Train Model
(5) In the Train Model, run the corresponding cell (such as Train U-Net) according to the selected model.

#### Evalution
(6) In Evaluation, the cell running the Eval function loads the relevant function

(7) In Evaluation, run the corresponding cell (such as Start Eval U-Net) according to the selected model.

#### Plt
(8) Run the cell in Plt to get an evaluation diagram.

## Results
Performance of different models on each category

![Image text](https://github.com/LULU-Li0720/skmwork/blob/main/Performance.png)

## Reference
The original paper did not offer the code of their models, so we decided to built the Unet and Vnet in the original paper.

We reference the Unet from https://github.com/mateuszbuda/brain-segmentation-pytorch,

and the Vnet from https://github.com/mattmacy/vnet.pytorch

to fit this task, we modified the model above and set different hyperparameters.

Our advance model is called "TransUnet", we plan to try different loss function, number of layers and Data Augmentation to see how it will perform.


### Data set:

Desai, A. D.; Schmidt, A. M.; Rubin, E. B.; Sandino, C. M.; Black, M. S.; Mazzoli, V.; Stevens, K. J.; Boutin, R.; R ́e, C.;
Gold, G. E.; et al. 2022. Skm-tea: A dataset for accelerated mri reconstruction with dense image labels for quantitative clinical evaluation. arXiv preprint arXiv:2203.06823

### Model:

Milletari, F.; Navab, N.; and Ahmadi, S.-A. 2016. V-net: Fully convolutional neural networks for volumetric medical image segmentation. In 2016 fourth international conference on 3D vision (3DV), 565–571. Ieee

Ronneberger, O.; Fischer, P.; and Brox, T. 2015. U-net: Convolutional networks for biomedical image segmentation. In Medical Image Computing and Computer-Assisted Intervention–MICCAI 2015: 18th International Conference, Munich, Germany, October 5-9, 2015, Proceedings, Part III 18, 234–241. Springer.

## Additional instructions:
We can observe that the specific performance of the experiment does not compare well with the actual labels. This is due to limited resources. It's a tremendous amount of work, but our approach is correct. With sufficient resources in the future, we can further investigate.

![Image text](https://github.com/LULU-Li0720/skmwork/blob/main/Comparison.png)
