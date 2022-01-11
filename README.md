# Food_cls Baseline

A simple baseline for SIGS_Big_Data_ML_Exam_2021.

https://www.kaggle.com/t/b7ed697207f0401b94a1f5c49c559d68

# Environment
- python 3.6
- torch 1.5.1
- torchvision 0.6.0
- tqdm

必须用 `GPU` 跑 Q.Q (3 min per epoch on Tesla T4 8GB Memory)

# Download

下载数据到指定路径 `./data/food/`,将三个文件夹分别移动到:

- `./data/food/train/train`
- `./data/food/val/val`
- `./data/food/test/test`

# Baseline的实现

打开baseline文件夹

# Prepare（已附上生成的索引文件，跳过此步）

修改了prepare.py文件，增加了生成索引文件，创建数据集：

`python prepare.py --src ./data/food/train/train --out ./data/food/train.txt`

`python prepare.py --src ./data/food/val/val  --out ./data/food/val.txt`

打开prepare.py文件，将line60 改为 prepare_data2(src_path, out_path)

`python prepare.py --src ./data/food/test --out ./data/food/test.txt`

修改 `dataset.py` 的 `107-108` 行为你的指定路径

`train_txt = "/data/food/train.txt"`

`eval_txt = "/data/food/val.txt"`

# Hyper-parameter

修改config.py文件

# Train

`CUDA_VISIBLE_DEVICES=0 python train.py`

# Inferance

在cpkt文件夹内已经有训练好的模型，可以直接运行inferance.py文件生成结果。inferance.py的功能为用训练好的模型测试 `./data/food/test` 路径下的所有图片，并生成 `submission.csv` 文件

`python inferance_baseline.py'

#模型优化实现
打开resnet文件夹

# Prepare（已附上生成的索引文件，跳过此步）

修改了prepare.py文件，增加了生成索引文件，创建数据集：

`python prepare.py --src ./data/food/train/train --out ./data/food/train.txt`

`python prepare.py --src ./data/food/val/val  --out ./data/food/val.txt`

打开prepare.py文件，将line61 改为 prepare_data2(src_path, out_path)

`python prepare.py --src ./data/food/test --out ./data/food/test.txt`

修改 `dataset.py` 的 `107-108` 行为你的指定路径

`train_txt = "/data/food/train.txt"`

`eval_txt = "/data/food/val.txt"`

# Hyper-parameter

修改config.py文件

# Train

`CUDA_VISIBLE_DEVICES=0 python train.py`

# Inferance

在cpkt文件夹内已经有训练好的模型，可以直接运行inferance.py文件生成结果。inferance.py的功能为用训练好的模型测试 `./data/food/test` 路径下的所有图片，并生成 `submission.csv` 文件

`python inferance_baseline.py'





