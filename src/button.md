# 点击按钮


```ts
const startBtn = this.node.getChildByName("Start");
const button = startBtn.addComponent(Button);
button.transition = Button.Transition.SCALE;

button.node.on(Node.EventType.TOUCH_START, (event) => {
    console.log("点击了开始游戏");
});
```