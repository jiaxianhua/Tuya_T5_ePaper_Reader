# 快速上手

本工程是 TuyaOpen 应用示例的一部分，构建流程与板级配置依赖 TuyaOpen 的工具链与 `tos.py`。

## 1) 准备环境
- 安装 TuyaOpen 工具链与依赖
- 确保 `tos.py` 可用
- 准备一张 FAT32 格式的 Micro SD 卡

## 2) 选择板级配置
在 TuyaOpen 工程根目录选择板级配置（会写入 `app_default.config`）：

```bash
# 在 TuyaOpen 工程根目录
. ./export.sh

# 进入应用目录（以 TuyaOpen 的 apps 路径为例）
cd apps/tuya_t5_epaper_reader

tos.py config choice
```

板级配置模板在本仓库：
- `config/TUYA_T5AI_BOARD.config`
- `config/TUYA_T5AI_POCKET.config`

## 3) 配置 Wi-Fi 与网盘（可选）
建议通过 Kconfig 菜单配置：

```bash
tos.py config menu
```

关键配置项：
- `EPAPER_WIFI_SSID` / `EPAPER_WIFI_PSWD`
- `BAIDU_NETDISK_ENABLE`
- `BAIDU_NETDISK_APP_KEY`
- `BAIDU_NETDISK_APP_SECRET`
- `BAIDU_NETDISK_TARGET_DIR`
- `BAIDU_NETDISK_SCOPE`

## 4) 构建与烧录

```bash
tos.py build
```

使用你的烧录工具将固件下载到开发板。

## 5) 准备 SD 卡内容
- 文本：`.txt`（UTF-8 / UTF-16 / GBK）
- 图片：`.bmp` / `.jpg` / `.jpeg` / `.png`

建议目录示例：
```
/Books
  /Novel
    book.txt
/Images
  cover.jpg
```

## 6) 运行与操作
- 上电自动挂载 `/sdcard` 并显示文件列表
- 方向键浏览，`MID` 打开文件
- `RST` 返回上一层，`SET` 切换横竖屏
- 长按 `RST` 进入百度网盘模式（若启用）
