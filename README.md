# DepthVideoMaker

Windows 本地黑白深度视频生成器，可将普通视频转换为灰度深度视频。

v1.5.0 使用 **Video Depth Anything Small** 联合分析连续视频帧，重点改善单帧深度模型常见的画面闪烁和深度跳变问题。程序支持 NVIDIA CUDA 推理、NVENC 硬件编码、原音轨保留和输入输出双视频预览。

## 下载

请前往 [Releases](https://github.com/S7ardvst/DepthVideoMaker/releases) 下载。

推荐使用最新版：

- [DepthVideoMaker v1.5.0](https://github.com/S7ardvst/DepthVideoMaker/releases/tag/v1.5.0)
- [DepthVideoMaker v1.3.0](https://github.com/S7ardvst/DepthVideoMaker/releases/tag/v1.3.0)
- [DepthVideoMaker v1.0.0](https://github.com/S7ardvst/DepthVideoMaker/releases/tag/v1.0.0)

## v1.5.0 主要功能

- 使用 Video Depth Anything Small 连续视频深度模型
- 每次联合分析 32 帧，降低深度视频闪烁
- 使用重叠窗口对齐和渐变融合，减少长视频窗口接缝
- 镜头切换时重新建立独立的深度范围
- 竖屏视频自动旋转推理并恢复原始方向
- 窗口尺寸变化时，视频预览画面自动适应
- 支持输入和输出双视频预览
- 支持拖放视频文件
- 支持时间线跳转、播放暂停和音量调节
- 支持深度对比度、Gamma 和黑白方向调整
- 支持 NVIDIA CUDA GPU 深度推理
- 支持 NVIDIA NVENC 硬件编码
- NVENC 不可用时自动切换为 libx264 编码
- 保留原视频音轨；格式不兼容时自动转换为 AAC
- 支持取消任务，完成、取消或失败后自动清理临时文件

## 安装方法

1. 打开 [v1.5.0 Release](https://github.com/S7ardvst/DepthVideoMaker/releases/tag/v1.5.0)。
2. 下载 `黑白深度视频生成器_安装包_v1.5.0.exe`。
3. 双击安装包并选择安装位置。
4. 安装完成后运行 `DepthVideoMaker_v1.5.0.exe`。

安装包内已包含 CUDA 12、cuDNN 和程序所需运行库，无需单独安装 CUDA Toolkit。

## 使用方法

1. 启动 DepthVideoMaker。
2. 选择或拖入需要处理的视频。
3. 选择输出文件位置。
4. 根据需要调整对比度、Gamma 和深度方向。
5. 选择是否启用 NVIDIA NVENC 硬件编码。
6. 点击“开始生成”，等待处理完成。

## 运行要求

- Windows 10 或 Windows 11 64 位
- NVIDIA 显卡及兼容驱动
- 建议至少 8GB 显存
- 输出目录需要有足够空间存放视频和临时深度缓存

v1.5.0 的深度推理需要 NVIDIA CUDA。NVENC 只负责视频编码；如果 NVENC 不可用，程序仍可使用 CPU 完成 H.264 编码。

## 支持格式

- 输入：MP4、MOV、AVI、MKV、WebM、M4V
- 输出：H.264 MP4
- 音频：优先复制原音轨，不兼容时转换为 AAC

## 版本说明

### v1.5.0

- 使用 Video Depth Anything Small 替代 Depth Anything V2 Small
- 从单帧深度估计升级为连续 32 帧时序深度估计
- 新增长视频重叠窗口对齐与融合
- 改进深度稳定性，减少闪烁和深度跳变
- 修复预览画面不随窗口尺寸变化的问题
- 修复 NVENC 可用性检测
- 改进竖屏视频处理
- 更新程序图标和带版本号的主程序文件名

### v1.3.0

- 新增 NVIDIA CUDA GPU 深度推理
- 新增自动、NVIDIA GPU（CUDA）、CPU 三种计算设备
- 新增 NVIDIA NVENC 硬件编码
- 安装程序支持自定义安装位置

### v1.0.0

- 首个公开发布版本
- 支持基本的视频深度图生成

## 使用的模型

深度估计模型：[Video Depth Anything Small](https://github.com/DepthAnything/Video-Depth-Anything)（Apache-2.0）。

## 注意事项

- 视频分辨率和时长越大，处理时间越长。
- 深度推理期间会占用较多显存，请关闭不需要的 GPU 程序。
- 软件生成的深度结果取决于原始视频的清晰度、运动幅度和场景内容。
- 首次运行若被 Windows SmartScreen 提示，请确认文件来源为本仓库的 Release 页面。

## 安装包校验

v1.5.0 安装包 SHA256：

```text
E8184DBDB897069FFA623342A6C73573F2066E79D17D39B1B7F42E6B1C4A1543
```

也可以下载 Release 中的 `SHA256SUMS.txt` 进行校验。
