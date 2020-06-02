简单题
1. 
优点：发现垃圾时立即回收
         最大限度减少程序暂停
缺点：无法回收循环引用的对象
          时间开销大

2.
标记整理可以看作时标记清除的增强
标记阶段的操作和清除一致
清除阶段会先执行整理，移动对象位置

3.
回收过程采用复制算法+标记整理
新生代内存区分为两个等大小空间
使用空间为From，空闲空间为To
活动对象储存From空间
标记整理后将活对象拷贝值To
From与To交换换成空间释放

4.
将GC中的对象安装各自的情况分为三种，白色（还未搜索过）  灰色（正在搜索） 黑色（搜索完成）
GC运行前所有的对象都是白色，灰色对象依次从栈中取出，其子对象也会被涂成灰色，当所有的子对象变成灰色时，该对象就会被涂成黑色，当GC运行结束，所有的活动对象全部变成黑色，垃圾则为白色
a，根查找阶段  b 标记阶段  c 清除阶段

代码题1
const fp = require('lodash/fp')
01：const f = fp.flowRight(fp.prop('in_stock'), fp.last)
02：const f = fp.flowRight(fp.prop('name'), fp.first)
04:  const f = fp.flowRight(fp.join('_'), fp.map(fp.toLower), fp.split('_'), _underscore())

代码题2
01 let ex1 = maybe.of(n).map(x => fp.map(x,2) )
04 let ex4 = Maybe.of(n).map(x => parseInt(x) )