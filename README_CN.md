# CellScope 公开版

[English](README.md) · [下载最新 Windows 版本](https://github.com/RoyYang-CN/CellScope-Public/releases/latest)

CellScope 用于 LTE/5G 工参 Excel 的批量核查：检测 PCI 复用冲突、TAC 区域异常和同站 MOD3 冲突，输出包含问题依据与候选修正值的 Excel 报告。建议值应由网优工程师结合原始数据和现网情况复核，不能直接作为现网变更指令。

## 功能与试用

- 支持常见中英文工参字段，提供[空白中文、英文模板](templates/)。
- 一次导入完成 PCI、TAC、MOD3 核查，并标记可能影响结论的数据问题。
- 单独生成核查报告，不覆盖原始 Excel。
- 支持中英文界面，首次启动默认英文。
- 免费试用 10 天，试用期可使用核查和推荐功能。到期后仍可查看核查问题和依据；推荐功能需要授权。

## 下载与授权

从 [Releases](https://github.com/RoyYang-CN/CellScope-Public/releases/latest) 下载 `CellScopePublic.exe`，适用于 64 位 Windows 10/11。可用发布页中的 `SHA256SUMS.txt` 核对文件。当前 EXE 未进行代码签名，Windows 可能提示“未知发布者”。

英文界面中的 **Buy License** 对应 [Creem 正式购买链接](https://www.creem.io/product/prod_1q96Nt7Aj1oyc29rYtZGeo)：一次性 **USD 29.90，含税**，授权一台 Windows 设备。付款后 Creem 通过邮件发送许可证密钥；首次激活需要联网，同一设备激活后可离线使用。请勿公开密钥。中文旧注册码和 Creem 许可证解锁同一套功能。

程序在本机处理工参 Excel；购买和首次激活会使用外部服务。不要在公开 Issue、论坛或截图中发布真实小区数据、客户信息或许可证密钥。

## 联系与使用边界

问题反馈：[hnzzlulu@gmail.com](mailto:hnzzlulu@gmail.com)。请说明程序版本和脱敏后的复现步骤。

核查结果是工程问题线索及候选建议。修改现网参数前，应复核坐标、站址、小区身份、区域规划和现网约束。

本仓库只发布程序、空白模板和说明；程序源码不在此仓库公开。
