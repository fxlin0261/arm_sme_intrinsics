# Required streaming features

`Required streaming features` 指：在 Streaming Mode（流式模式）下使用这个 intrinsic，处理器必须具备哪些架构特性。

| 表达式 | 含义 |
| --- | --- |
| `FEAT_SME` | 需要 SME |
| `FEAT_SME2` | 需要 SME2 |
| `FEAT_SME2,FEAT_SME_I16I64` | 同时需要 SME2 和 I16I64 扩展 |
| `(FEAT_SME,FEAT_SVE2p1)\|FEAT_SME2` | 满足“SME + SVE2.1”或“SME2”任一条件 |

逗号表示 **同时满足**，`|` 表示 **满足其一**，括号表示条件分组。

这列的中文含义是 **所需架构特性**。

## 条目统计

| 分类 | 目录条数 | 索引条数 |
| --- | ---: | ---: |
| SME | 5,887 | 5,887 |
| SME2 | 2,306 | 2,306 |

两组共有 **713 条交叉项**，去重后：

**5,887 + 2,306 − 713 = 7,480 条**

## 为什么有 713 条交叉项

官网对这 713 个 intrinsic 给出了两种可选的架构特性路径：一条通过 SME 加上指定的 SVE 扩展，另一条通过 SME2 系列。因此同一条目分别收录在 `categories_sme/` 和 `categories_sme2/`，索引的两个表格也各列一次。

例如，`svbfmlslb[_f32]` 的官网要求为：

```text
(FEAT_SME,FEAT_SVE2p1)|FEAT_SME2
```

这表示满足 **SME + SVE2.1**，或者满足 **SME2**，两者任选其一。单独支持基础 SME 并不足以满足前一种条件。

| 官网可选特性路径 | 交叉条数 |
| --- | ---: |
| SME + SVE2.1，或 SME2 | 322 |
| SME + SVE2.1，或 SME2.1 | 353 |
| SME + SVE2.2，或 SME2.2 | 38 |
| 合计 | **713** |

这是按可选特性路径分类产生的交叉，不是重复抓取。也不是因为 SME2 兼容 SME 就把全部 SME 条目重复收录。两个表格共 8,193 行，按官网条目名去重后为 7,480 条。
