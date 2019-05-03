RFC11: Binding Macro
====================

## Motivation


由于不同的语言允许的特殊符号不同, 为了兼容考虑宏的模式只能由英文字母组成 `[@][a-zA-Z]+`

使用所有符号仍是合法的, 但是造成语言之间的迁移问题的话, 自行处理.

将宏分类为两种, 建议命名法:

- 数据类型: `[@][a-z][a-zA-Z]*`.
- 数据容器: `[@][A-Z][a-zA-Z]*`.

## Reference

[#RFC3: Structured Macro](./RFC3%20-%20Structured%20Macro.md)

## Design

```arc
key@macro = 'raw-value'
```

表示将右边的输入交给左边的 Handler.

此特性有助于语言的反射特性实现

```arc
key@List  = [1, "2", "2"]
key@Tuple = [1, 2, 2]
key@Set   = [1, 2, 3]
```


允许 



考虑不同的符号

```text
key~Set = [1, 2, 3]
key@Set = [1, 2, 3]
key#Set = [1, 2, 3]
key^Set = [1, 2, 3]
key&Set = [1, 2, 3]
key*Set = [1, 2, 3]
key?Set = [1, 2, 3]
```