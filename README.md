# DNA Builder

DNA Builder 用于根据 5′→3′ DNA 序列生成 ssDNA 或 dsDNA 的 XYZ 几何结构。程序使用内置核苷酸/碱基对坐标模板，并按固定螺旋步进拼接结构。

公开署名：hyphoon  
联系：wuhaifeng@ustc.edu.cn

## 依赖

- Python 3
- NumPy
- SciPy

安装依赖：

```bash
python -m pip install numpy scipy
```

## 使用

运行：

```bash
python DNAbuilder.py
```

程序会依次要求：

1. 输入仅由 `A/C/G/T` 构成的 DNA 序列；
2. 输入 `1` 生成 ssDNA，或输入 `2` 生成 dsDNA。

输出文件名：

```text
<SEQUENCE>_ssDNA.xyz
<SEQUENCE>_dsDNA.xyz
```

例如输入 `ACGT` 并选择 dsDNA，会生成：

```text
ACGT_dsDNA.xyz
```

## 几何规则

程序使用固定坐标模板：

- ssDNA：`A / C / G / T`
- dsDNA：`AT / CG / GC / TA`
- 螺旋轴：x 轴
- 相邻模板旋转：36°
- 相邻模板沿 x 轴平移：3.37998

## 使用限制

该脚本执行几何拼接，不包含力场优化、量子化学优化、分子动力学松弛或结构合理性判定。XYZ 也不保存键连接、残基编号、链信息和电荷状态。

生成结构用于进一步计算前，应检查连接区域、末端原子、质子化状态和目标 DNA 构象。

## License

当前未设置开源许可。
