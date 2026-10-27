# vectordrift

**比较两批文档的嵌入分布，检测整体漂移。**

`vectordrift` —— 计算嵌入向量的均值、协方差与近邻分布，比较两批数据之间的偏移量

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`vectordrift.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install qiulisao-vectordrift
```

装完直接用命令名调用：

```bash
vectordrift --help
```

也可以不用安装，直接把 `vectordrift.py` 拷走用——它只依赖标准库。

## 为什么需要它

不依赖具体模型，只用向量空间的几何量，模型换了也能比

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 向量漂移检测 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python vectordrift.py --file input.txt
python vectordrift.py --text "示例内容"
python vectordrift.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 分箱是等宽或等频，样本太少时结论不稳。
- 不做显著性检验。

## 跑测试

```bash
python test_vectordrift.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/qiulisao/vectordrift>

---

## 关于作者

qiulisao 做向量漂移检测相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://qiulisao.github.io>
- 仓库：<https://github.com/qiulisao/vectordrift>

## 许可

MIT，见 [LICENSE](LICENSE)。
