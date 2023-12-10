# rclone
[rclone115](https://github.com/gaoyb7/rclone-release) 魔改，增加双线程下载
# 注意事项
* 只支持 mount命令
* 需要重新生成rclone.conf文件，新增下载超时参数
* 下载超时计算方法：vfs read chunk size / 2 / 单线程下载速度（参考：chunk size：64,单线程下载速度 8M/s, timeout为4-8s）
# 更新说明
* 2023.11.29  修复内存泄漏
* 2023.12.06  修复http 416问题
* 2023.12.10  删除timeout参数，固定为5分钟，对失败的网络请求进行retry处理
