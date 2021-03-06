<!--
 * @Description: 操作符
 * @Author: shenxh
 * @Date: 2021-12-22 16:21:39
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-27 16:15:27
-->

- [一元操作符](#一元操作符)
  - [递增/递减操作符](#递增递减操作符)
  - [一元加和减](#一元加和减)
- [布尔操作符](#布尔操作符)
  - [逻辑非](#逻辑非)
  - [逻辑与](#逻辑与)
  - [逻辑或](#逻辑或)
- [乘性操作符](#乘性操作符)
  - [乘法操作符](#乘法操作符)
  - [除法操作符](#除法操作符)
  - [取模操作符](#取模操作符)
- [指数操作符](#指数操作符)
- [加性操作符](#加性操作符)
  - [加法操作符](#加法操作符)
  - [减法操作符](#减法操作符)
- [关系操作符](#关系操作符)
- [相等操作符](#相等操作符)
  - [等于和不等于](#等于和不等于)
  - [全等和不全等](#全等和不全等)
- [条件操作符](#条件操作符)
- [赋值操作符](#赋值操作符)
- [逗号操作符](#逗号操作符)

# 一元操作符
只操作一个值的操作符叫一元操作符（unary operator）。一元操作符是 ECMAScript 中最简单的操作符。

##  递增/递减操作符
递增和递减操作符有两个版本：前缀版和后缀版。顾名思义，前缀版就是位于要操作的变量前头，后缀版就是位于要操作的变量后头。

前缀递增操作符会给数值加 1，把两个加号（`++`）放到变量前头即可：

```
let age = 18;

// 相当于 age = age + 1;
++age; // 19
```

前缀递减操作符也类似，只不过是从一个数值减 1。使用前缀递减操作符，只要把两个减号（`--`）放到变量前头即可：

```
let age = 18;

// 相当于 age = age - 1;
--age; // 17
```

无论使用前缀递增还是前缀递减操作符，变量的值都会在语句被求值**之前**改变。（在计算机科学中，这通常被称为具有副作用。）请看下面的例子：

```
let age = 29;
let anotherAge = --age + 2;

console.log(age); // 28
console.log(anotherAge); // 30
```

在这个例子中，变量 anotherAge 以 age 减 1 后的值再加 2 进行初始化。因为递减操作先发生，所以 age 的值先变成 28，然后再加 2，结果是 30。

递增和递减的后缀版语法一样（分别是 `++` 和 `--`），只不过要放在变量后面。后缀版与前缀版的主要区别在于，后缀版递增和递减在语句被求值后才发生。在某些情况下，这种差异没什么影响，比如：

```
let age = 18;

// 相当于 age = age + 1;
age++; // 19
```

把递增操作符放到变量后面不会改变语句执行的结果，因为上面例子中递增是唯一的操作。可是，在跟其他操作混合时，差异就会变明显，比如：

```
let age = 29;
let anotherAge = age-- + 2;

console.log(age); // 28
console.log(anotherAge); // 31
```

## 一元加和减
一元加和减操作符对大多数开发者来说并不陌生，它们在 ECMAScript 中跟在高中数学中的用途一样。一元加由一个加号（`+`）表示，放在变量前头，对数值没有任何影响：

```
let num = 25;

num = +num;
console.log(num); // 25
```

如果将一元加应用到非数值，则会执行与使用 `Number()` 转型函数一样的类型转换：布尔值 `false` 和 `true` 转换为 0 和 1，字符串根据特殊规则进行解析，对象会调用它们的 `valueOf()` 和/或 `toString()` 方法以得到可以转换的值。

下面的例子演示了一元加在应用到不同数据类型时的行为：

```
let s1 = "01";
let s2 = "1.1";
let s3 = "z";
let b = false;
let f = 1.1;
let o = {
  valueOf() {
    return -1;
  }
};

s1 = +s1; // 值变成数值 1
s2 = +s2; // 值变成数值 1.1
s3 = +s3; // 值变成 NaN
b = +b; // 值变成数值 0
f = +f; // 不变，还是 1.1
o = +o; // 值变成数值-1
```

一元减由一个减号（`-`）表示，放在变量前头，主要用于把数值变成负值，如把 1 转换为 -1。示例如下：

```
let num = 25;

num = -num;
console.log(num); // -25
```

对数值使用一元减会将其变成相应的负值（如上面的例子所示）。在应用到非数值时，一元减会遵循与一元加同样的规则，先对它们进行转换，然后再取负值：

```
let s1 = "01";
let s2 = "1.1";
let s3 = "z";
let b = false;
let f = 1.1;
let o = {
  valueOf() {
    return -1;
  }
};

s1 = -s1; // 值变成数值-1
s2 = -s2; // 值变成数值-1.1
s3 = -s3; // 值变成 NaN
b = -b; // 值变成数值 0
f = -f; // 变成-1.1
o = -o; // 值变成数值 1
```

> 注: 一元加和减操作符主要用于基本的算术，但也可以像上面的例子那样，用于数据类型转换。

# 布尔操作符
对于编程语言来说，布尔操作符跟相等操作符几乎同样重要。如果没有能力测试两个值的关系，那么像 if-else 和循环这样的语句也没什么用了。布尔操作符一共有 3 个：逻辑非、逻辑与和逻辑或。

## 逻辑非
逻辑非操作符由一个叹号（`!`）表示，可应用给 ECMAScript 中的任何值。这个操作符始终返回布尔值，无论应用到的是什么数据类型。逻辑非操作符首先将操作数转换为布尔值，然后再对其取反。换句话说，逻辑非操作符会遵循如下规则。
+ 如果操作数是对象，则返回 false
+ 如果操作数是空字符串，则返回 true
+ 如果操作数是非空字符串，则返回 false
+ 如果操作数是数值 0，则返回 true
+ 如果操作数是非 0 数值（包括 Infinity），则返回 false
+ 如果操作数是 null，则返回 true
+ 如果操作数是 NaN，则返回 true
+ 如果操作数是 undefined，则返回 true

以下示例验证了上述行为：

```
console.log(!false); // true
console.log(!"blue"); // false
console.log(!0); // true
console.log(!NaN); // true
console.log(!""); // true
console.log(!12345); // false 
```

逻辑非操作符也可以用于把任意值转换为布尔值。同时使用两个叹号（`!!`），相当于调用了转型函数 `Boolean()`。无论操作数是什么类型，第一个叹号总会返回布尔值。第二个叹号对该布尔值取反，从而给出变量真正对应的布尔值。结果与对同一个值使用 `Boolean()` 函数是一样的：

```
console.log(!!"blue"); // true
console.log(!!0); // false
console.log(!!NaN); // false
console.log(!!""); // false
console.log(!!12345); // true
```

## 逻辑与
逻辑与操作符由两个和号（`&&`）表示，应用到两个值，如下所示：

```
let result = true && false;
```

逻辑与操作符遵循如下真值表：

|第一个操作数|第二个操作数|结果|
|-|-|-|
|true|true|true|
|true|false|false|
|false|true|false|
|false|false|false|

逻辑与操作符是一种短路操作符，意思就是如果第一个操作数决定了结果，那么永远不会对第二个操作数求值。对逻辑与操作符来说，如果第一个操作数是 false，那么无论第二个操作数是什么值，结果也不可能等于 true。

##  逻辑或
逻辑或操作符由两个管道符（`||`）表示，比如：

```
let result = true || false;
```

逻辑或操作符遵循如下真值表：

|第一个操作数|第二个操作数|结果|
|-|-|-|
|true|true|true|
|true|false|true|
|false|true|true|
|false|false|false|

同样与逻辑与类似，逻辑或操作符也具有短路的特性。只不过对逻辑或而言，第一个操作数求值为 true，第二个操作数就不会再被求值了。

# 乘性操作符
ECMAScript 定义了 3 个乘性操作符：乘法、除法和取模。

在处理非数值时，它们也会包含一些自动的类型转换。如果乘性操作符有不是数值的操作数，则该操作数会在后台被使用 `Number()` 转型函数转换为数值。这意味着空字符串会被当成 0，而布尔值 true 会被当成 1。

## 乘法操作符
乘法操作符由一个星号（`*`）表示，可以用于计算两个数值的乘积。比如：

```
let result = 3 * 5; // 15
```

不过，乘法操作符在处理特殊值时也有一些特殊的行为。
+ 如果操作数都是数值，则执行常规的乘法运算，即两个正值相乘是正值，两个负值相乘也是正值，正负符号不同的值相乘得到负值
+ 如果有任一操作数是 NaN，则返回 NaN
+ 如果有不是数值的操作数，则先在后台用 `Number()` 将其转换为数值，然后再应用上述规则

## 除法操作符
除法操作符由一个斜杠（`/`）表示，用于计算第一个操作数除以第二个操作数的商，比如：

```
let result = 66 / 11; // 6
```

跟乘法操作符一样，除法操作符针对特殊值也有一些特殊的行为。
+ 如果操作数都是数值，则执行常规的除法运算，即两个正值相除是正值，两个负值相除也是正值，符号不同的值相除得到负值
+ 如果有任一操作数是 NaN，则返回 NaN
+ 如果是 0 除以 0，则返回 NaN
+ 如果有不是数值的操作数，则先在后台用 `Number()` 函数将其转换为数值，然后再应用上述规则

## 取模操作符
取模（余数）操作符由一个百分比符号（`%`）表示，比如：

```
let result = 26 % 5; // 1 (余数为 1)
```

与其他乘性操作符一样，取模操作符对特殊值也有一些特殊的行为。
+ 如果操作数是数值，则执行常规除法运算，返回余数
+ 如果被除数是无限值，除数是有限值，则返回 NaN
+ 如果被除数是有限值，除数是 0，则返回 NaN
+ 如果是无限值除以无限值，则返回 NaN
+ 如果被除数是有限值，除数是无限值，则返回被除数
+ 如果被除数是 0，除数不是 0，则返回 0
+ 如果有不是数值的操作数，则先在后台用 `Number()` 函数将其转换为数值，然后再应用上述规则

# 指数操作符
ES7 新增了指数操作符, 用两个星号 (`**`) 表示：

```
let result1 = 3 ** 2; // 9 (3 的平方)
let result2 = 16 ** 0.5; // 4 (根号 16)
```

不仅如此，指数操作符也有自己的指数赋值操作符 `**=` ，该操作符执行指数运算和结果的赋值操作：

```
let squared = 3;

squared **= 2;
console.log(squared); // 9
```

# 加性操作符
加性操作符，即加法和减法操作符，一般都是编程语言中最简单的操作符。不过，在 ECMAScript 中，这两个操作符拥有一些特殊的行为。与乘性操作符类似，加性操作符在后台会发生不同数据类型的转换。只不过对这两个操作符来说，转换规则不是那么直观。

## 加法操作符
加法操作符（`+`）用于求两个数的和，比如：

```
let result = 1 + 2; 
```

如果两个操作数都是数值，加法操作符执行加法运算并根据如下规则返回结果：
+ 如果有任一操作数是 NaN，则返回 NaN
+ 如果是 `+0` 加 `+0`，则返回 `+0`
+ 如果是 `-0` 加 `+0`，则返回 `+0`
+ 如果是 `-0` 加 `-0`，则返回 `-0`

不过，如果有一个操作数是字符串，则要应用如下规则：
+ 如果两个操作数都是字符串，则将第二个字符串拼接到第一个字符串后面
+ 如果只有一个操作数是字符串，则将另一个操作数转换为字符串，再将两个字符串拼接在一起

如果有任一操作数是对象、数值或布尔值，则调用它们的 `toString()` 方法以获取字符串，然后再应用前面的关于字符串的规则。对于 `undefined` 和 `null`，则调用 `String()` 函数，分别获取"undefined"和"null"。

看下面的例子：

```
let result1 = 5 + 5; // 两个数值
let result2 = 5 + "5"; // 一个数值和一个字符串

console.log(result1); // 10
console.log(result2); // "55"
```

## 减法操作符
减法操作符（`-`）也是使用很频繁的一种操作符，比如：

```
let result = 2 - 1;
```

与加法操作符一样，减法操作符也有一组规则用于处理 ECMAScript 中不同类型之间的转换。
+ 如果两个操作数都是数值，则执行数学减法运算并返回结果
+ 如果有任一操作数是 NaN，则返回 NaN
+ 如果是 `+0` 减 `+0`，则返回 `+0`
+ 如果是 `+0` 减 `-0`，则返回 `-0`
+ 如果是 `-0` 减 `-0`，则返回 `+0`
+ 如果有任一操作数是字符串、布尔值、null 或 undefined，则先在后台使用 `Number()` 将其转换为数值，然后再根据前面的规则执行数学运算。如果转换结果是 NaN，则减法计算的结果是 NaN
+ 如果有任一操作数是对象，则调用其 `valueOf()` 方法取得表示它的数值。如果该值是 NaN，则减法计算的结果是 NaN。如果对象没有 `valueOf()` 方法，则调用其 `toString()` 方法，然后再将得到的字符串转换为数值

以下示例演示了上面的规则：

```
let result1 = 5 - true; // true 被转换为 1，所以结果是 4
let result2 = NaN - 1; // NaN
let result3 = 5 - 3; // 2
let result4 = 5 - ""; // ""被转换为 0，所以结果是 5
let result5 = 5 - "2"; // "2"被转换为 2，所以结果是 3
let result6 = 5 - null; // null 被转换为 0，所以结果是 5
```

# 关系操作符
关系操作符执行比较两个值的操作，包括小于（`<`）、大于（`>`）、小于等于（`<=`）和大于等于（`>=`），用法跟数学课上学的一样。这几个操作符都返回布尔值，如下所示：

```
let result1 = 5 > 3; // true
let result2 = 5 < 3; // false 
```

与 ECMAScript 中的其他操作符一样，在将它们应用到不同数据类型时也会发生类型转换和其他行为。
+ 如果操作数都是数值，则执行数值比较。
+ 如果操作数都是字符串，则逐个比较字符串中对应字符的编码。
+ 如果有任一操作数是数值，则将另一个操作数转换为数值，执行数值比较。
+ 如果有任一操作数是对象，则调用其 `valueOf()` 方法，取得结果后再根据前面的规则执行比较。如果没有 `valueOf()` 操作符，则调用 toString()方法，取得结果后再根据前面的规则执行比较。
+ 如果有任一操作数是布尔值，则将其转换为数值再执行比较。

是在比较两个数值字符串的时候，比如下面这个例子：

```
let result = "23" < "3"; // true 
```

这里在比较字符串"23"和"3"时返回 true。因为两个操作数都是字符串，所以会逐个比较它们的字符编码（字符"2"的编码是 50，而字符"3"的编码是 51）。不过，如果有一个操作数是数值，那么比较的结果就对了：

```
let result = "23" < 3; // false
```

因为这次会将字符串"23"转换为数值 23，然后再跟 3 比较，结果当然对了。只要是数值和字符串比较，字符串就会先被转换为数值，然后进行数值比较。对于数值字符串而言，这样能保证结果正确。

# 相等操作符
判断两个变量是否相等是编程中最重要的操作之一。在比较字符串、数值和布尔值是否相等时，过程都很直观。但是在比较两个对象是否相等时，情形就比较复杂了。

ECMAScript 中的相等和不相等操作符，原本在比较之前会执行类型转换，但很快就有人质疑这种转换是否应该发生。

最终，JavaScript 提供了两组操作符。第一组是等于和不等于，它们在比较之前执行转换。第二组是全等和不全等，它们在比较之前不执行转换。

## 等于和不等于
ECMAScript 中的等于操作符用两个等于号（`==`）表示，如果操作数相等，则会返回 `true`。不等于操作符用叹号和等于号（`!=`）表示，如果两个操作数不相等，则会返回 `true`。

这两个操作符都会先进行类型转换（通常称为强制类型转换）再确定操作数是否相等。

在转换操作数的类型时，相等和不相等操作符遵循如下规则。
+ 如果任一操作数是布尔值，则将其转换为数值再比较是否相等。`false` 转换为 0，`true` 转换为 1
+ 如果一个操作数是字符串，另一个操作数是数值，则尝试将字符串转换为数值，再比较是否相等
+ 如果一个操作数是对象，另一个操作数不是，则调用对象的 `valueOf()` 方法取得其原始值，再根据前面的规则进行比较。

在进行比较时，这两个操作符会遵循如下规则。
+ `null` 和 `undefined` 相等
+ `null` 和 `undefined` 不能转换为其他类型的值再进行比较
+ 如果有任一操作数是 NaN，则相等操作符返回 `false`，不相等操作符返回 `true`。记住：即使两个操作数都是 NaN，相等操作符也返回 `false`，因为按照规则，NaN 不等于 NaN
+ 如果两个操作数都是对象，则比较它们是不是同一个对象。如果两个操作数都指向同一个对象，则相等操作符返回 `true`。否则，两者不相等

下表总结了一些特殊情况及比较的结果。
|表达式|结果|
|-|-|
|null == undefined|true|
|"NaN" == NaN|false|
|5 == NaN|false|
|NaN == NaN|false|
|NaN != NaN|true|
|false == 0|true|
|true == 1|true|
|true == 2|false|
|undefined == 0|false|
|null == 0|false|
|"5" == 5|true|

> 注: NaN 和任何值都不相等, 包括它自己

## 全等和不全等
全等和不全等操作符与相等和不相等操作符类似，只不过它们在比较相等时不转换操作数。全等操作符由 3 个等于号（`===`）表示，只有两个操作数在不转换的前提下相等才返回 `true`，比如：

```
let result1 = ("55" == 55); // true，转换后相等
let result2 = ("55" === 55); // false，不相等，因为数据类型不同
```

在这个例子中，第一个比较使用相等操作符，比较的是字符串"55"和数值 55。如前所述，因为字符串"55"会被转换为数值 55，然后再与数值 55 进行比较，所以返回 `true`。第二个比较使用全等操作符，因为没有转换，字符串和数值当然不能相等，所以返回 `false`。

不全等操作符用一个叹号和两个等于号（`!==`）表示，只有两个操作数在不转换的前提下不相等才返回 `true`。比如：

```
let result1 = ("55" != 55); // false，转换后相等
let result2 = ("55" !== 55); // true，不相等，因为数据类型不同
```

这一次，第一个比较使用不相等操作符，它会把字符串"55"转换为数值 55，跟第二个操作数相等。既然转换后两个值相等，那就返回 `false`。第二个比较使用不全等操作符。这时候可以这么问：“字符串 55 和数值 55 有区别吗？”答案是“有”（`true`）。

另外，虽然 `null == undefined` 是 `true`（因为这两个值类似），但 `null === undefined` 是 `false`，因为它们不是相同的数据类型。

> 注: 由于相等和不相等操作符存在类型转换问题，因此推荐使用全等和不全等操作符。这样有助于在代码中保持数据类型的完整性。

# 条件操作符
条件操作符是 ECMAScript 中用途最为广泛的操作符之一, 我们一般称之为"三元表达式":

```
let variable = boolean_expression ? true_value : false_value;
```

上面的代码执行了条件赋值操作，即根据条件表达式 boolean_expression 的值决定将哪个值赋给变量 variable 。如果 boolean_expression 是 true ，则赋值 true_value ；如果 boolean_expression 是 false，则赋值 false_value。比如：

```
let max = (num1 > num2) ? num1 : num2;
```

在这个例子中，max 将被赋予一个最大值。这个表达式的意思是，如果 num1 大于 num2（条件表达式为 `true`），则将 num1 赋给 max。否则，将 num2 赋给 max。

# 赋值操作符
简单赋值用等于号（`=`）表示，将右手边的值赋给左手边的变量，如下所示：

```
let num = 10;
```

复合赋值使用乘性、加性或位操作符后跟等于号（`=`）表示。这些赋值操作符是类似如下常见赋值操作的简写形式：

```
let num = 10;

num = num + 10;
```

以上代码的第二行可以通过复合赋值来完成：

```
let num = 10;

num += 10;
```

每个数学操作符以及其他一些操作符都有对应的复合赋值操作符：
+ 乘后赋值（`*=`）
+ 除后赋值（`/=`）
+ 取模后赋值（`%=`）
+ 加后赋值（`+=`）
+ 减后赋值（`-=`）
+ 左移后赋值（`<<=`）
+ 右移后赋值（`>>=`）
+ 无符号右移后赋值（`>>>=`）

这些操作符仅仅是简写语法，使用它们不会提升性能。

# 逗号操作符
逗号操作符可以用来在一条语句中执行多个操作。

在一条语句中同时声明多个变量是逗号操作符最常用的场景，如下所示：

```
let num1 = 1, num2 = 2, num3 = 3;
```
