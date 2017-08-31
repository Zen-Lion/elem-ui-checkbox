# elem-ui-checkbox
vue 结合 elem组件中的checkbox 循环嵌套 实现全选和 单选

elem-ui 组件内 checkbox
  当v-for 嵌套 v-for 时 要想在二级拿到一级的index 直接定义不同的index就行
  当遍历时想给每一个元素定义唯一的id 可以动态设置 :ref = "xx.name"
  使用 ES6 提供的新的数据结构set，它类似与数组，但其值唯一没有重复，它本身是一个构造函数用来生成set数据结构 new Set()
  参数可以是数组或者类数组
  -Set 实列 的操作方法：
       - 可通过add 向Set结构中加入成员
            const s = new Set();
            [2, 3, 5, 4, 5, 2, 2].forEach(x => s.add(x));
            for (let i of s) {
              console.log(i);
            }
            // 2 3 5 4
       - delete(val)  删除某个值，返回一个布尔值，表示删除是否成功
       - has(val)  返回一个布尔值，表示该值是否为Set成员，上面例子中有用到
       - clear()   清除所有成员，没有返回值
       - Array.from 方法可以将Set结构转为数组
         例：给数组去重
            function dedupe(array){
              return Array.from(new Set(array))
            }
            dedupe([1,1,2,3]) // [1,2,3]
   -Set 实列的遍历方法 【Set结构键名和键值是同一个值】
       - keys() 返回键名的遍历器
       - values() 返回键值的遍历器
       - entries() 返回键值对的遍历器
       - forEach() 使用回调函数遍历每个成员
   - for ... of
     forEach 遍历数组时缺陷是不能使用break、return 语句
     for ... in 缺陷是遍历索引值是string而非number，某些情况下遍历数组元素顺序是任意的
     for ... of 循环遍历数据如数组中的单值并解决上面两个的缺陷问题
  - 扩展运算符（...）
  - Set 结构很容易实现并集、交集、差集
        let a = new Set([1, 2, 3]);
        let b = new Set([4, 3, 2]);
        // 并集
        let union = new Set([...a, ...b]);
        // Set {1, 2, 3, 4}
        // 交集
        let intersect = new Set([...a].filter(x => b.has(x)));
        // set {2, 3}
        // 差集
        let difference = new Set([...a].filter(x => !b.has(x)));
        // Set {1}
