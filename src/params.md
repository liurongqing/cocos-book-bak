# 场景传参


节点脚本

```ts
import { _decorator, Component, Node, director } from "cc";
const { ccclass, property } = _decorator;

@ccclass("RootNodeController")
export class RootNodeController extends Component {
  start() {
    const node = this.node;
    director.addPersistRootNode(node);

    node.attr({ data: 123 });
  }

  update(deltaTime: number) {}
}

```

写数据

```ts
const rootNode: any = director.getScene().getChildByName("RootNode");
rootNode.attr({ data: { msg: "我是从home过来的", key: "home" } });
```

获取数据及清空

```ts
const rootNode: any = director.getScene().getChildByName("RootNode");
const data = rootNode?.data;
if (data) {
  console.log(data);
  // 清空
  rootNode.attr({ data: null });
}
```