# DepthVideoMaker

黑白深度视频生成器，可将普通视频转换为灰度深度视频。

支持 NVIDIA CUDA 深度推理与 NVENC 硬件编码；没有可用 NVIDIA GPU 时，也可以使用 CPU 处理。

## 下载

请前往 [Releases](https://github.com/S7ardvst/DepthVideoMaker/releases) 下载。

推荐使用最新版：

- [DepthVideoMaker v1.3.0](https://github.com/S7ardvst/DepthVideoMaker/releases/tag/v1.3.0)
- [DepthVideoMaker v1.0.0](https://github.com/S7ardvst/DepthVideoMaker/releases/tag/v1.0.0)

## 主要功能

- 将普通视频转换为黑白深度视频
- 支持输入、输出双视频预览
- 支持拖放视频文件
- 支持时间线跳转、播放暂停和音量调节
- 支持 MP4、MOV、AVI、MKV、WebM、M4V 等常见格式
- 输出 H.264 MP4 视频
- 保留原视频音轨
- 支持 NVIDIA CUDA GPU 深度推理
- 支持 NVIDIA NVENC 硬件编码
- CUDA 或 NVENC 不可用时自动回退到 CPU

## v1.3.0 安装方法

由于 v1.3.0 安装包较大，下载文件采用分卷压缩。

1. 下载 v1.3.0 Release 中的全部 `.7z.001`、`.7z.002` 分卷文件。
2. 将所有分卷放在同一个文件夹内。
3. 安装 [7-Zip](https://www.7-zip.org/)。
4. 右键 `.7z.001` 文件。
5. 选择“7-Zip → 解压到当前文件夹”。
6. 运行解压得到的安装程序。

请勿单独解压 `.7z.002` 文件。

## v1.0.0 安装方法

1. 下载 v1.0.0 Release 中的 `.exe` 安装包。
2. 双击运行安装程序。
3. 根据安装向导完成安装。

## 使用方法

1. 启动 DepthVideoMaker。
2. 选择或拖入需要处理的视频。
3. 选择输出文件位置。
4. 选择计算设备：
   - 自动
   - NVIDIA GPU（CUDA）
   - CPU
5. 根据需要启用 NVIDIA NVENC 硬件编码。
6. 开始生成并等待处理完成。

## GPU 说明

v1.3.0 安装包已包含 CUDA 12 与 cuDNN 运行库，无需单独安装 CUDA Toolkit。

使用 GPU 加速仍需要：

- NVIDIA 显卡
- 正常安装且版本合适的 NVIDIA 显卡驱动

如果 CUDA 初始化失败，可以将计算设备切换为 CPU。

## 版本说明

### v1.3.0

- 新增 NVIDIA CUDA GPU 深度推理
- 新增自动、NVIDIA GPU（CUDA）、CPU 三种计算设备
- 新增 NVIDIA NVENC 硬件编码
- CUDA 不可用时自动回退 CPU
- NVENC 不可用时自动回退 libx264
- 安装程序支持自定义安装位置

### v1.0.0

- 首个公开发布版本
- 支持基本的视频深度图生成

## 使用的模型

深度估计模型：Depth Anything V2 Small（Apache-2.0）

## 注意事项

- 视频分辨率和时长越大，处理时间越长。
- 使用 CPU 处理通常会比 NVIDIA GPU 慢。
- 请确保输出目录有足够的磁盘空间。
- 软件生成的深度结果取决于原始视频的画面质量和内容。
