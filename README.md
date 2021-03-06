# CycleGAN Implement
## CycleGAN with PyTorch

### Title
[Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks](https://arxiv.org/abs/1703.10593)


<img src="./git_img/cycleGAN.png"  width="750" height="200"> 
---

## Requirment
- Python                 3.7+
- torch                  1.7.1+cu110
- torchvision            0.8.2+cu110
- matplotlib             3.3.3
- numpy                  1.19.5
- Pillow                 8.1.0
- scikit-image           0.17.2
- scipy                  1.5.4
- tensorboard            2.4.1
- tensorboardX           2.1


## Train

    $ python main.py --mode train 
                     --data_path data/monet2photo \
                     --ckpt_path ckpt/monet2photo \
                     --result_path result/monet2photo \
                     --gpu 0
---

* Set your data_path, ckpt_path, and result_path.
* Hyperparameters were written to **arg.txt** under the **[log directory]**.



## Test
    $ python main.py --mode test 
                     --ckpt_path ckpt/monet2photo \
                     --result_path result/monet2photo \
                     --gpu 0
---

* To test using trained network, set **ckpt_path** defined in the **train** phase.
* Generated image will be saved as ** sample.jpg ** in the ** [result directory+"_test"] ** folder.


## Results
![alt-text](./git_img/photo2monet.png "convert photo to monet")

    1st row: input-photo 
    2nd row: output-monet 
    3th row: Identity-photo
    
![alt-text](./git_img/monet2photo.png "convert monet to photo")

    1st row: input-monet 
    2nd row: output-photo 
    3th row: Identity-monet


## Directories structure

    [dataset name]
    +---[Executable code]   - (Github code)
    |   +---main.py
    |   |   ...
    |   +---utils.py 
    \---[root]               - (Result)
        +---data
        |   +---[data_name1]
        |   |   +---trainA
        |   |   |   +---0000.jpg
        |   |   |   |   ...
        |   |   |   \---1234.jpg
        |   |   +---trainB
        |   |   |   +---0000.jpg
        |   |   |   |   ...
        |   |   |   \---1234.jpg
        |   |   +---testA
        |   |   |   +---0000.jpg
        |   |   |   |   ...
        |   |   |   \---1234.jpg
        |   |   +---testB
        |   |   |   +---0000.jpg
        |   |   |   |   ...
        |   |   |   \---1234.jpg
        |   \---[data_name2]
        |       |   ...
        +---ckpt
        |   +---[data_name1]
        |   |   +---model_epoch0000.pth
        |   |   |   ...
        |   |   \---model_epoch1234.pth
        |   \---[data_name2]
        |       +   ...
        +---result
        |   +---[data_name1]
        |   |   +---sample0000.jpg
        |   |   |   ...
        |   |   \---sample1234.jpg
        |   \---[data_name2]
        |       |   ...
        \---result_test
            +---[data_name1]
            |   +---sample0000.jpg
            |   |   ...
            |   \---sample1234.jpg
            \---[data_name2]
                |   ...
