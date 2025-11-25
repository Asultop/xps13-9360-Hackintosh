
**EFI 已配置说明**

- **用途**: 该 `EFI` 目录已根据本仓库的标准配置生成，可直接放入目标机器的 EFI 分区尝试引导（适用于本仓库目标机型 `XPS13-9360`）。
- **状态**: 已包含常用的引导器、驱动、ACPI 补丁与常用 kext。引导时请使用 `EFI/OC/config.plist` 对应的配置（Clover 支持已移除）。

**使用前准备**

- **备份原有 EFI**: 在对目标磁盘进行任何修改前，务必备份原有 EFI 分区，例如将原有 `EFI` 目录复制到安全位置。
- **确认匹配**: 确认你的硬件与本仓库的说明或分支匹配（例如 CPU、Wi‑Fi 芯片、声卡型号），不匹配时可能需要调整 `config.plist`、驱动或 kext。

**安装步骤（Windows / macOS / Linux 通用）**

1. 挂载 EFI 分区（例如 macOS 下用 `diskutil`，Windows 可用第三方工具，Linux 可用 `mount`）。
2. 备份目标分区上的 `EFI` 目录：复制到 `EFI-backup-YYYYMMDD`。
3. 将本仓库中的 `EFI` 目录整体复制到 EFI 分区根目录（替换或按需合并）。
4. 确认 `OC` 使用的 `config.plist` 与 `Kexts`、`Drivers` 相互匹配。
5. 安全弹出/卸载 EFI 分区并尝试重启进入引导菜单选择相应引导器。

**常见注意事项**

- **快速恢复**: 若引导失败，可恢复备份的 `EFI` 目录以回退到原状态。
- **签名和 SIP**: macOS 系统版本、SIP（System Integrity Protection）或引导安全选项可能影响引导，按需参考 OpenCore/Clover 官方文档调整设置。
- **日志与调试**: 若无法引导，请启用引导器的调试日志（例如 OpenCore 的 `-v`、`debug` 设置）并查看 `Boot.log` 或 `dmelog` 等输出以排查问题。

**免责声明**

- 本仓库提供的 `EFI` 仅用于社区学习与测试。请在法律允许范围内使用，并自行承担风险。对数据丢失或硬件损坏概不负责。

