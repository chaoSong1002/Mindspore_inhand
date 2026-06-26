# MindSpore inhand 掌中宝
# 软件描述
软件集成了一些用mindspore训练的模型，包括图像分类、目标检测、语义分割等，用于展示mindspore的功能和性能。
# 软件功能一览

<p align = "center"> 
<img src="image.png" width="50%" height="50%" >
</p>

# 软件问题汇总
1. 问题1：软件只能在arm架构的手机上加载网络模型，在x86虚拟安卓机上无法加载。
   ![alt text](image-1.png)
2. 舞蹈梦工程无法使用，页面显示不齐全。
   ![alt text](image-2.png)
   该页面被设置为了横屏，但是页面是按竖屏设计的所以显示不全，只有半屏。更改后正常显示。
3. Quick Start内容网页都已经失效，打开后为空页面。
   <p align = "center">
   <img src="image-3.png" width="50%" height="50%" >
   </p>





---

# 新增功能：表情识别 (Expression Recognition)

# 功能概述
基于深度学习的人脸表情识别模块，支持识别 **3 种表情**：
- 😄 Happy（开心）
- 😢 Sad（悲伤）
- 😐 Neutral（中性）

# 技术方案
| 项目 | 说明 |
|------|------|
| 模型架构 | ImprovedCNN（~1.7M 参数） |
| 准确率 | 86.1%（FER2013 测试集） |
| 推理引擎 | ONNX Runtime Mobile v1.18.0 |
| 输入 | 48×48 灰度图，[0,1] 范围 |
| 模型大小 | 7.1 MB |

# 功能特性
- **拍照/相册识别**：选图后自动检测人脸并识别表情
- **实时检测**：点击 "Live Detect" 开启前置摄像头实时识别
- **人脸检测**：Android FaceDetector API 自动裁剪人脸区域
  
# 使用方式
1. 首页 → 高级区 → Expression Recognition
2. 选择照片或拍照 → Recognize Expression
3. 或点击 Live Detect 开启实时表情检测

# 代码结构
```
superresolution/src/main/java/com/mindspore/superresolution/
├── SuperResolutionModelExecutor.java    # ONNX 推理 + 人脸检测
├── SuperResolutionMainActivity.java     # 静态识别界面
├── LiveExpressionActivity.java          # 实时摄像头检测
├── ImageUtils.java                      # 图像预处理
├── BitmapUtils.java                     # 工具类
└── ModelExecutionResult.java            # 结果数据类
```
