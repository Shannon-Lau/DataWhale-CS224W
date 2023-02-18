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

### 1.5.5 节点之间连接

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
# 设置每个节点可视化时的坐标
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
# 可视化时每一列包含的节点
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

# 3. 图数据挖掘

