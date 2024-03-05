# 公共约定

为保持各模块的纯洁性和通讯协议等的独立性，此仓库将保存光纤装配项目各模块的公共约定。

## 通讯约定

在这里约定通讯的方式与内容

### 通讯协议

目前使用的是默认的串口通信（8N1，无奇偶校验）

### 通讯内容

通讯的内容是一个文本形式的 Serialized JSON 数据包，即一串字符串，下面是各字段名称和它们的数据类型：

名称 | 类型 | 描述
--- | --- | ---
Mode | enum | 可能的值为：0: STOP, 1: RUN, 2: RUN_SPEED, 3: STATUS (获取状态)
Speed | float？ | 速度
MaxSpeed | float？ | 最大速度
Acceleration | float？ | 加速度
Target | float？ | 目标位置
Position | float？ | 电机当前位置，一般由下位机返回

> `?` 表示可能为 null
 
> 注意：各字段是首字母大写的形式

### 示例

```json
{"Mode":1,"Speed":null,"MaxSpeed:5.0","Acceleration":1.0,"Target":20,"Position":null}
```
