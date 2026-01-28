# 墨阅 · E-Paper Reader WiKi

> 基于涂鸦 T5 平台的轻量级墨水屏文件阅读演示工程，支持 SD 卡目录浏览、文本阅读（断点记录）、图片渲染（1-bit 黑白）、按键交互与启动网络时间同步。

## 一分钟了解
- **面向场景**：离线阅读、资料展示、低功耗信息看板
- **核心能力**：SD 卡目录浏览、文本分页/断点、图片（BMP/JPG/PNG）渲染、旋转与按键控制
- **可扩展点**：编码处理、云端内容（百度网盘）、PDF 预处理、UI/交互优化

## 功能一览
- SD 卡挂载与目录分页浏览
- 文本自动换行与分页（阅读进度保存）
- 图片渲染为 1-bit 黑白图（BMP/JPG/PNG）
- 横竖屏旋转（SET 键切换）
- 启动时联网校时（HTTP Date）
- 百度网盘浏览与下载（可选）

## 快速开始
1. 选择板级配置（写入 `app_default.config`）
2. 配置 Wi-Fi 与百度网盘（可选）参数
3. 构建固件并烧录
4. 插入 FAT32 SD 卡，设备上电进入文件列表

详见：`docs/wiki/Quick-Start.md`

## 目录结构速览
- `src/`：应用源码（UI、文本阅读、图片渲染、网盘）
- `lib/`：EPD 驱动、字库与绘制工具
- `config/`：板级配置参考
- `tools/`：辅助工具（如 PDF 拆页）
- `screenshots/`：示例截图

## 典型使用流程
1. 上电进入 SD 文件列表
2. 方向键移动选择，`MID` 进入目录或打开文件
3. 文本阅读：`UP/DOWN` 行滚动，`LEFT/RIGHT` 翻页
4. `RST` 返回，`SET` 旋转
5. （可选）长按 `RST` 进入百度网盘

## 相关页面
- 快速上手：`docs/wiki/Quick-Start.md`
- 使用指南：`docs/wiki/Usage.md`
- 构建与配置：`docs/wiki/Build-Config.md`
- 架构与模块：`docs/wiki/Architecture.md`
- 百度网盘：`docs/wiki/Baidu-NetDisk.md`
- FAQ：`docs/wiki/FAQ.md`
- 排障：`docs/wiki/Troubleshooting.md`
- 参考与工具：`docs/wiki/References.md`
