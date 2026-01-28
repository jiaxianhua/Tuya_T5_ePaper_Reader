# 构建与配置

## Kconfig 关键项
文件：`Kconfig`

### Wi-Fi
- `EPAPER_WIFI_SSID`
- `EPAPER_WIFI_PSWD`

### SD Pinmux（可选）
- `EBABLE_SD_PINMUX`
- `SD_CLK_PIN / SD_CMD_PIN / SD_D0_PIN / SD_D1_PIN / SD_D2_PIN / SD_D3_PIN`

### 百度网盘（可选）
- `BAIDU_NETDISK_ENABLE`
- `BAIDU_NETDISK_APP_KEY`（client_id）
- `BAIDU_NETDISK_APP_SECRET`（client_secret）
- `BAIDU_NETDISK_TARGET_DIR`（默认 `/TuyaT5AI`）
- `BAIDU_NETDISK_SCOPE`（默认 `basic,netdisk`）

## 时间同步
文件：`src/net_time_sync.c`
- 默认使用 HTTP `Date` 头进行校时
- 默认服务器：`www.baidu.com`，路径 `/`
- 时区偏移：`+8`
- 若未成功联网校时，会设置默认时间

## 板级配置
- `config/TUYA_T5AI_BOARD.config`
- `config/TUYA_T5AI_POCKET.config`

## 构建命令
在 TuyaOpen 工程根目录：

```bash
. ./export.sh
cd apps/tuya_t5_epaper_reader

tos.py config choice
# 可选：tos.py config menu

tos.py build
```

## 安全与保密建议
- `BAIDU_NETDISK_APP_SECRET` 属于敏感信息，建议仅本地配置，不要提交到版本库
