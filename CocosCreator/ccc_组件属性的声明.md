### 代码示例

```ts
    //节点
    @property(cc.Node)
    icon: cc.Node = null;
    // 浮点型数字
    @property
    Speed: number = 3
    // 枚举
    private state: State = State.right
    private maxX: number = 0
    private maxY: number = 0
    // 整数
    @property({
        type: cc.Integer,
        // 是否在编辑器中隐藏
        visible: true,
        // 是否在编辑器中改名
        displayName: "sdd",
        // 编辑器的提示文字
        tooltip: "asd",
        // 是否是只读
        readonly: false,
        // 
        slide: true,
        // 设置 最小值 最大值 步长
        range: [1, 5, 1],

    })
    myInteger = 1
    // 字符床、串
    @property({ multiline: true })
    myText = ""
    // 向量
    @property
    myOffset = new cc.Vec2(100.100)
    // 节点数组
    @property([cc.Node])
    public myNode: cc.Node[] = []
    // 颜色数组
    @property([cc.Color])
    private myColor: cc.Color[] = []

    _width = 10
    // get set 寄存器
    @property
    get width() {
        return this._width
    }

    set width(value) {
        cc.log("LJJ just a SB");
        this._width = value;
    }
````