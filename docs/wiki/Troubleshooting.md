# 排障

## SD 卡未挂载
- 确认 SD 卡为 FAT32 格式
- 检查 `EBABLE_SD_PINMUX` 与引脚配置（如需）
- 查看串口日志是否提示挂载失败

## 列表为空或文件乱码
- 隐藏文件（以 `.` 开头）会被忽略
- 文件名编码可能为 GBK/UTF-8 混用，尝试更换编码或简化文件名

## 图片无法打开
- 仅支持 `BMP/JPG/JPEG/PNG`
- BMP 只支持 1-bit 或 24-bit
- 文件过大可能导致内存不足

## 时间不正确
- 需要联网后通过 HTTP Date 校时
- 若 Wi-Fi 未配置或网络不可用，将使用默认时间

## 百度网盘进入失败
- 检查 `BAIDU_NETDISK_ENABLE` 是否开启
- 确认 Wi-Fi 配置正确
- 确认 `APP_KEY/APP_SECRET` 已配置
