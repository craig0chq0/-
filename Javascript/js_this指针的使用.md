### 代码示例

```ts
class classOne {

    constructor() { }

    public name = "李俊杰"

    public writeName() {
        console.log(`我的名字叫${this.name}`);
    }

    public writeOtherName(cb: () => void) {
        cb();
    }
}

class classTwo {

    constructor() { }

    public name = "陈皓奇"

    public writeName() {
        console.log(`我的名字叫${this.name}`);
    }

    // 这里的 function 的 指针 为 undefined
    public askOther0(obj: classOne) {
        obj.writeOtherName(function(){
            console.log(this);
        });
    }

    // 箭头函数的 this 指针 绑定 生成这个函数 所在的对象
    // 即 classTwo
    public askOther1(obj: classOne) {
        obj.writeOtherName(()=>{
            console.log(`我的名字叫${this.name}`);
        });
    }
}

let one = new classOne();
// 李俊杰
one.writeName();
let two = new classTwo();
// 陈皓奇
two.writeName();
// 李俊杰
// two.askOther0(one);
// 陈皓奇
two.askOther1(one);
```