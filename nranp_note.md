由于公司git限制，目前暂且用md文档完成改进记录，再次配置时可以根据当前文档进行配置。

## 2024-08-26 Karabiner 官网

由于本文档仅用于个人整理信息，不妨也将[官网地址](https://karabiner-elements.pqrs.org/)记录在此。

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
