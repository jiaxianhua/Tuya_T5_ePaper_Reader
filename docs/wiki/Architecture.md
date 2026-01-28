# 架构与模块

## 系统分层
```
应用层：文件列表 / 文本阅读 / 图片浏览 / 按键交互 / 断点记录 / 旋转
  ↓
TuyaOS / TAL 抽象层：tal_time / tal_kv / event / netmgr / http_client
  ↓
设备驱动：SD/FATFS / GPIO Keys / EPD SPI
  ↓
图形与字库：GUI_Paint / HZK24 GBK
```

## 关键模块
- 应用入口：`src/tuya_main.c`
  - 初始化日志、按键、SD 挂载
  - UI 刷新主循环与状态机（文件列表/阅读/网盘）

- 时间同步：`src/net_time_sync.c`
  - 订阅网络状态，联网后通过 HTTP Date 校时

- 图片渲染：`src/sd_image_view.c`
  - BMP/JPG/PNG 解码并输出 1-bit 图像

- 百度网盘：`src/baidu_netdisk.c` / `src/baidu_netdisk.h`
  - 设备码授权、列表、详情、下载

- 显示与绘制：`lib/GUI/GUI_Paint.*`
- EPD 驱动：`lib/e-Paper/EPD_4in26.*`
- 字库：`lib/Fonts/hzk24.*`

## 主要路径与文件
- SD 挂载点：`/sdcard`
- 阅读进度：`/.sd_reader/progress.bin`
- 百度网盘 Token：`/.sd_reader/baidu_token.txt`

## UI 状态机（核心）
- `STATE_FILE_LIST`：SD 文件列表
- `STATE_SHOW_FILE`：文本或图片显示
- `STATE_BD_AUTH`：网盘授权
- `STATE_BD_LIST`：网盘列表
- `STATE_BD_DETAIL`：网盘文件详情
- `STATE_BD_MSG`：网盘消息/下载进度
- `STATE_ERROR`：错误页
