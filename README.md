# 门禁监测助手


| Version | Date       | Description                                                  | Other      |
| ------- | ---------- | ------------------------------------------------------------ | ---------- |
| v1.0.0  | 2021/07/22 | 口罩监测模型部署到 ART-Pi 中                                   |            |


## 1. 项目说明

该项目将口罩监测模型部署到RT-Thread提供的ART-Pi开发板并通过gc0328读取图像数据，最后通过多媒体扩展版输出结果。

## 2. 环境

- 操作系统： Windows10
- X-CUBE-AI： 5.2.0
- RT-Thread Studio： 2.1.1
- RT-AK

    [RT-AK仓库](https://github.com/RT-Thread/RT-AK)

## 2. 元件

- ART-Pi
- ART-Pi 多媒体扩展版
- gc0328

## 3. 步骤

### 3.0 准备文件

- RT-Thread工程
- RT-AK
- 准备好的模型
- X-CUBE-AI

### 3.1 部署模型

在命令行中进入到`RT-AK\rt_ai_tools`输入

```
python aitools.py --project="工程路径" --model="模型路径" --model_name="mask" --platform=stm32 --ext_tools="X-CUBE-AI路径" --clear
```

例如：

```
D:\RT-ThreadAI\RT-AK\rt_ai_tools>python aitools.py --project=D:\RT-ThreadAI\mask_detect --model=D:\RT-ThreadAI\RT-AK\rt_ai_tools\Models\mask_detect.tflite --model_name=mask --platform=stm32 --ext_tools=D:\RT-ThreadAI\stm32ai-windows-5.2.0\windows --clear
```

## 4. 训练模型

## 4.3 网络结构

- 两层卷积 + 一层全连接

![model](https://user-images.githubusercontent.com/48997918/126664710-692b93d4-696b-4bf1-98d8-d134d9d4f42c.png)


## 4.4 训练模型 & 验证模型

- 训练模型

![training](https://user-images.githubusercontent.com/48997918/126664723-b9e23965-ee89-411a-853a-e34bb0b62929.png)


- 验证训练模型的准确率

![evaluate](https://user-images.githubusercontent.com/48997918/126664763-96c984d4-bd6e-4ced-9597-06ab6552f4ac.png)


# 5. 运行结果


## 感谢名单
- Derekduke
- lebhoryi
