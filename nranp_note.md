由于公司git限制，目前暂且用md文档完成改进记录，再次配置时可以根据当前文档进行配置。

## 2024-08-26 Karabiner 官网

由于本文档仅用于个人整理信息，不妨也将[官网地址](https://karabiner-elements.pqrs.org/)记录在此。

## 2024-08-26 载入现有规则

如同该仓库 README.md 文档所言，直接打开下述地址，由karabiner自行完成配置即可。这里的仓库地址仍然是原仓库地址，保持所用数据一直为最新的仓库内容。

```
karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/rux616/karabiner-windows-mode/main/json/windows_shortcuts.json
```

## 2024-08-26 切换输入法规则

当前并未了解规则的JSON语法，参考了[这篇大佬的博客](https://arminli.com/custom-karabiner-elements-shift/)完成了配置，将切换输入法方式由 `CONTROL`+`SAPCE` 更换为 `Shift` 单击切换。

直接在复杂规则中添加如下规则内容即可。

```json
{
    "description": "Change left_shift to control+space when used alone",
    "manipulators": [
        {
            "from": {
                "key_code": "left_shift",
                "modifiers": { "optional": ["any"] }
            },
            "to": [
                {
                    "key_code": "left_shift",
                    "modifiers": []
                }
            ],
            "to_if_alone": [
                {
                    "key_code": "spacebar",
                    "modifiers": ["left_control"]
                }
            ],
            "type": "basic"
        }
    ]
}
```

## 2024-08-26 去除IDE模式限制

目前部分快捷键被配置为排除 IDE 模式，我[通过修改配置文件解决](https://github.com/rux616/karabiner-windows-mode/issues/60#issuecomment-2309512135)

但是我不清楚为什么会单独排除 IDE 中的改键，但当前使用时没发现有问题。

## 2024-08-30 修改功能键(Function Keys)

仓库提供的预设功能键映射不太满足我当前键盘的键位，比如`上一首`、`暂停/播放`、`下一首`在习惯上应该是相邻的，但键盘由于将功能键四四分组而将其分开。

当前我的键位映射如下，`\`表示未修改：

| 按键 | 预设 | 修改后 |
| --- | --- | ----- |
| F1 | 降低亮度 | \ |
| F2 | 提高亮度 | \ |
| F3 | mission_control | \ |
| F4 | spotlight | \ |
| F5 | dictation | \ |
| F6 | F6 | 上一首 |
| F7 | 上一首 | 播放/暂停 |
| F8 | 播放/暂停 | 下一首 |
| F9 | 下一首 | F9 |
| F10 | 静音 | \ |
| F11 | 提高音量 | \ |
| F12 | 降低音量 | \ |
