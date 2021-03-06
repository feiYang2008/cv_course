# 第5章  
## 章节介绍(Chapter Abstract)  
* 分类识别任务


## 数据集（DataSets）  
* http://www.vision.caltech.edu/visipedia/CUB-200-2011.html  
  Wah C., Branson S., Welinder P., Perona P., Belongie S. “The Caltech-UCSD Birds-200-2011 Dataset.” Computation & Neural Systems Technical Report, CNS-TR-2011-001  
## 项目使用方法(Usage)  
* 1、在 chapter_05 文件夹下新建文件夹datasets，或是命令行构建 mkdir datasets  
* 2、将下载数据集压缩包 CUB_200_2011.tgz 在datasets文件夹下解压。  
* 3、在 chapter_05 根目录下运行命令： python utils/make_train_test_datasets.py ，制作数据集，会在 datasets 文件夹下生成 train_datasets（训练集），test_datasets（测试集）两个文件夹。制作数据的默认模式为目标crop标注边界框（bounding box 简称 bbox）区域，去除了背景，如下图bbox区域。  

  ![sample_1](https://github.com/XiangLiK/cv_course/raw/master/chapter_05/samples/sample_1.png)  
  crop模式样本,如下图:  
  ![sample_3](https://github.com/XiangLiK/cv_course/raw/master/chapter_05/samples/sample_3.png)  

* 4、模型训练，在 chapter_04 根目录下运行命令：python train.py  
  * A) 建议仔细阅读 train.py 接口参数注释。
  * B) 训练参数记录和模型保存路径会为 model_exp 文件夹，默认模式是每次训练都会清除之前的训练相关文件，可以设置 train.py 的 clear_model_exp = Flase，就可以保持每次训练相关文件不清除。
* 5、分析模型训练过程中的训练集loss和验证集loss，需求最佳的泛化模型点。在chappter_05 根目录下运行命令：python analyze/loss_trainval.py  
  运行后显示 train & val loss分析结果，如下图:  
  ![sample_trainVal_Loss](https://github.com/XiangLiK/cv_course/raw/master/chapter_05/samples/trainVal_Loss.png)  
* 6、模型测试，简化测试，同时获得模型的性能指标，注：（该项目以预测分类Top1为比较策略，获得模型精确率（Precision） 和 召回率（Recall），及所有类别的平均精确率和平均召回率，同时结果保存在 test_日期.json。）  
* 7、图片的前向推断运行命令：python inference.py , 可视化结果举例，如下图所示。


![sample_2](https://github.com/XiangLiK/cv_course/raw/master/chapter_05/samples/sample_2.png)  

## 联系方式 （Contact）  
* E-mails: 305141918@qq.com  
