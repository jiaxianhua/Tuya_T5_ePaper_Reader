# 百度网盘

## 功能概览
- 设备码授权（二维码 + 验证码）
- 浏览网盘目录
- 查看文件详情
- 下载文件到 SD 卡

## 启用与配置
在 `Kconfig` 中启用并配置：
- `BAIDU_NETDISK_ENABLE=y`
- `BAIDU_NETDISK_APP_KEY`
- `BAIDU_NETDISK_APP_SECRET`
- `BAIDU_NETDISK_TARGET_DIR`（默认 `/TuyaT5AI`）
- `BAIDU_NETDISK_SCOPE`（默认 `basic,netdisk`）

## 进入方式
- **长按 `RST`** 进入网盘模式

## 授权流程
1. 设备显示二维码或验证 URL + 设备码
2. 手机端完成授权
3. 授权成功后进入网盘列表

## 列表与详情
- 列表：方向键选择，`MID` 查看详情
- 详情：`MID` 触发下载

## 下载与存储
- 默认下载目录：`/sdcard/TuyaT5AI`
- Token 与会话缓存：`/.sd_reader/baidu_token.txt`

## 提示与错误
- 下载进度显示在消息页
- 下载失败会显示错误信息与 URL 便于调试

## 安全建议
- `BAIDU_NETDISK_APP_SECRET` 请勿提交到代码仓库
