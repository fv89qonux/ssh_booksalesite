## 本项目实现的最终作用是基于SSH实现一个图书销售商场项目网站
## 分为2个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 图书管理
 - 添加图书
 - 添加类目
 - 添加顾客
 - 用户管理
 - 管理员登录
 - 类目列表管理
 - 订单管理
 - 顾客管理
### 第2个角色为用户角色，实现了如下功能：
 - 加入购物车
 - 提交订单
 - 查看书店首页
 - 查看图书详情
 - 查看我的订单
 - 用户注册
 - 用户登录
## 数据库设计如下：
# 数据库设计文档

**数据库名：** ssh_booksalesite

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [admin](#admin) | 管理员表 |
| [book](#book) | 图书信息表 |
| [category](#category) | 分类表 |
| [indent](#indent) |  |
| [items](#items) |  |
| [users](#users) |  |

**表名：** <a id="admin">admin</a>

**说明：** 管理员表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | username |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 用户名  |
|  3   | password |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 密码  |

**表名：** <a id="book">book</a>

**说明：** 图书信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名称  |
|  3   | cover |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 封面  |
|  4   | price |   float   | 13 |   0    |    Y     |  N   |   NULL    | 价格  |
|  5   | intro |   varchar   | 1024 |   0    |    Y     |  N   |   NULL    | 介绍  |
|  6   | auther |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 作者  |
|  7   | press |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 出版社  |
|  8   | pubdate |   date   | 10 |   0    |    Y     |  N   |   NULL    | 出版日期  |
|  9   | special |   int   | 10 |   0    |    Y     |  N   |   0    | 特卖  |
|  10   | news |   int   | 10 |   0    |    Y     |  N   |   0    | 新书  |
|  11   | sale |   int   | 10 |   0    |    Y     |  N   |   0    | 打折  |
|  12   | category_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 分类  |

**表名：** <a id="category">category</a>

**说明：** 分类表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |

**表名：** <a id="indent">indent</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | total |   float   | 13 |   0    |    Y     |  N   |   NULL    | 总价  |
|  3   | amount |   int   | 10 |   0    |    Y     |  N   |   NULL    | 商品总数  |
|  4   | status |   tinyint   | 4 |   0    |    Y     |  N   |   1    | 状态(1未处理/2已处理)  |
|  5   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 收货人姓名  |
|  6   | phone |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 收货人电话  |
|  7   | address |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 收货地址  |
|  8   | systime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 下单时间  |
|  9   | user_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 下单用户  |

**表名：** <a id="items">items</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | price |   float   | 13 |   0    |    Y     |  N   |   NULL    | 购买时价格  |
|  3   | amount |   int   | 10 |   0    |    Y     |  N   |   NULL    | 数量  |
|  4   | book_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 图书ID  |
|  5   | indent_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="users">users</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | username |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 用户名  |
|  3   | password |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 密码  |
|  4   | phone |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 电话  |

