# 1. 基础操作

## 1.1 安装以及环境配置

```python
# 导入Networkx
import networkx as nx
```

```python
# 输出NetworkX的版本
nx.__version__
>>> '2.8.8'
```

```python
# 导入绘图工具matplotlib
import matplotlib.pyplot as plt
%matplotlib inline
plt.rc("font",family='SimHei') # 中文字体
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

```python
# (1, 100),(2,500),(3,300)
plt.plot([1,2,3], [100,500,300])
# 设置中文标题和字体大小
plt.title('matplotlib中文字体测试', fontsize=25)
# 设置X轴标签及大小
plt.xlabel('X轴', fontsize=15)
# 设置Y轴标签及大小
plt.ylabel('Y轴', fontsize=15)
# 显示图像
plt.show()
```

![1676710634259](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182330214.png)



## 1.2 创建图——内置图

```python
import networkx as nx
# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

### 1.2.1 全连接图

```python
# 绘制无向全脸截图，节点设置为5
G = nx.complete_graph(5)
# 绘制图像
nx.draw(G)
```

![1676710792233](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331385.png)

```python
# 图的连接数
G.size()
>>> 10
```

```python
# 设置有向全连接图
G = nx.complete_graph(5, nx.DiGraph())
# 绘制
nx.draw(G)
```

![1676710924558](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182330921.png)

```python
# 连接个数
G.size()
>>> 20
```

```python
# 图像是否为有向图
G.is_directed()
>>> True
```

### 1.2.2 环状图

```python
# 无向环状图
G = nx.cycle_graph(5)
nx.draw(G)
```

![1676711028872](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182330291.png)

```python
# 有向环状图
G = nx.cycle_graph(5, nx.DiGraph())
nx.draw(G)
```

![1676711053860](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331386.png)

### 1.2.3 梯状图

```python
G = nx.ladder_graph(5)
nx.draw(G)
```

![1676711087106](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331387.png)

> 不支持有向图

### 1.2.4 线性串珠图

```python
# 无向线性串珠图
G = nx.path_graph(15)
nx.draw(G)
```

![1676711144667](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331388.png)

```python
# 有向线性串珠图
G = nx.path_graph(15, nx.DiGraph())
nx.draw(G)
```

![1676711166128](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331389.png)

### 1.2.5 星状图

```python
# 无向星状图
G = nx.star_graph(7)
nx.draw(G)
```

![1676711202285](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331390.png)

> 不支持有向图

### 1.2.6 轮辐图

```python
# 轮辐图
G = nx.wheel_graph(7)
nx.draw(G)
```

![1676711263523](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331391.png)

> 不支持有向图

### 1.2.7 二项树

```python
# 无向二项树
G = nx.binomial_tree(5)
nx.draw(G)
```

![1676711330311](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331392.png)

```python
# 有向二项树
G = nx.binomial_tree(5,nx.DiGraph())
nx.draw(G)
```

![1676711347508](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331393.png)

### 1.2.8 二维矩形网状图

```python
G = nx.grid_2d_graph(3,5)
nx.draw(G)
```

![1676711384542](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331394.png)

### 1.2.9 多维矩形网状图

```python
G = nx.grid_graph(dim=(2,3,4))
nx.draw(G)
```

![1676711422604](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331396.png)

### 1.2.10 二维三角形网状图

```python
G = nx.triangular_lattice_graph(2,5)
nx.draw(G)
```

![1676711460044](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331397.png)

### 1.2.11 二维六边形蜂窝图

 ```python
G = nx.hexagonal_lattice_graph(2,3)
nx.draw(G)
 ```

![1676711481125](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331398.png)



### 1.2.12 N维超立方体图

```python
G = nx.hypercube_graph(4)
nx.draw(G)
```

![1676711544456](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331399.png)

### 1.2.13 钻石图

```python
G = nx.diamond_graph()
nx.draw(G)
```

![1676711624171](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331400.png)

### 1.2.14 牛角图

```python
# 无向牛角图
G = nx.bull_graph()
nx.draw(G)
```

![1676711675936](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331401.png)

```python
# 有向牛角图
G = nx.bull_graph(nx.DiGraph())
nx.draw(G)
```

![1676712238848](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331402.png)

### 1.2.15 furcht图

```python
G = nx.frucht_graph()
nx.draw(G)
```

![1676712277530](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331403.png)

### 1.2.16 House图

```python
# 无向图
G = nx.house_graph()
nx.draw(G)
```

![1676712311781](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331404.png)

```python
# 有向图
G = nx.house_graph(nx.DiGraph())
nx.draw(G)
```

![1676712394084](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331405.png)

### 1.2.17 Petersen图

```python
# 无向
G = nx.petersen_graph()
nx.draw(G)
```

![1676712554951](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331406.png)

```python
# 有向
G = nx.petersen_graph(nx.DiGraph())
nx.draw(G)
```

![1676712585602](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331407.png)

### 1.2.18 风筝图

```python
# 有向
G = nx.krackhardt_kite_graph(nx.DiGraph())
nx.draw(G)
```

![1676712714043](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331408.png)

```python
# 无向
G = nx.krackhardt_kite_graph()
nx.draw(G)
```

![1676712747012](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331409.png)

### 1.2.19 随机图

```python
G = nx.erdos_renyi_graph(10, 0.5)
nx.draw(G)
```

![1676712777951](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331410.png)

### 1.2.20 无标度有向图

```python
G = nx.scale_free_graph(20)
nx.draw(G)
```

![1676712809289](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331411.png)

### 1.2.21 空手道俱乐部

```python
# 空手道俱乐部
G = nx.karate_club_graph()
nx.draw(G, with_labels=True)
```

![1676712869011](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331412.png)

```python
# 第五个节点的所属派系
G.nodes[5]['club']
>>> 'Mr. Hi'
```

```python
# 第九个节点的所属派系
G.nodes[9]['club']
>>> 'Officer'
```

### 1.2.22 悲惨世界人物关系

```python
# 雨果《悲惨世界》人物关系
G = nx.les_miserables_graph()
plt.figure(figsize=(12,10))
pos = nx.spring_layout(G, seed=10) # 设置一个弹簧布局，随机数种子为10
nx.draw(G, pos, with_labels=True)
```

![1676720238078](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331413.png)

### 1.2.23 家族系谱图

```python
# Florentine families graph
G = nx.florentine_families_graph()
nx.draw(G, with_labels=True)
```

![1676720271465](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331414.png)

### 1.2.24 社群聚类图

```python
G = nx.caveman_graph(4, 3)
nx.draw(G, with_labels=True)
```

![1676720300783](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331415.png)

### 1.2.25 树状结构

```python
tree = nx.random_tree(n=10, seed=0)
print(nx.forest_str(tree, sources=[0]))
>>>
╙── 0
    ├── 3
    └── 4
        ├── 6
        │   ├── 1
        │   ├── 2
        │   └── 7
        │       └── 8
        │           └── 5
        └── 9
```

## 1.3 通过连接表和邻接表创建图

1. 首先导入工具包、设置中文字体

```python
import networkx as nx
import numpy as np
import random # 随机数
import pandas as pd

# 数据可视化
import matplotlib.pyplot as plt
import matplotlib as mpl
%matplotlib inline
plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

2. 导入三元组的连接表

> 数据来源：OpenKG-四大名著人物关系知识图谱和OWL本体：http://www.openkg.cn/dataset/ch4masterpieces

```python
# 导入 csv 文件定义的三元组连接表，构建有向图
df = pd.read_csv('triples.csv')
```

![1676720761301](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331416.png)

3. 通过三元组创建连接表Edge List并创建图

```python
G = nx.DiGraph()  # 创建有向图
edges = [edges for edges in zip(df['head'], df['tail'])]  # 获取所有边关系
G.add_edges_from(edges)  # 从edges拿数据创建图的边关系
G.edges('曹操')  # 获得含有曹操的连接
>>> 
OutEdgeDataView([('曹操', '徐庶'), ('曹操', '张辽'), ('曹操', '蒯越'), ('曹操', '蔡瑁'), ('曹操', '张绣'), ('曹操', '夏侯淳'), ('曹操', '夏侯渊'), ('曹操', '曹真'), ('曹操', '郭嘉'), ('曹操', '徐晃'), ('曹操', '乐进'), ('曹操', '张郃'), ('曹操', '许褚'), ('曹操', '典韦'), ('曹操', '荀彧'), ('曹操', '荀攸'), ('曹操', '贾诩'), ('曹操', '司马懿'), ('曹操', '程昱'), ('曹操', '于禁'), ('曹操', '邓艾'), ('曹操', '钟会'), ('曹操', '庞德')])
```

4. 可视化

```python
# 节点排版布局-默认弹簧布局
pos = nx.spring_layout(G, seed=123)

plt.figure(figsize=(15,15))
nx.draw(G, pos=pos, with_labels=True)
```

![1676721337194](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331417.png)

5. 查看全局的参数

```python
print(G)  # 查看节点和连接的个数
>>> DiGraph with 123 nodes and 144 edges
print(len(G))  # 查看G有多少节点
>>> 123
print(G.size())  # 查看G有多少连接
>>> 144
print(G.number_of_nodes())
>>> 123
```

```python
print(G.nodes)  # 查看G有哪些节点
>>>
NodeView(('关羽', '刘备', '张飞', '张苞', '关兴', '关平', '卢植', '公孙瓒', '甘氏', '刘禅', '诸葛瞻', '诸葛亮', '姜维', '黄月英', '黄承彦', '诸葛瑾', '公孙越', '马超', '马腾', '韩遂', '徐庶', '曹操', '刘胜', '刘启', '刘辩', '孙权', '孙尚香', '糜氏', '糜芳', '糜竺', '魏延', '赵云', '黄忠', '庞统', '法正', '蒋琬', '马良', '孟获', '沙摩柯', '庞德公', '马谡', '祝融', '孙韶', '孙策', '孙氏', '陆逊', '刘协', '董卓', '王允', '貂蝉', '吕布', '丁原', '高顺', '陈宫', '张辽', '刘表', '蔡氏', '蔡瑁', '蒯越', '黄祖', '文聘', '张宝', '张角', '张梁', '袁绍', '袁术', '袁谭', '袁熙', '袁尚', '吴国太', '孙坚', '大乔', '小乔', '周瑜', '丁奉', '徐盛', '鲁肃', '张昭', '蒋钦', '太史慈', '周泰', '凌统', '吕蒙', '甘宁', '黄盖', '韩当', '程普', '曹嵩', '吕伯奢', '邹氏', '张绣', '清河公主', '夏侯楙', '夏侯渊', '夏侯淳', '曹真', '曹爽', '郭嘉', '徐晃', '乐进', '张郃', '许褚', '典韦', '荀彧', '荀攸', '贾诩', '司马懿', '程昱', '于禁', '邓艾', '钟会', '庞德', '司马师', '司马昭', '司马炎', '曹仁', '曹纯', '曹昂', '刘氏', '超昂', '卞氏', '曹丕', '曹植'))
```

```python
print(G.edges)
>>>
OutEdgeView([('关羽', '刘备'), ('关羽', '张飞'), ('刘备', '诸葛亮'), ('刘备', '马超'), ('刘备', '徐庶'), ('刘备', '姜维'), ('刘备', '糜芳'), ('刘备', '糜竺'), ('刘备', '魏延'), ('刘备', '赵云'), ('刘备', '黄忠'), ('刘备', '庞统'), ('刘备', '法正'), ('刘备', '蒋琬'), ('刘备', '马良'), ('刘备', '孟获'), ('刘备', '沙摩柯'), ('张飞', '刘备'), ('张苞', '张飞'), ('关兴', '关羽'), ('关平', '张苞'), ('关平', '关羽'), ('卢植', '刘备'), ('公孙瓒', '刘备'), ('甘氏', '刘备'), ('刘禅', '甘氏'), ('诸葛瞻', '刘禅'), ('诸葛瞻', '诸葛亮'), ('诸葛亮', '姜维'), ('姜维', '诸葛亮'), ('黄月英', '诸葛亮'), ('黄承彦', '黄月英'), ('诸葛瑾', '诸葛亮'), ('公孙越', '公孙瓒'), ('马腾', '马超'), ('韩遂', '马腾'), ('曹操', '徐庶'), ('曹操', '张辽'), ('曹操', '蒯越'), ('曹操', '蔡瑁'), ('曹操', '张绣'), ('曹操', '夏侯淳'), ('曹操', '夏侯渊'), ('曹操', '曹真'), ('曹操', '郭嘉'), ('曹操', '徐晃'), ('曹操', '乐进'), ('曹操', '张郃'), ('曹操', '许褚'), ('曹操', '典韦'), ('曹操', '荀彧'), ('曹操', '荀攸'), ('曹操', '贾诩'), ('曹操', '司马懿'), ('曹操', '程昱'), ('曹操', '于禁'), ('曹操', '邓艾'), ('曹操', '钟会'), ('曹操', '庞德'), ('刘胜', '刘启'), ('刘辩', '刘启'), ('孙权', '诸葛瑾'), ('孙权', '孙策'), ('孙权', '周瑜'), ('孙权', '陆逊'), ('孙权', '丁奉'), ('孙权', '徐盛'), ('孙权', '鲁肃'), ('孙权', '张昭'), ('孙权', '蒋钦'), ('孙权', '太史慈'), ('孙权', '周泰'), ('孙权', '凌统'), ('孙权', '吕蒙'), ('孙权', '甘宁'), ('孙权', '黄盖'), ('孙权', '韩当'), ('孙权', '程普'), ('孙尚香', '刘备'), ('孙尚香', '吴国太'), ('糜氏', '刘备'), ('糜芳', '糜氏'), ('糜竺', '糜芳'), ('庞德公', '庞统'), ('马谡', '马良'), ('马谡', '诸葛亮'), ('马谡', '刘备'), ('祝融', '孟获'), ('孙韶', '孙策'), ('孙策', '孙坚'), ('孙氏', '陆逊'), ('孙氏', '孙策'), ('刘协', '刘辩'), ('董卓', '刘协'), ('董卓', '吕布'), ('王允', '刘协'), ('貂蝉', '王允'), ('貂蝉', '吕布'), ('吕布', '高顺'), ('吕布', '陈宫'), ('吕布', '张辽'), ('丁原', '吕布'), ('刘表', '刘协'), ('刘表', '黄祖'), ('刘表', '文聘'), ('蔡氏', '刘表'), ('蔡瑁', '蔡氏'), ('蒯越', '蔡瑁'), ('张宝', '张角'), ('张梁', '张宝'), ('袁绍', '刘协'), ('袁术', '袁绍'), ('袁谭', '袁绍'), ('袁熙', '袁谭'), ('袁尚', '袁熙'), ('吴国太', '孙坚'), ('吴国太', '孙权'), ('孙坚', '孙权'), ('大乔', '孙策'), ('大乔', '陆逊'), ('小乔', '大乔'), ('周瑜', '小乔'), ('曹嵩', '曹操'), ('吕伯奢', '曹嵩'), ('邹氏', '曹操'), ('邹氏', '张绣'), ('清河公主', '曹操'), ('夏侯楙', '清河公主'), ('夏侯渊', '夏侯楙'), ('夏侯渊', '夏侯淳'), ('曹爽', '曹真'), ('荀彧', '荀攸'), ('司马师', '司马懿'), ('司马昭', '司马师'), ('司马昭', '司马懿'), ('司马炎', '司马昭'), ('曹仁', '曹操'), ('曹纯', '曹仁'), ('曹昂', '曹操'), ('刘氏', '曹操'), ('超昂', '刘氏'), ('卞氏', '曹操'), ('曹丕', '卞氏'), ('曹植', '曹丕')])
```

6. 生成邻接列表

```python
for line in nx.generate_adjlist(G):
    print(line)
>>>
关羽 刘备 张飞
刘备 诸葛亮 马超 徐庶 姜维 糜芳 糜竺 魏延 赵云 黄忠 庞统 法正 蒋琬 马良 孟获 沙摩柯
张飞 刘备
张苞 张飞
关兴 关羽
关平 张苞 关羽
卢植 刘备
公孙瓒 刘备
甘氏 刘备
刘禅 甘氏
诸葛瞻 刘禅 诸葛亮
...(省略)
```

7. 导出邻接列表

```python
# 将邻接表导出为本地文件 grid.edgelist
nx.write_edgelist(G, path="grid.edgelist", delimiter=":")
```

![1676722011927](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331418.png)

8. 从本地读取邻接列表

```python
# 从本地文件 grid.edgelist 读取邻接表
H = nx.read_edgelist(path="grid.edgelist", delimiter=":")
```

9. 可视化

```python
# 可视化
plt.figure(figsize=(15,14))
pos = nx.spring_layout(H, iterations=3, seed=5)
nx.draw(H, pos, with_labels=True)
plt.show()
```

![1676722101503](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331419.png)

> 不论是从邻接表获取的图还是通过连接表获取的信息，他们表示的图都是一样的，偶保存了完整的信息。

## 1.4 手动创建节点

### 1.4.1 创建无节点、无连接的图

```python
# 无向图
G = nx.Graph()  # 创建G
print(G.is_directed())  # G是否为有向图
print(G)
>>> 
False
<networkx.classes.graph.Graph at 0x223beb10820>
```

```python
G.nodes  # 打印G的节点
>>> 
NodeView(())
```

```python
nx.draw(G)  # 绘制G
```

![1676723224302](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331420.png)

```python
# 给整张图添加特征属性
G.graph['Name'] = 'HelloWorld'
print(G.graph)
>>>
{'Name': 'HelloWorld'}
```

```python
# 创建有向图
H = nx.DiGraph()
print(H.is_directed())
>>>
True
```



### 1.4.2 添加单个节点

```python
G.add_node('刘备')  # 添加“刘备”节点
G.nodes  # 打印节点
>>> NodeView(('刘备',))
```

```python
G.add_node('Yom')  # 添加“Yom”节点
G.nodes
>>> NodeView(('刘备', 'Yom'))
```

```python
G.add_node(1)  # 添加节点“1”
G.nodes
>>> NodeView(('刘备', 'Yom', 1))
```

### 1.4.3 添加多个节点

```python
G.add_nodes_from(['诸葛亮', '曹操'])
G.nodes
>>>
NodeView(('刘备', 'Yom', 1, '诸葛亮', '曹操'))
```

```python
G.add_nodes_from(range(100,105))
G.nodes
>>>
NodeView(('刘备', 'Yom', 1, '诸葛亮', '曹操', 100, 101, 102, 103, 104))
```

### 1.4.4 添加带属性特征的节点

```python
G = nx.Graph()
G.add_node(0, a='haha', b='heihei', c='xixi')  # 在创建节点的时候，为节点添加属性特征
G.nodes[0]  # 访问名为“0”的节点
>>> {'a': 'haha', 'b': 'heihei', 'c': 'xixi'}
```

```python
G.add_nodes_from([    
    ('关羽',{'武器': '青龙偃月刀','武力值':90,'智力值':80}),    
    ('张飞',{'武器': '丈八蛇矛','武力值':85,'智力值':75}),    
    ('吕布',{'武器':'方天画戟','武力值':100,'智力值':70})
])
G.nodes
>>>
NodeView(('刘备', 'Yom', 1, '诸葛亮', '曹操', 100, 101, 102, 103, 104, '关羽', '张飞', '吕布'))
```

还可以对节点的属性进行访问

```python
G.nodes['张飞']
>>>
{'武器': '丈八蛇矛', '武力值': 85, '智力值': 75}
```

```python
nx.draw(G,with_labels=True)
```

![1676725217974](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331421.png)

### 1.4.5 从其他图添加节点

```python
H = nx.path_graph(10)  # 创建线性串珠图(10节点)
H.nodes
>>>
NodeView((0, 1, 2, 3, 4, 5, 6, 7, 8, 9))
```

```python
nx.draw(H, with_labels=True)  # 可视化
```

![1676725312529](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331422.png)

```python
# 将H的节点添加至G中
G.add_nodes_from(H)
# 绘图
nx.draw(G, with_labels=True)
```

![1676725356863](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331423.png)

### 1.4.6 将整个图作为节点导入

```python
# 将H本身作为节点导入
G.add_node(H)
G.nodes
>>>
NodeView(('刘备', 'Yom', 1, '诸葛亮', '曹操', 100, 101, 102, 103, 104, '关羽', '张飞', '吕布', 0, 2, 3, 4, 5, 6, 7, 8, 9, <networkx.classes.graph.Graph object at 0x00000223BE66B580>))
```

```python
nx.draw(G, with_labels=True)
```

![1676725431712](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331424.png)

> 节点可以为任意[可哈希](https://docs.python.org/3/glossary.html#term-hashable)的对象，比如字符串、图像、XML对象，甚至另一个Graph、自定义的节点对象。
>
> 通过这种方式，你可以根据你的应用，自由灵活地构建：图为节点、文件为节点、函数为节点，等灵活的图形式。

## 1.5 手动创建连接

```python
# 创建无向图G
G = nx.Graph()
# 为无向图G添加全局特征{"Name":"HelloWorld"}
G.graph["Name"] = "HelloWorld"
# 创建0号节点，并随意添加三个特征
G.add_node(0, x=1, y=2, z=3)
# 使用另一种方式创建1,2号节点，同样添加三个特征
G.add_nodes_from([
    (1,{'x':1,'y':1,'z':4}),
    (2,{'x':2,'y':3,'z':1})
])
```

```python
# 获取全局节点个数
G.number_of_nodes()
>>> 3
```

```python
G.nodes
>>>
NodeView((0, 1, 2))
```

```python
# data=True可以返回节点特征
G.nodes(data=True) 
>>>
NodeDataView({0: {'x': 1, 'y': 2, 'z': 3}, 1: {'x': 1, 'y': 1, 'z': 4}, 2: {'x': 2, 'y': 3, 'z': 1}})
```

```python
for node in G.nodes(data=True):
    print(node)
>>>
(0, {'x': 1, 'y': 2, 'z': 3})
(1, {'x': 1, 'y': 1, 'z': 4})
(2, {'x': 2, 'y': 3, 'z': 1})
```

### 1.5.1 创建单个连接

> 在连接的时候可以设置连接的属性

```python
# 将节点0和节点1连接，并设置连接的属性
G.add_edge(0, 1, weight=0.5, like=3)
```

### 1.5.2 创建多个连接

```python
G.add_edges_from([
  (1, 2, {'weight': 0.3, 'like':5}),
  (2, 0, {'weight': 0.1, 'like':8})
])
```

```python
# 查看节点0和节点1之间的连接特征
G.edges[(0, 1)]
>>>
{'weight': 0.5, 'like': 3}
```

### 1.5.3 可视化

```python
nx.draw(G, with_labels = True)
```

![1676727650337](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182331425.png)

### 1.5.4 全图连接信息

```python
G.number_of_edges()
>>> 3
```

```python
G.size()
>>> 3
```

```python
G.edges()
>>>
EdgeView([(0, 1), (0, 2), (1, 2)])
```

```python
G.edges(data=True)
>>>EdgeDataView([(0, 1, {'weight': 0.5, 'like': 3}), (0, 2, {'weight': 0.1, 'like': 8}), (1, 2, {'weight': 0.3, 'like': 5})])
```

```python
# 遍历所有连接，data=True 表示输出连接特征属性信息
for edge in G.edges(data=True):
    print(edge)
>>>
(0, 1, {'weight': 0.5, 'like': 3})
(0, 2, {'weight': 0.1, 'like': 8})
(1, 2, {'weight': 0.3, 'like': 5})
```

### 1.5.5 节点度

```python
# 指定节点
node_id = 1
G.degree[node_id]
>>>
2
```

```python
# 指定节点的所有相邻节点
for neighbor in G.neighbors(node_id):
    print("Node {} has neighbor {}".format(node_id, neighbor))
>>>
Node 1 has neighbor 0
Node 1 has neighbor 2
```

# 2. 数据可视化

## 2.1 nx.draw可视化函数

```python
# 图数据挖掘
import networkx as nx

import numpy as np

# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

# plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

### 2.1.1 原生可视化

```python
# 使用Fruchterman-Reingold计算过的布局
pos = nx.spring_layout(G, seed=123)
"""
circular_layout：节点在一个圆环上均匀分布
random_layout：节点随机分布
shell_layout：节点在同心圆上分布
spring_layout： 用Fruchterman-Reingold算法排列节点
spectral_layout：根据图的拉普拉斯特征向量排列节
布局也可用pos参数指定，例如，nx.draw(G, pos = spring_layout(G)) 这样指定了networkx上以中心放射状分布.
"""
```

```python
# 绘制
nx.draw(G, pos)
```

![image-20230218233302844](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182333935.png)

### 2.1.2 节点大小

```python
# 将node_size设置为0
nx.draw(G, pos, node_size=0, with_labels=False)
```

![](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182334222.png)

### 2.1.3 设置颜色

```python
nx.draw(
    G,                         # 图
    pos,                       # 布局
    node_color='#A0CBE2',      # 节点颜色
    edgecolors='red',          # 节点外边缘的颜色
    edge_color="blue",         # edge的颜色
    # edge_cmap=plt.cm.coolwarm, # 配色方案
    node_size=800,             # 节点大小
    with_labels=False,         # 是否显示节点label
    width=3,                   # 连接的宽度
)
```

![image-20230218233544023](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182335108.png)

### 2.1.4 有向图

```python
nx.draw(
    G.to_directed(),  # 转换为有向图
    pos,
    node_color="tab:orange",
    node_size=400,
    with_labels=False,
    edgecolors="tab:gray",
    arrowsize=10,  # 箭头的大小
    width=2,
)
```

![image-20230218233615772](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182336848.png)

### 2.1.5 设置节点坐标

在有些场景中，我们会尽可能保存实际场景的空间坐标信息，比如：上海地铁站，每个站点都有对应的经纬度，我们将其抽象成Graph之后，也会保存实际的坐标信息。

- 无向图

```python
G = nx.Graph()
G.add_edge(1, 2)
G.add_edge(1, 3)
G.add_edge(1, 5)
G.add_edge(2, 3)
G.add_edge(3, 4)
G.add_edge(4, 5)
nx.draw(G, with_labels=True)
```

![image-20230218233731514](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182337593.png)

```python
# 设置每个节点可视化时的坐标，以字典的形式，传入每个节点的坐标。
pos = {1: (0, 0), 2: (-1, 0.3), 3: (2, 0.17), 4: (4, 0.255), 5: (5, 0.03)}

# 设置其它可视化样式
options = {
    "font_size": 36,    # label显示的大小
    "node_size": 3000,  # 节点大小
    "node_color": "white",
    "edgecolors": "black", 
    "linewidths": 5, # 节点线宽
    "width": 5, # edge线宽
}

nx.draw_networkx(G, pos, **options)  # 使用draw_networkx

ax = plt.gca()
ax.margins(0.20) # 在图的边缘留白，防止节点被截断
plt.axis("off")
plt.show()
```

![image-20230218233808045](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182338110.png)

- 有向图

```python
G = nx.DiGraph([(0, 3), (1, 3), (2, 4), (3, 5), (3, 6), (4, 6), (5, 6)])
nx.draw(G, with_labels=True)
```

![image-20230218233846384](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182338460.png)

```python
# 可视化时每一列包含的节点（以栅格的状态展示）
left_nodes = [0, 1, 2]
middle_nodes = [3, 4]
right_nodes = [5, 6]
```

```python
# 可视化时每个节点的坐标
pos = {n: (0, i) for i, n in enumerate(left_nodes)}
pos.update({n: (1, i + 0.5) for i, n in enumerate(middle_nodes)})
pos.update({n: (2, i + 0.5) for i, n in enumerate(right_nodes)})
```

```python
pos
>>>
{0: (0, 0),
 1: (0, 1),
 2: (0, 2),
 3: (1, 0.5),
 4: (1, 1.5),
 5: (2, 0.5),
 6: (2, 1.5)}
```

```python
nx.draw_networkx(G, pos, **options)

ax = plt.gca()
ax.margins(0.20) # 在图的边缘留白，防止节点被截断
plt.axis("off")
plt.show()
```

![image-20230218233941825](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302182339894.png)

## 2.2 American 128 Cities Transportation Relationships

dataset: kruth_miles.txt.gz

```python
# 图数据挖掘
import networkx as nx

import numpy as np

# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

# plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

```python
import gzip  # 由于数据集是压缩包，所以要解压
import re  # 使用正则匹配

import warnings
warnings.simplefilter("ignore")
```

### 2.2.1 构建图

```python
fh = gzip.open("knuth_miles.txt.gz", "r") # 加载数据集

G = nx.Graph()  # 创建没有节点的无向图
G.position = {}  # 设置G的position属性特征
G.population = {}  # 这只G的population属性特征
```

**重头戏**：提取节点、建立连接及其特征抽取、提取G的属性

```python
cities = []  # 存放所有city
for line in fh.readlines(): # 遍历文件中的每一行
    line = line.decode()  # 将读取的二进制文件解码(见注释1)
    if line.startswith("*"):  # 其它行，跳过
        continue

    numfind = re.compile(r"^\d+")  # 正则匹配以数字开头的行（其实就是）

    if numfind.match(line):  # 记录城市间距离的行(见注释4)
        dist = line.split()  # 实际就是城市之间的距离(见注释2)
        for d in dist:
            G.add_edge(city, cities[i], weight=int(d))
            i = i + 1
    else:  # 记录城市经纬度、人口的行 (见注解3)
        i = 1
        (city, coordpop) = line.split("[")
        cities.insert(0, city)
        (coord, pop) = coordpop.split("]")
        (y, x) = coord.split(",")

        G.add_node(city)
        # assign position - Convert string to lat/long
        x = -float(x) / 100
        y = float(y) / 100
        G.position[city] = (x, y)
        pop = float(pop) / 1000
        G.population[city] = pop
```

* 注释【1】：

```python
txt = [line.decode() for line in fh.readlines()]
print(txt)
>>>
['* This file miles_dat.txt is part of NetworkX and is distributed \n', '* with the same license as NetworkX.\n', '* Distributed under the terms of the GNU Lesser General Public License\n', '* http://www.gnu.org/copyleft/lesser.html\n', '* This file is not part of the Stanford GraphBase; the name has been\n', '* changed to avoid any confusion with files from that collection.\n', '* Original...
```

在数据的前面，会有一些以"\*"开头的注释，我们不需要，所以当我们读取到以"\*"开头的行时，就跳过。

- 注释【2】：

![image-20230219161936484](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302191619655.png)

这是数据集的部分，从这里我们可以看出有两种类型的数据：

1. 以城市名称开头（如：Youngstown，OH）
2. 以数字开头（如：966、1513 2410）

第一种数据的含义：首府, 州简称[纬度(y轴), 经度(x轴)]人口

第二种数据的含义：这是代表城市之间的距离（如：966是Youngstown和Yankton之间的距离；1513是Yakima与Youngstown之间的距离，2410是Yakima和Yankton之间的距离；以此类推）

- 注释【3】：

这个条件判断第一次肯定会进入到else里面，因为我们要先创建节点，才能以距离作为连接的属性建立边关系。

```python
i = 1  
(city, coordpop) = line.split("[")  # 通过'['将数据截断，分为城市和coordpop(经纬人口)
cities.insert(0, city)  # 在列表中的index=0处添加城市
(coord, pop) = coordpop.split("]")  # 通过']'将coodrpop(经纬人口)截断成coord经纬和pop人口
(y, x) = coord.split(",")  # 用','分割数据，由于数据集中给的是(纬度(y轴), 经度(x轴))，我们之后再position时会用(x,y)，所以要转换一下
G.add_node(city)  # 以city作为节点
# assign position - Convert string to lat/long
x = -float(x) / 100  # 十进制的经纬度中，精度是负的，所以也要改一下（地理知识，我也不知道为什么）
y = float(y) / 100
G.position[city] = (x, y)  # 给city节点的position特征添加值
pop = float(pop) / 1000  # 人口进行缩放
G.population[city] = pop  # 添加population特征值
```

- 注释【4】：

在有了节点之后，我们就可以对其进行连接的创建。

```python
if numfind.match(line):  # 记录城市间距离的行
    dist = line.split()  # 对距离的数据进行切割
    for d in dist:  # 遍历
        G.add_edge(city, cities[i], weight=int(d))
        """
        假如说我们现在有两个节点了，分别是Youngstown, OH 和 Yankton, SD；
        由else代码块中的逻辑，我们可以知道：Yankton, SD是被insert到index=0的位置，且此时city=Yankton, SD
        那么Youngstown, OH就在cities列表中被向后推了1个index，即他的index为1；
        那么我们创建的就是city(Yankton, SD)和cities[i](Youngstown, OH)的连接 注：i=1
        且我们将从dist中拿出的距离作为了边的属性特征
        """
        i = i + 1
        """
        如果说我们现在有了三个节点，分别是Youngstown, OH、Yankton, SD、Yakima, WA
        那么cities = ['Yakima, WA', 'Yankton, SD', 'Youngstown, OH']
        city = 'Yakima, WA'
        此时dist = ['1513', '2410']
        连接建立：
        1. Yakima, WA ---1513---Yankton, SD
        2. Yakima, WA ---2410---Youngstown, OH
        """
```

### 2.2.2 查看图

通过上面得逻辑，我们已经构建好了图模型，现在我们来观察一下他的信息。

```python
print(G)
>>> Graph with 128 nodes and 8128 edges
```

> 一共有128个节点，8128个连接。

```python
G.nodes
>>> 
NodeView(('Youngstown, OH', 'Yankton, SD', 'Yakima, WA', 'Worcester, MA', 'Wisconsin Dells, WI', 'Winston-Salem, NC', 'Winnipeg, MB', 'Winchester, VA', 'Wilmington, NC', 'Wilmington, DE', 'Williston, ND', 'Williamsport, PA', 'Williamson, WV', 'Wichita Falls, TX', 'Wichita, KS', 'Wheeling, WV', 'West Palm Beach, FL', 'Wenatchee, WA'......
```

> 打印了所有得节点名称

### 2.2.3 查看图的特征

- 经纬坐标

```python
G.position
>>>
{'Youngstown, OH': (-80.65, 41.1),
 'Yankton, SD': (-97.39, 42.88),
 'Yakima, WA': (-120.51, 46.6),
 'Worcester, MA': (-71.8, 42.27),
 'Wisconsin Dells, WI': (-89.77, 43.63),...
```

> 每个节点都会有经纬度。

- 人口数据

```python
G.population
>>>
{'Youngstown, OH': 115.436,
 'Yankton, SD': 12.011,
 'Yakima, WA': 49.826,
 'Worcester, MA': 161.799,
 'Wisconsin Dells, WI': 2.521,
 'Winston-Salem, NC': 131.885,
 'Winnipeg, MB': 564.473,
```

- 连通关系

```python
G.edges(data=True)
>>>
dgeDataView([('Youngstown, OH', 'Yankton, SD', {'weight': 966}), ('Youngstown, OH', 'Yakima, WA', {'weight': 2410}), ('Youngstown, OH', 'Worcester, MA', {'weight': 604}), ('Youngstown, OH', 'Wisconsin Dells, WI', {'weight': 595}), ('Youngstown, OH', 'Winston-Salem, NC', {'weight': 494}),...
```

### 2.2.4 筛选小于指定阈值的城市

```python
H = nx.Graph()  # 新建一个无节点无向图
for v in G:  # 遍历G中的节点
    H.add_node(v)  # 添加节点到H
for (u, v, d) in G.edges(data=True):  # 参考('Youngstown, OH', 'Yankton, SD', {'weight': 966})
    if d["weight"] < 800:  # 距离小于800
        H.add_edge(u, v)  # 建立连接
```

### 2.2.5 可视化

```python
# 节点颜色-节点度
node_color = [float(H.degree(v)) for v in H]  # 将图H中所有节点的度拿出来当作node_color
# print(node_color)
# 节点尺寸-节点人口
node_size = [G.population[v] for v in H]  # 将图H中，节点的population拿出当作node_size
# print(node_size)
```

```python
fig = plt.figure(figsize=(12, 10))
nx.draw(
    H,
    G.position,  # 将position作为坐标
    node_size=node_size,
    node_color=node_color,
    with_labels=True,
)
plt.show()
```

![image-20230219180327659](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302191803793.png)

## 2.3 有向图可视化

```python
# 图数据挖掘
import networkx as nx

import numpy as np

# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

# plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
import matplotlib as mpl
```

### 2.3.1 创建有向图

```python
seed = 13648  # 固定随机数种子
G = nx.random_k_out_graph(10, 3, 0.5, seed=seed) # 随机的K-out图
pos = nx.spring_layout(G, seed=seed)  # 弹簧布局
```

### 2.3.2 初步可视化

```python
nx.draw(G, pos, with_labels=True)
```

![image-20230220112601743](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201126820.png)

### 2.3.3 高级可视化

- 节点大小

```python
# 节点大小
node_sizes = [12 + 10 * i for i in range(len(G))]
node_sizes
>>> 
[12, 22, 32, 42, 52, 62, 72, 82, 92, 102]
```

- 节点颜色

```python
# 节点颜色
M = G.number_of_edges()  # 图中边的个数
edge_colors = range(2, M + 2)
edge_colors
>>> 
range(2, 32)
```

- 节点透明度

```python
# 节点透明度
edge_alphas = [(5 + i) / (M + 4) for i in range(M)]
edge_alphas
>>>
[0.14705882352941177,
 0.17647058823529413,
 0.20588235294117646,
 0.23529411764705882,
 0.2647058823529412,
 0.29411764705882354,...
```

- 配色方案

```python
# 配色方案
cmap = plt.cm.plasma
# cmap = plt.cm.Blues
```

- 绘制

```python
plt.figure(figsize=(10,8))  # 设置画布

# 绘制节点
nodes = nx.draw_networkx_nodes(G, pos, node_size=node_sizes, node_color="indigo")

# 绘制连接
edges = nx.draw_networkx_edges(
    G,
    pos,
    node_size=node_sizes,   # 节点尺寸
    arrowstyle="->",        # 箭头样式
    arrowsize=20,           # 箭头尺寸
    edge_color=edge_colors, # 连接颜色
    edge_cmap=cmap,         # 连接配色方案
    width=4                # 连接线宽
)


# 设置每个连接的透明度
for i in range(M):
    edges[i].set_alpha(edge_alphas[i])

# 调色图例
pc = mpl.collections.PatchCollection(edges, cmap=cmap)
pc.set_array(edge_colors)
plt.colorbar(pc)

ax = plt.gca()
ax.set_axis_off()
```

![image-20230220162322009](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201623097.png)

## 2.4 国际象棋对局分析

分析1886-1985年的国际象棋对局数据，绘制多路有向图，节点尺寸为胜利个数，连接宽度为对局个数。

```python
# 图数据挖掘
import networkx as nx

# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

# plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

### 2.4.1 导入数据

```python
import pandas as pd
df = pd.read_csv('WCC.csv')
df
```

![image-20230220164123469](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201641707.png)

### 2.4.2 构建MultiDiGraph

```python
G = nx.from_pandas_edgelist(df, 'White', 'Black', edge_attr=True, create_using=nx.MutliDiGraph())
```

> 使用pandas导入csv文件创建节点和边。
>
> 参数解析：df，csv文件
>
> "White","Black"：代表节点的df中的列
>
> edge_attr：连接是否带有属性特征
>
> create_using：使用nx中的MultiDiGraph

### 2.4.3 数据探索

```python
print('棋手（节点）个数', G.number_of_nodes())
print('棋局（连接）个数', G.number_of_edges())
>>>
棋手（节点）个数 25
棋局（连接）个数 685
```

```python
# 所有节点
G.nodes
>>>
NodeView(('Zukertort, Johannes H', 'Steinitz, Wilhelm', 'Chigorin, Mikhail I', 'Gunsberg, Isidor A', 'Lasker, Emanuel', 'Marshall, Frank J', 'Tarrasch, Siegbert', 'Janowski, Dawid M', 'Schlechter, Carl', 'Capablanca, Jose Raul', 'Alekhine, Alexander A', 'Bogoljubow, Efim D', 'Euwe, Max', 'Keres, Paul', 'Smyslov, Vassily V', 'Reshevsky, Samuel H', 'Botvinnik, Mikhail M', 'Bronstein, David I', 'Tal, Mikhail N', 'Petrosian, Tigran V', 'Spassky, Boris V', 'Fischer, Robert J', 'Korchnoi, Viktor L', 'Karpov, Anatoly', 'Kasparov, Gary'))
```

```python
# 所有连接（带特征）
G.edges(data=True)
>>>
OutMultiEdgeDataView([('Zukertort, Johannes H', 'Steinitz, Wilhelm', {'Date': '1886.01.11', 'EventDate': '1886.01.11', 'Event': 'World Championship 1st', 'Site': 'USA', 'ECO': 'D11', 'Round': 1, 'Result': '0-1'}), ('Zukertort, Johannes H', 'Steinitz, Wilhelm', {'Date': '1886.01.15', 'EventDate': '1886.01.11', 'Event': 'World Championship 1st', 'Site': 'USA', 'ECO': 'D10', 'Round': 3, 'Result': '1-0'}),...
```

```python
# 两个棋手的所有棋局
G.get_edge_data('Zukertort, Johannes H', 'Steinitz, Wilhelm')
>>>
{0: {'Date': '1886.01.11',
  'EventDate': '1886.01.11',
  'Event': 'World Championship 1st',
  'Site': 'USA',
  'ECO': 'D11',
  'Round': 1,
  'Result': '0-1'},
 1: {'Date': '1886.01.15',
  'EventDate': '1886.01.11',
  'Event': 'World Championship 1st',
  'Site': 'USA',
  'ECO': 'D10',
  'Round': 3,
  'Result': '1-0'},...
```

### 2.4.4 初步可视化

```python
pos = nx.spring_layout(G, seed=10)  # 弹簧布局
nx.draw(G, pos)  # 绘制
```

![image-20230220165133263](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201651329.png)

### 2.4.5 连通域分析

```python
# 将G转为无向图，分析连通域
H = G.to_undirected()
```

```python
for each in nx.connected_components(H):
    print('连通域')
    print(H.subgraph(each))
    print('包含节点')
    print(each)
    print('\n')
>>>
连通域
MultiGraph with 22 nodes and 304 edges
包含节点
{'Smyslov, Vassily V', 'Tarrasch, Siegbert', 'Steinitz, Wilhelm', 'Marshall, Frank J', 'Lasker, Emanuel', 'Spassky, Boris V', 'Petrosian, Tigran V', 'Gunsberg, Isidor A', 'Bronstein, David I', 'Zukertort, Johannes H', 'Keres, Paul', 'Fischer, Robert J', 'Schlechter, Carl', 'Capablanca, Jose Raul', 'Janowski, Dawid M', 'Tal, Mikhail N', 'Alekhine, Alexander A', 'Chigorin, Mikhail I', 'Euwe, Max', 'Reshevsky, Samuel H', 'Bogoljubow, Efim D', 'Botvinnik, Mikhail M'}


连通域
MultiGraph with 3 nodes and 49 edges
包含节点
{'Karpov, Anatoly', 'Korchnoi, Viktor L', 'Kasparov, Gary'}
```

### 2.4.6 高级可视化

```python
# 将G转为无向-单连接图
H = nx.Graph(G)
```

```python
H.edges()
>>>
EdgeView([('Zukertort, Johannes H', 'Steinitz, Wilhelm'), ('Steinitz, Wilhelm', 'Chigorin, Mikhail I'), ('Steinitz, Wilhelm', 'Gunsberg, Isidor A'), ('Steinitz, Wilhelm', 'Lasker, Emanuel'), ('Lasker, Emanuel', 'Marshall, Frank J'), ('Lasker, Emanuel', 'Tarrasch, Siegbert'), ('Lasker, Emanuel', 'Janowski, Dawid M'), ('Lasker, Emanuel', 'Schlechter, Carl'), ('Lasker, Emanuel', 'Capablanca, Jose Raul'), ('Capablanca, Jose Raul', 'Alekhine, Alexander A'), ('Alekhine, Alexander A', 'Bogoljubow, Efim D'), ('Alekhine, Alexander A', 'Euwe, Max'), ('Euwe, Max', 'Keres, Paul'), ('Euwe, Max', 'Smyslov, Vassily V'), ('Euwe, Max', 'Botvinnik, Mikhail M'), ('Euwe, Max', 'Reshevsky, Samuel H'), ('Keres, Paul', 'Smyslov, Vassily V'), ('Keres, Paul', 'Botvinnik, Mikhail M'), ('Keres, Paul', 'Reshevsky, Samuel H'), ('Smyslov, Vassily V', 'Reshevsky, Samuel H'), ('Smyslov, Vassily V', 'Botvinnik, Mikhail M'), ('Reshevsky, Samuel H', 'Botvinnik, Mikhail M'), ('Botvinnik, Mikhail M', 'Bronstein, David I'), ('Botvinnik, Mikhail M', 'Tal, Mikhail N'), ('Botvinnik, Mikhail M', 'Petrosian, Tigran V'), ('Petrosian, Tigran V', 'Spassky, Boris V'), ('Spassky, Boris V', 'Fischer, Robert J'), ('Korchnoi, Viktor L', 'Karpov, Anatoly'), ('Karpov, Anatoly', 'Kasparov, Gary')])
```

```python
# 两个棋手的所有棋局
len(G.get_edge_data('Zukertort, Johannes H', 'Steinitz, Wilhelm'))
>>>
10
```

```python
# 两个棋手节点之间的 连接宽度 与 棋局个数 成正比
edgewidth = [len(G.get_edge_data(u, v)) for u, v in H.edges()]
edgewidth
>>>
[10,
 19,
 10,
 9,
 7,
 8,
 11,
 5,
 7,
 17,
 26,
 27,...
```

```python
# 棋手节点的大小 与 赢棋次数 成正比
wins = dict.fromkeys(G.nodes(), 0) # 生成每个棋手作为key的dict
for (u, v, d) in G.edges(data=True):  # (u,v,连接属性)
    r = d["Result"].split("-")  # 使用'-'切分对局分数
    if r[0] == "1":  # u获胜
        wins[u] += 1.0  # 以选手u的名字为key的dict的value+1.0
    elif r[0] == "1/2":  # 平局，各加0.5
        wins[u] += 0.5 
        wins[v] += 0.5
    else:  # v获胜
        wins[v] += 1.0
nodesize = [wins[v] * 50 for v in H]  # 放大50倍
```

```python
print(wins)
>>>
{'Zukertort, Johannes H': 7.5,
 'Steinitz, Wilhelm': 53.0,
 'Chigorin, Mikhail I': 17.0,
 'Gunsberg, Isidor A': 8.5,
 'Lasker, Emanuel': 61.5,
 'Marshall, Frank J': 3.5,
 'Tarrasch, Siegbert': 5.5,...
```

```python
print(nodesize)
>>>
[375.0,
 2650.0,
 850.0,
 425.0,
 3075.0,
 175.0,
 275.0,...
```

```python
# 使用kamada_kawai_layout布局
pos = nx.kamada_kawai_layout(H)

# 手动微调节点的横坐标（越大越靠右）、纵坐标（越大越靠下）
pos["Reshevsky, Samuel H"] += (0.05, -0.10)
pos["Botvinnik, Mikhail M"] += (0.03, -0.06)
pos["Smyslov, Vassily V"] += (0.05, -0.03)
```

```python
fig, ax = plt.subplots(figsize=(12, 12))

# 可视化连接
nx.draw_networkx_edges(H, pos, alpha=0.3, width=edgewidth, edge_color="m")

# 可视化节点
nx.draw_networkx_nodes(H, pos, node_size=nodesize, node_color="#210070", alpha=0.9)

# 节点名称文字说明
label_options = {"ec": "k", "fc": "white", "alpha": 0.7}
nx.draw_networkx_labels(H, pos, font_size=14, bbox=label_options)

# 标题和图例
font = {"fontname": "Helvetica", "color": "k", "fontweight": "bold", "fontsize": 16}
ax.set_title("World Chess Championship Games: 1886 - 1985", font)
# 图例字体颜色
font["color"] = "r"

# 文字说明
ax.text(
    0.80,
    0.10,
    "edge width = # games played",
    horizontalalignment="center",
    transform=ax.transAxes,
    fontdict=font,
)
ax.text(
    0.80,
    0.06,
    "node size = # games won",
    horizontalalignment="center",
    transform=ax.transAxes,
    fontdict=font,
)

# 调整图的大小，提高可读性
ax.margins(0.1, 0.05)
fig.tight_layout()
plt.axis("off")
plt.show()
```

![image-20230220170723034](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201707154.png)

## 2.5 自定义节点图标

```python
# 图数据挖掘
import networkx as nx

# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

# plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
import PIL
```

### 2.5.1 设置图标路径

```python
icons = {
    'router': 'database-storage.png',
    'switch': 'wifi.png',
    'PC': 'laptop.png',
}

# 载入图像
images = {k: PIL.Image.open(fname) for k, fname in icons.items()}  # 字典推导式
```

```python
print(images)
>>>
{'router': <PIL.PngImagePlugin.PngImageFile image mode=RGBA size=512x512>,
 'switch': <PIL.PngImagePlugin.PngImageFile image mode=RGBA size=512x512>,
 'PC': <PIL.PngImagePlugin.PngImageFile image mode=RGBA size=512x512>}
```

### 2.5.2 建立节点

```python
# 创建节点
G.add_node("router", image=images["router"])  # 创建节点'router',设置属性image=images["router"]
for i in range(1, 4):  # 创建3个交换机节点
    G.add_node(f"switch_{i}", image=images["switch"])  # 建立交换机节点1，2，3；并设置属性
    for j in range(1, 4): # 为每个交换机节点建立3个PC节点（一共是9个）
        G.add_node("PC_" + str(i) + "_" + str(j), image=images["PC"])  # 共新添9个节点，并设置属性

# 创建路由器router和3台交换机switch的连接
G.add_edge("router", "switch_1")
G.add_edge("router", "switch_2")
G.add_edge("router", "switch_3")

# 对于每个交换机switch节点，都和对应的PC建立连接
for u in range(1, 4):
    for v in range(1, 4):
        G.add_edge("switch_" + str(u), "PC_" + str(u) + "_" + str(v))
```

### 2.5.3 原生绘制

```python
nx.draw(G, with_labels=True)
```

![image-20230220171838457](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201718550.png)

### 2.5.4 使用图标作为节点

```python
fig, ax = plt.subplots()
```

![image-20230220171921061](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201719153.png)

```python
# 调节图片尺寸（相对于 X 轴）
icon_size = (ax.get_xlim()[1] - ax.get_xlim()[0]) * 0.03
icon_center = icon_size / 2.0
```

```python
pos = nx.spring_layout(G, seed=1)
fig, ax = plt.subplots(figsize=(14,10))

# 绘制连接
# min_source_margin 和 min_target_margin 调节连接端点到节点的距离（越大距离越远）
nx.draw_networkx_edges(
    G,
    pos=pos,
    ax=ax,
    arrows=True,
    arrowstyle="-",
    min_source_margin=30,
    min_target_margin=30,
)

# 给每个节点添加各自的图片
for n in G.nodes:
    xf, yf = ax.transData.transform(pos[n]) # data坐标 转 display坐标
    xa, ya = fig.transFigure.inverted().transform((xf, yf)) # display坐标 转 figure坐标
    
    a = plt.axes([xa - icon_center, ya - icon_center, icon_size, icon_size])
    a.imshow(G.nodes[n]["image"])
    a.axis("off")

plt.show()
```

![image-20230220172758993](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201727101.png)

## 2.6 Ego图

现实社会中很多现象都能抽象为Ego图

```python
# 图数据挖掘
import networkx as nx

import numpy as np

# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

### 2.6.1 创建图

```python
from operator import itemgetter
```

```
创建Barabási-Albert无标度网络
论文：A. L. Barabási and R. Albert "Emergence of scaling in random networks", Science 286, pp 509-512, 1999.
n个节点逐渐生长，新节点与degree高的旧节点产生m条连接。
```

```python
n = 1000
m = 2
seed = 20532
G = nx.barabasi_albert_graph(n, m, seed=seed)
```

### 2.6.2 原生可视化

```python
pos = nx.spring_layout(G, seed=seed)
nx.draw(G, pos)
```

![image-20230220173054591](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201730677.png)

### 2.6.3 度最大的节点

```python
largest_hub, degree = sorted(G.degree(), key=itemgetter(1))[-1]
```

```python
# 度最大的节点
print(largest_hub)
print(degree)
print(G.edges(4))
>>>
4
88
EdgeDataView([(4, 2), (4, 3), (4, 8), (4, 11), (4, 12), (4, 13), (4, 15), (4, 18), (4, 25), (4, 26), (4, 32), (4, 38), (4, 40), (4, 41), (4, 45), (4, 53), (4, 58), (4, 67), (4, 69), (4, 79), (4, 83), (4, 85), (4, 89), (4, 90), (4, 103), (4, 104), (4, 109), (4, 124), (4, 125), (4, 141), (4, 143), (4, 151), (4, 159), (4, 175), (4, 176), (4, 208), (4, 215), (4, 230), (4, 262), (4, 270), (4, 282), (4, 283), (4, 296), (4, 303), (4, 314), (4, 321), (4, 333), (4, 345), (4, 364), (4, 368), (4, 380), (4, 391), (4, 406), (4, 412), (4, 414), (4, 421), (4, 439), (4, 442), (4, 465), (4, 479), (4, 481), (4, 505), (4, 509), (4, 530), (4, 538), (4, 541), (4, 548), (4, 573), (4, 580), (4, 584), (4, 586), (4, 645), (4, 657), (4, 678), (4, 689), (4, 710), (4, 711), (4, 723), (4, 752), (4, 873), (4, 911), (4, 913), (4, 914), (4, 956), (4, 968), (4, 970), (4, 975), (4, 994)])
```

### 2.6.4 Ego Graph

```python
hub_ego = nx.ego_graph(G, largest_hub, radius=1)
```

```python
pos = nx.spring_layout(hub_ego, seed=seed)
nx.draw(hub_ego, pos, node_color="b", node_size=50, with_labels=False)

# 大红显示主节点
options = {"node_size": 300, "node_color": "r"}
nx.draw_networkx_nodes(hub_ego, pos, nodelist=[largest_hub], **options)

plt.show()
```

![image-20230220183206611](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201832709.png)

# 3. 图数据挖掘

案例：北京上海地铁站的图数据挖掘

## 3.1 PageRank API

```python
# 图数据挖掘
import networkx as nx

# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

```python
# 创建一个星状图
G = nx.star_graph(7)
```

```python
# 绘制
nx.draw(G, with_labels = True)
```

![image-20230220183549716](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201835821.png)

```python
# 计算节点重要度
pagerank = nx.pagerank(G, alpha=0.8)
print(pagerank)
>>>
{0: 0.4583348922684132,
 1: 0.07738072967594098,
 2: 0.07738072967594098,
 3: 0.07738072967594098,
 4: 0.07738072967594098,
 5: 0.07738072967594098,
 6: 0.07738072967594098,
 7: 0.07738072967594098}
```

> 可以看出0号节点的重要度很高。
>
> 注意点：
>
> 1. PageRank只对有向图有效，我们这里传入的是无向图，那么NetworkX就会自动将其转换为双向图。
> 2. 我们可以通过`PageRank?`查看其源码和论文链接等信息。

## 3.2 Node Degree分析

Node Degree可以反映出节点的重要度。

```python
# 图数据挖掘
import networkx as nx

import numpy as np

# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

### 3.2.1 创建图

```python
# 创建 Erdős-Rényi 随机图，也称作 binomial graph
# n-节点数
# p-任意两个节点产生连接 的概率

G = nx.gnp_random_graph(100, 0.02, seed=10374196)
```

```python
# 初步可视化
pos = nx.spring_layout(G, seed=10)
nx.draw(G, pos)
```

![image-20230220190749484](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201907589.png)

### 3.2.2 最大连通子域

```python
# 查看有多少连通分量
print(nx.number_connected_components(G))
>>> 
19
```

```python
# 获取最大的连通分量构成的子图
Gcc = G.subgraph(sorted(nx.connected_components(G), key=len, reverse=True)[0])
```

```python
pos = nx.spring_layout(Gcc, seed=10396953)
nx.draw_networkx_nodes(Gcc, pos, node_size=20)
nx.draw_networkx_edges(Gcc, pos, alpha=0.4)
```

![image-20230220190739859](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201907965.png)

```python
plt.figure(figsize=(12,8))
pos = nx.spring_layout(Gcc, seed=10396953)

# 设置其它可视化样式
options = {
    "font_size": 12,
    "node_size": 350,
    "node_color": "white",
    "edgecolors": "black",
    "linewidths": 1, # 节点线宽
    "width": 2, # edge线宽
}

nx.draw_networkx(Gcc, pos, **options)

plt.title('Connected components of G', fontsize=20)
plt.axis('off')
plt.show()
```

![image-20230220190839970](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201908086.png)

```python
# 每个节点的度
G.degree()
>>>
DegreeView({0: 2, 1: 4, 2: 4, 3: 4, 4: 2, 5: 4, 6: 4, 7: 2, 8: 2, 9: 1, 10: 3, 11: 0, 12: 1, 13: 2, 14: 6, 15: 2, 16: 0, 17: 0, 18: 3, 19: 1, 20: 3, 21: 1, 22: 1, 23: 1, 24: 1, 25: 3, 26: 0, 27: 2, 28: 2, 29: 0, 30: 2, 31: 1, 32: 1, 33: 0, 34: 1, 35: 4, 36: 2, 37: 2, 38: 1, 39: 5, 40: 5, 41: 1, 42: 4, 43: 1, 44: 0, 45: 2, 46: 3, 47: 1, 48: 2, 49: 2, 50: 3, 51: 2, 52: 0, 53: 3, 54: 0, 55: 3, 56: 1, 57: 2, 58: 2, 59: 2, 60: 1, 61: 1, 62: 0, 63: 2, 64: 4, 65: 5, 66: 2, 67: 0, 68: 2, 69: 2, 70: 1, 71: 3, 72: 2, 73: 4, 74: 1, 75: 2, 76: 2, 77: 2, 78: 5, 79: 2, 80: 0, 81: 1, 82: 2, 83: 1, 84: 2, 85: 0, 86: 4, 87: 2, 88: 4, 89: 2, 90: 2, 91: 3, 92: 0, 93: 2, 94: 0, 95: 4, 96: 1, 97: 4, 98: 0, 99: 2})
```

```python
# 按照degree排序获得sequence
degree_sequence = sorted((d for n, d in G.degree()), reverse=True)
print(degree_sequence)
>>>
[6,
 5,
 5,
 5,
 5,
 4,
 4,
 4,
 4,
 4,
 4,...
```

```python
plt.figure(figsize=(12,8))
plt.plot(degree_sequence, "b-", marker="o")
plt.title('Degree Rank Plot', fontsize=20)
plt.ylabel('Degree', fontsize=25)
plt.xlabel('Rank', fontsize=25)
plt.tick_params(labelsize=20) # 设置坐标文字大小
plt.show()
```

![image-20230220191202713](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201912830.png)

```python
# 将degree_sequence进行去重，并且要返回每个元素出现的次数
np.unique(degree_sequence, return_counts=True)
>>>
(array([0, 1, 2, 3, 4, 5, 6]),
 array([16, 22, 34, 10, 13,  4,  1], dtype=int64))
```

```python
X = np.unique(degree_sequence, return_counts=True)[0]
Y = np.unique(degree_sequence, return_counts=True)[1]
print(X)
print(Y)
>>>
array([0, 1, 2, 3, 4, 5, 6])
array([16, 22, 34, 10, 13,  4,  1])
```

```python
plt.figure(figsize=(12,8))
# plt.bar(*np.unique(degree_sequence, return_counts=True))
plt.bar(X, Y)

plt.title('Degree Histogram', fontsize=20)
plt.ylabel('Number', fontsize=25)
plt.xlabel('Degree', fontsize=25)
plt.tick_params(labelsize=20) # 设置坐标文字大小
plt.show()
plt.show()
```

![image-20230220191745975](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201917100.png)

## 3.3 棒棒糖图特征分析

```python
# 图数据挖掘
import networkx as nx

# 数据可视化
import matplotlib.pyplot as plt
%matplotlib inline

# plt.rcParams['font.sans-serif']=['SimHei']  # 用来正常显示中文标签  
plt.rcParams['axes.unicode_minus']=False  # 用来正常显示负号
```

### 3.3.1 导入图

```python
# 第一个参数指定头部节点数，第二个参数指定尾部节点数
G = nx.lollipop_graph(4, 7)
```

### 3.3.2 可视化

```python
pos = nx.spring_layout(G, seed=3068)
nx.draw(G, pos=pos, with_labels=True)
plt.show()
```

![image-20230220193113931](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302201931063.png)

### 3.3.3 图数据分析

- 半径

```python
# 半径
nx.radius(G)
>>>
4
```

- 直径

```python
# 直径
nx.diameter(G)
>>> 
8
```

- 偏心度

```python
# 偏心度：每个节点到图中其它节点的最远距离
nx.eccentricity(G)
>>>
{0: 8, 1: 8, 2: 8, 3: 7, 4: 6, 5: 5, 6: 4, 7: 5, 8: 6, 9: 7, 10: 8}
```

- 中心节点

```python
# 中心节点，偏心度与半径相等的节点
nx.center(G)
>>>
[6]
```

- 外围节点

```python
# 外围节点，偏心度与直径相等的节点
nx.periphery(G)
>>>
[0, 1, 2, 10]
```

- Desity

n为节点个数，m为连接个数

对于无向图：

$$
density = \frac{2m}{n(n-1)}
$$

对于有向图：

$$
density = \frac{m}{n(n-1)}
$$

无连接图的density为0，全连接图的density为1，Multigraph（多重连接图）和带self loop图的density可能大于1。

```python
nx.density(G)
>>>
0.23636363636363636
```

- 3号节点到其他节点的度数

```python
node_id = 3
nx.single_source_shortest_path_length(G, node_id)
>>>
{3: 0, 0: 1, 1: 1, 2: 1, 4: 1, 5: 2, 6: 3, 7: 4, 8: 5, 9: 6, 10: 7}
```

- 两两节点之间的度数

```python
pathlengths = []
for v in G.nodes():
    spl = nx.single_source_shortest_path_length(G, v)
    for p in spl:
        print('{} --> {} 最短距离 {}'.format(v, p, spl[p]))
        pathlengths.append(spl[p])

>>>
0 --> 0 最短距离 0
0 --> 1 最短距离 1
0 --> 2 最短距离 1
0 --> 3 最短距离 1
0 --> 4 最短距离 2
0 --> 5 最短距离 3
0 --> 6 最短距离 4
0 --> 7 最短距离 5
0 --> 8 最短距离 6
0 --> 9 最短距离 7
0 --> 10 最短距离 8...
```

- 最短路径

```python
# 平均最短距离
sum(pathlengths) / len(pathlengths)
>>>
3.2231404958677685
```

- 不同距离节点对个数

```python
dist = {}
for p in pathlengths:
    if p in dist:
        dist[p] += 1
    else:
        dist[p] = 1
        
dist
>>>
{0: 11, 1: 26, 2: 18, 3: 16, 4: 14, 5: 12, 6: 10, 7: 8, 8: 6}
```

## 3.4 计算节点特征

```python
import networkx as nx
import matplotlib.pyplot as plt
import matplotlib.colors as mcolors
%matplotlib inline
```

### 3.4.1 定义绘制函数

```python
def draw(G, pos, measures, measure_name):
    """
    绘制
    :param G: 图
    :param pos: 坐标
    :param measures: 使用的尺标
    :param measure_name: 度量尺标的名称
    """
    nodes = nx.draw_networkx_nodes(G, pos, node_size=250, cmap=plt.cm.plasma, 
                                   node_color=list(measures.values()),
                                   nodelist=measures.keys())
    nodes.set_norm(mcolors.SymLogNorm(linthresh=0.01, linscale=1, base=10))
    edges = nx.draw_networkx_edges(G, pos)

    plt.title(measure_name)
    plt.colorbar(nodes)
    plt.axis('off')
    plt.show()
```

### 3.4.2 导入图

- 无向图

  > 使用的是空手道俱乐部数据。

```python
G = nx.karate_club_graph()
pos = nx.spring_layout(G, seed=675)
nx.draw(G, pos, with_labels=True)
```

![image-20230221151201404](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211512491.png)

- 有向图

  ```python
  DiG = nx.DiGraph()
  DiG.add_edges_from([(2, 3), (3, 2), (4, 1), (4, 2), (5, 2), (5, 4),
                      (5, 6), (6, 2), (6, 5), (7, 2), (7, 5), (8, 2),
                      (8, 5), (9, 2), (9, 5), (10, 5), (11, 5)])
  nx.draw(DiG, pos, with_labels=True)
  ```

![image-20230221151249840](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211512904.png)

### 3.4.3 Degree Centrality

**无向图：**

- 无向图：直接使用节点的度绘制

```python
# (节点，度)
list(nx.degree(G))
>>>
[(0, 16),
 (1, 9),
 (2, 10),
 (3, 6),
 (4, 3),
 (5, 4),...
```

```python
dict(G.degree())
>>>
{0: 16,
 1: 9,
 2: 10,
 3: 6,
 4: 3,
 5: 4,...
```

```python
draw(G, pos, dict(G.degree()), 'Node Degree')
```

![image-20230221151415756](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211514827.png)

- 无向图：使用nx的API求Degree Centrality.

```python
nx.degree_centrality(G)
>>>
{0: 0.48484848484848486,
 1: 0.2727272727272727,
 2: 0.30303030303030304,
 3: 0.18181818181818182,
 4: 0.09090909090909091,
 5: 0.12121212121212122,...
```

```python
draw(G, pos, nx.degree_centrality(G), 'Degree Centrality')
```

![image-20230221153050899](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211530969.png)

**有向图：**

```python
# 入度中心性
nx.in_degree_centrality(DiG)
>>>
{2: 0.7000000000000001,
 3: 0.1,
 4: 0.1,
 1: 0.1,
 5: 0.6000000000000001,
 6: 0.1,
 7: 0.0,
 8: 0.0,
 9: 0.0,...
```

```python
# 出度中心性
nx.out_degree_centrality(DiG)
>>>
{2: 0.1,
 3: 0.1,
 4: 0.2,
 1: 0.0,
 5: 0.30000000000000004,...
```

```python
draw(DiG, pos, nx.in_degree_centrality(DiG), 'DiGraph Degree Centrality')
```

![image-20230221153254194](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211532261.png)

```python
draw(DiG, pos, nx.out_degree_centrality(DiG), 'DiGraph Degree Centrality')
```

![image-20230221153309896](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211533960.png)



### 3.4.4 Node Centrality

Node Degree 只考虑连接的数量而不考虑质量；

Node Centrality 将连接的质量也纳入考虑。

衡量Node Centrality的方法：

- Eigenvector centrality
- Betweenness centrality
- Closeness centrality

#### 3.4.4.1 Eigenvector Centrality

**无向图：**

```python
nx.eigenvector_centrality(G)
>>>
{0: 0.3554834941851943,
 1: 0.2659538704545025,
 2: 0.3171893899684447,
 3: 0.21117407832057059,
 4: 0.0759664588165738,...
```

```python
draw(G, pos, nx.eigenvector_centrality(G), 'Eigenvector Centrality')
```

![image-20230221153707707](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211537792.png)

**有向图：**

```python
nx.eigenvector_centrality_numpy(DiG)
>>>
{2: 0.7071067871666155,
 3: 0.7071067752064792,
 4: 7.973423921114883e-09,
 1: 7.973424032137185e-09,
 5: 7.973423712948066e-09,
 6: 7.973423865603732e-09,...
```

```python
draw(DiG, pos, nx.eigenvector_centrality_numpy(DiG), 'DiGraph Eigenvector Centrality')
```

![image-20230221153800506](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211538579.png)

#### 3.4.4.2 Between Centrality

```python
nx.betweenness_centrality(G)
>>>
{0: 0.43763528138528146,
 1: 0.053936688311688304,
 2: 0.14365680615680618,
 3: 0.011909271284271283,
 4: 0.0006313131313131313,
 5: 0.02998737373737374,
```

```python
draw(G, pos, nx.betweenness_centrality(G), 'Betweenness Centrality')
```

![image-20230221154025013](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211540086.png)

#### 3.4.4.3 Clonessness Centrality

```python
nx.closeness_centrality(G)
>>>
{0: 0.5689655172413793,
 1: 0.4852941176470588,
 2: 0.559322033898305,
 3: 0.4647887323943662,
 4: 0.3793103448275862,
 5: 0.38372093023255816,...
```

```python
draw(G, pos, nx.closeness_centrality(G), 'Closeness Centrality')
```

![image-20230221154109866](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211541959.png)

### 3.4.5 PageRank

```python
nx.pagerank(DiG, alpha=0.85)
>>>
{2: 0.38439863456604384,
 3: 0.3429125997558898,
 4: 0.039087092099966095,
 1: 0.03278149315934399,
 5: 0.08088569323449774,
 6: 0.039087092099966095,
```

```python
draw(DiG, pos, nx.pagerank(DiG, alpha=0.85), 'DiGraph PageRank')
```

![image-20230221154314247](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211543329.png)

### 3.4.6 Clustering Coefficient

```python
nx.triangles(G)
>>>
{0: 18,
 1: 12,
 2: 11,
 3: 10,
 4: 2,...
```

```python
nx.triangles(G, 0)
>>>
18
```

```python
draw(G, pos, nx.triangles(G), 'Triangles')
```

![image-20230221160228551](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211602665.png)

```python
nx.clustering(G)
>>>
{0: 0.15,
 1: 0.3333333333333333,
 2: 0.24444444444444444,
 3: 0.6666666666666666,
 4: 0.6666666666666666,
 5: 0.5,...
```

```python
nx.clustering(G, 0)
>>>
0.15
```

```python
draw(G, pos, nx.clustering(G), 'Clustering Coefficient')
```

![image-20230221155847375](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211558464.png)



### 3.4.7 Katz Centrality

```python
nx.katz_centrality(G, alpha=0.1, beta=1.0)
>>>
{0: 0.32132459695923254,
 1: 0.23548425319449465,
 2: 0.26576588481542884,
 3: 0.19491320249172545,
 4: 0.12190440564948415,
 5: 0.13097227932864922,...
```

```python
draw(G, pos, nx.katz_centrality(G, alpha=0.1, beta=1.0), 'Katz Centrality')
```

![image-20230221160427995](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211604091.png)

```python
draw(DiG, pos, nx.katz_centrality(DiG, alpha=0.1, beta=1.0), 'DiGraph Katz Centrality')
```

![image-20230221160446117](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211604216.png)

## 3.5 实战上海地铁站

data：上海、北京地铁邻接列表。

![image-20230221161259798](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211612973.png)

> 前一站、下一站、几号线、间隔时间

### 3.5.1 定义工具函数

- 绘图函数

```python
def draw(G, pos, measures, measure_name):
    
    plt.figure(figsize=(20, 20))
    nodes = nx.draw_networkx_nodes(G, pos, node_size=250, cmap=plt.cm.plasma, 
                                   node_color=list(measures.values()),
                                   nodelist=measures.keys())
    nodes.set_norm(mcolors.SymLogNorm(linthresh=0.01, linscale=1, base=10))
    # labels = nx.draw_networkx_labels(G, pos)
    edges = nx.draw_networkx_edges(G, pos)

    plt.title(measure_name, fontsize=30)
    # plt.colorbar(nodes)
    plt.axis('off')
    plt.show()
```

- 字典安置排序函数

```python
def dict_sort_by_value(dict_input):
    '''
    输入字典，输出按值排序的字典
    '''
    return sorted(dict_input.items(),key=lambda x : x[1], reverse=True)  
```

### 3.5.2 数据导入

```python
# 上海地铁站点连接表
df = pd.read_csv('shanghai_subway.csv')
df.head()
>>>
```

![image-20230221170929152](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211709252.png)

### 3.5.3 创建图

```python
# 创建无向图
G = nx.Graph()
```

```python
# 查看前5行数据
for idx, row in df.iterrows():
    if i < 5:
        print(idx, row['前一站'], row['后一站'], row['地铁线'], row['时间（分钟）'])
        i += 1
>>>
0 莘庄 外环路 1 2
1 外环路 莲花路 1 2
2 莲花路 锦江乐园 1 3
3 锦江乐园 上海南站 1 3
4 上海南站 漕宝路 1 3
```

```python
for idx, row in df.iterrows(): # 遍历表格的每一行
    G.add_edges_from([(row['前一站'], row['后一站'])], line=row['地铁线'], time=row['时间（分钟）'])
```

### 3.5.4 查看图的信息

```python
# 节点个数
len(G)
>>>
402
```

```python
# 节点个数
len(G.nodes)
>>>
402
```

```python
# 连接个数
len(G.edges)
>>>
480
```

```python
# 查看连接属性特征
G.edges[('同济大学', '四平路')]
>>>
{'line': 10, 'time': 2}
```

### 3.5.5 可视化

```python
# 节点排版布局-默认弹簧布局
pos = nx.spring_layout(G, seed=123)
plt.figure(figsize=(15,15))
nx.draw(G, pos=pos)
```

![image-20230221171813726](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211718894.png)

### 3.5.6 Shortest Path

```python
# 任意两节点之间是否存在路径
nx.has_path(G, source='昌吉东路', target='同济大学')
>>>
True
```

```python
# 任意两节点之间的最短路径
nx.shortest_path(G, source='昌吉东路', target='李子园', weight='time')
>>>
['昌吉东路', '上海赛车场', '嘉定新城', '马陆', '陈翔公路', '南翔', '桃浦新村', '武威路', '祁连山路', '李子园']
```

```python
# 任意两节点之间的最短路径长度
nx.shortest_path_length(G, source='昌吉东路', target='李子园', weight='time')
>>>
29
```

```python
# 全图平均最短路径
nx.average_shortest_path_length(G, weight='time')
>>>
41.06494956638255
```

### 3.5.7 地铁导航系统

```python
# 指定起始站和终点站
A_station = '昌吉东路'
B_station = '李子园'

# 获取最短路径
shortest_path_list = nx.shortest_path(G, source=A_station, target=B_station, weight='time')

for i in range(len(shortest_path_list)-1):
    previous_station = shortest_path_list[i]  # 前一站
    next_station = shortest_path_list[i+1]  # 后一站
    line_id = G.edges[(previous_station, next_station)]['line'] # 地铁线编号
    time = G.edges[(previous_station, next_station)]['time']    # 时间
    print('{}--->{} {}号线 {}分钟'.format(previous_station, next_station, line_id, time)) # 输出结果
    
# 最短路径长度
print('共计 {} 分钟'.format(nx.shortest_path_length(G, source=A_station, target=B_station, weight='time')))
>>>
昌吉东路--->上海赛车场 11号线 4分钟
上海赛车场--->嘉定新城 11号线 4分钟
嘉定新城--->马陆 11号线 3分钟
马陆--->陈翔公路 11号线 4分钟
陈翔公路--->南翔 11号线 3分钟
南翔--->桃浦新村 11号线 3分钟
桃浦新村--->武威路 11号线 3分钟
武威路--->祁连山路 11号线 2分钟
祁连山路--->李子园 11号线 3分钟
共计 29 分钟
```

### 3.5.8 节点度(同Degree Centrality)

```python
# 查看所有节点的度
dict(G.degree())
>>>
{'莘庄': 2,
 '外环路': 2,
 '莲花路': 2,
 '锦江乐园': 2,
 '上海南站': 5,
 '漕宝路': 4,...
```

```python
# 按照字典的值排序
dict_sort_by_value(dict(G.degree()))
>>>
[('世纪大道', 7),
 ('龙阳路', 7),
 ('徐家汇', 6),
 ('陕西南路', 6),
 ('人民广场', 6),
 ('汉中路', 6),
 ('静安寺', 6),
 ('南京西路', 6),
 ('曹杨路', 6),
 ('上海南站', 5),
 ('宜山路', 5),...
```

```python
draw(G, pos, dict(G.degree()), 'Node Degree')
```

![image-20230221173619284](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211736469.png)

```python
nx.degree_centrality(G)
>>>
{'莘庄': 0.004987531172069825,
 '外环路': 0.004987531172069825,
 '莲花路': 0.004987531172069825,
 '锦江乐园': 0.004987531172069825,
 '上海南站': 0.012468827930174564,
 '漕宝路': 0.00997506234413965,...
```

```python
dict_sort_by_value(nx.degree_centrality(G))
>>>
[('世纪大道', 0.017456359102244388),
 ('龙阳路', 0.017456359102244388),
 ('徐家汇', 0.014962593516209476),
 ('陕西南路', 0.014962593516209476),
 ('人民广场', 0.014962593516209476),
 ('汉中路', 0.014962593516209476),
 ('静安寺', 0.014962593516209476),...
```

```python
draw(G, pos, nx.degree_centrality(G), 'Degree Centrality')
```

![image-20230221173910625](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302211739780.png)

### 3.5.9 Eigenvector Centrality

```python
dict_sort_by_value(nx.eigenvector_centrality(G))
>>>
[('南京西路', 0.34518830475920503),
 ('人民广场', 0.32714367869804883),
 ('陕西南路', 0.29476635705907395),
 ('一大会址·黄陂南路', 0.27634308858888684),
 ('静安寺', 0.27321037099703027),...
```

```python
draw(G, pos, nx.eigenvector_centrality(G), 'Eigenvector Centrality')
```

![image-20230221205849095](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302212058215.png)

### 3.5.10 Betweenness Centrality

```python
nx.betweenness_centrality(G)
>>>
{'莘庄': 0.08596009975062345,
 '外环路': 0.090498753117207,
 '莲花路': 0.09501246882793019,
 '锦江乐园': 0.09950124688279302,
 '上海南站': 0.15500031266221054,
 '漕宝路': 0.1285121727826632,...
```

```python
draw(G, pos, nx.betweenness_centrality(G), 'Betweenness Centrality')
```

![image-20230221210014859](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302212100970.png)

### 3.5.11 Closeness Centrality

```python
nx.closeness_centrality(G)
>>>
{'莘庄': 0.062451331568291545,
 '外环路': 0.06620439161300974,
 '莲花路': 0.0704126426690079,
 '锦江乐园': 0.07516401124648547,
 '上海南站': 0.08057062487442235,...
```

```python
draw(G, pos, nx.closeness_centrality(G), 'Closeness Centrality')
```

![image-20230221210125131](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302212101237.png)

### 3.5.12 PageRank

```python
nx.pagerank(G)
>>>
{'莘庄': 0.002411931402069049,
 '外环路': 0.0023510599069236924,
 '莲花路': 0.002242849588934548,
 '锦江乐园': 0.002047439221984982,
 '上海南站': 0.004243625463037333,
 '漕宝路': 0.0031132555714021132,
```

```python
draw(G, pos, nx.pagerank(G, alpha=0.85), 'PageRank')
```

![image-20230221210228873](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302212102979.png)

### 3.5.13 Katz Centrality

```python
nx.katz_centrality(G, alpha=0.1, beta=1.0)
>>>
{'莘庄': 0.04628361847743404,
 '外环路': 0.04629979955008696,
 '莲花路': 0.046459980071164066,
 '锦江乐园': 0.04804561840862006,
 '上海南站': 0.06374187049734861,...
```

```python
draw(G, pos, nx.katz_centrality(G, alpha=0.1, beta=1.0), 'Katz Centrality')
```

![image-20230221210406683](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302212104867.png)

### 3.5.14 HIST Hubs and Authorities

```python
h, a = nx.hits(G)
draw(G, pos, h, 'DiGraph HITS Hubs')
draw(G, pos, a, 'DiGraph HITS Authorities')
```

![image-20230221210508491](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302212105671.png)

![image-20230221210513863](https://cdn.jsdelivr.net/gh/Shannon-Lau/DataWhale-CS224W@main/image/202302212105042.png)
