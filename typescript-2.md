## 如果想切换到安卓模拟器每次打开需要遵循一下步骤：

把这个输入进terminal：

export ANDROID_HOME=/Users/zhenyingyu/Library/Android/sdk

再输入：npm run android

## _layout.tsx代码解析：

```typescript
import { Tabs } from "expo-router"; // 从expo-router包中导入Tabs组件
import { Text, View } from "react-native"; // 从react-native中导入Text和View组件
import FontAwesome from "@expo/vector-icons/FontAwesome"; // 从@expo/vector-icons包中导入FontAwesome图标库

export default function Layout() { // 导出默认的函数组件Layout
  return (
    <Tabs> // 使用Tabs组件来创建一个标签导航
      <Tabs.Screen
        name="video/[id]" // 创建一个标签页，其路由名称为“video/[id]”
        options={{
          href: null, // 该标签页没有设置href，可能意味着它不指向一个具体的URL
        }}
      />
      <Tabs.Screen
        name="index" // 创建一个名为“index”的标签页
        options={{
          title: "HOME", // 设置标签页标题为“HOME”
          tabBarLabel: ({ focused }) => ( // 设置标签栏文字，根据是否聚焦改变颜色
            <Text style={{ color: focused ? "#231F20" : "#999693" }}>home</Text>
          ),
          tabBarIcon: ({ focused }) => ( // 设置标签栏图标，根据是否聚焦改变颜色
            <FontAwesome
              name="home"
              size={20}
              color={focused ? "#231F20" : "#999693"}
            />
          ),
        }}
      />
      <Tabs.Screen
        name="createContent" // 创建一个名为“createContent”的标签页
        options={{
          title: "create", // 设置标签页标题为“create”
          tabBarButton: (props) => ( // 自定义标签按钮
            <View style={{ justifyContent: "center" }}> // 按钮居中显示
              <FontAwesome.Button
                onPress={props.onPress} // 点击事件处理
                onBlur={props.onBlur} // 失焦事件处理
                size={20} // 图标大小
                name="plus" // 图标为加号
                style={{
                  paddingRight: 0, // 右内边距为0
                  backgroundColor: "#ff5722", // 背景颜色
                  width: 45, // 宽度
                  flexDirection: "column", // 排列方向为列
                }}
              />
            </View>
          ),
        }}
      />
      <Tabs.Screen
        name="userProfile" // 创建一个名为“userProfile”的标签页
        options={{
          title: "userProfile", // 设置标签页标题为“userProfile”
          tabBarLabel: ({ focused }) => ( // 设置标签栏文字，根据是否聚焦改变颜色
            <Text style={{ color: focused ? "#231F20" : "#999693" }}>me</Text>
          ),
          tabBarIcon: ({ focused }) => ( // 设置标签栏图标，根据是否聚焦改变颜色
            <FontAwesome
              name="user"
              size={20}
              color={focused ? "#231F20" : "#999693"}
            />
          ),
        }}
      />
    </Tabs> // 结束Tabs组件
  );
}

```
