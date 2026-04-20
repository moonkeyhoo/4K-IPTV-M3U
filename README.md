# RTP 自动更新工具

该仓库使用 `rtp/b.py` 按省份模板自动搜集可用 `udpxy` 节点，并生成：

- `rtp/*.txt`
- `rtp/*.m3u`

## 本地运行

1. 安装依赖：
   - `pip install -r requirements.txt`
2. 设置环境变量：
   - `QUAKE_TOKEN=<你的 Quake Token>`
3. 运行：
   - `python rtp/b.py`

如需本地一键提交并推送，可使用：

- `python rtp/b.py --push`

## GitHub 定时更新（每 3 天）

工作流文件：`.github/workflows/update-rtp.yml`

- 定时表达式：`0 2 */3 * *`
- 触发方式：手动触发 + 定时触发

### 必要配置

在仓库 `Settings -> Secrets and variables -> Actions` 中新增：

- `QUAKE_TOKEN`：你的 Quake API Token

配置完成后，工作流会每 3 天自动执行脚本并提交变更到当前仓库。
# 4K-IPTV-M3U
组播源，实时更新全国地区4K直播源

## 本地 GUI 工具（按省份导出 M3U）

仅 Windows 使用，基于 PySide6。

1. 安装依赖：`pip install -r requirements.txt`
2. 启动工具：`python scripts/export_m3u_by_province_gui.py`
3. 在界面中设置输出目录（默认项目下 `m3u`），点击“开始抓取并导出”
4. 工具会自动执行流程：省份下拉逐项选择 -> 找“新上线”IP -> “查看频道列表” -> 点击“M3U下载”
5. 文件名格式：`省份拼音+4K.m3u`（例如 `hubei4K.m3u`）
