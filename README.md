 项目简介：
 本项目是针对超冷原子物理实验中“非线性相变识别”难题而开发的一套量子-经典混合深度学习框架。在真实的物理探测中，
 图像往往伴随极强的泊松散粒噪声（SNR $\approx$ 30）或干涉条纹本底（SNR $\approx$ 14），导致相变临界点的特征发生严重的
 贝叶斯重叠。为突破这一极限，本项目摒弃了传统 CNN 的“经验记忆”黑盒范式，首创了两大核心架构：V28 物理约束架构：融合动态 
 ROI 与 6-Qubit 量子线路，创新性引入 PINN（物理信息神经网络）单调性约束，彻底剥离低频干涉条纹。V31 极限拓扑架构：将量子层
 扩容至 8-Qubit，剥离线性分类器，并在 128 维超球面上引入 ArcFace 角裕度惩罚，结合八路全对称大考（Octa-TTA），成功抹平散粒涨落，
 斩获了 99.91% 的物理识别极限。
 
文件名解释：，
train_v：模拟生成10万张冷原子图像图片代码
model_v：模型代码
train_V:训练代码
_pth:为权重文件
图片为训练结果过程曲线

例如：
Dataset_Fluo_SNR30/ (文件夹)解释：由生成脚本构建的数据集存放目录，包含了 10 万张 32×32 分辨率的单通道灰度图像，按 0~9 阶跃类别分文件夹存放，等效信噪比30
Model_V28_Fluorescence_Best.pth解释：V28 模型训练得到的最佳权重参数文件。
Model_V31_Fluorescence_Best.pth解释：V31 极限模型训练得到的最佳权重参数文件（斩获 99.91% 准确率的节点）。


环境配置：您需要搭建一个基于 Python 3.9+，以 PyTorch (GPU版) 为经典计算底盘，结合 PennyLane 进行量子模拟，
并辅以 TensorBoard 等常用科学组件的量子-经典混合机器学习环境。

压缩包有相应的文件

方案一：如果您使用的是 Windows 系统（并且已经安装了 Anaconda 或 Miniconda），请在项目根目录下新建一个名为 setup.bat 的文件；
方案二：如果您使用的是 Linux 服务器或者 Windows 的 WSL 子系统，请在项目根目录下新建一个名为 setup.sh 的文件，；
方案三：除了上述的一键自动化脚本，为了符合 GitHub 开源项目的最高规范，您还必须在项目根目录放一个名为 requirements.txt 的文件，方便不想用一键脚本的极客开发者手动安装。
一键指令：pip install torch torchvision pennylane pennylane-lightning tensorboard numpy Pillow tqdm 

