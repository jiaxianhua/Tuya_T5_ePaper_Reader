# 参考与工具

## 重要源码位置
- 应用入口与 UI：`src/tuya_main.c`
- 时间同步：`src/net_time_sync.c`
- 图片渲染：`src/sd_image_view.c`
- 百度网盘：`src/baidu_netdisk.c`
- 绘制与字库：`lib/GUI/GUI_Paint.*`、`lib/Fonts/hzk24.*`
- EPD 驱动：`lib/e-Paper/EPD_4in26.*`

## 工具
### PDF 拆页
文件：`tools/pdf_to_pages.py`

用法：
```bash
python3 tools/pdf_to_pages.py /path/to/book.pdf
```

说明：
- 依赖 `pdftoppm`（poppler-utils）
- 输出为 JPG，分辨率 120 DPI，文件名 `0001.jpg` 开始

## 截图
位于 `screenshots/`，可用于 README/WiKi 展示：
- `screenshots/sd_card_files.png`
- `screenshots/txt_portrait.png`
- `screenshots/txt_landscape.png`
- `screenshots/7_keys.png`
- `screenshots/baidu_net_disk_files.png`
- `screenshots/baidu_net_disk_qrcode.png`
- `screenshots/baidu_net_disk_app.png`
- `screenshots/baidu_net_disk_download.png`
- `screenshots/jpg.png`
- `screenshots/png.png`
