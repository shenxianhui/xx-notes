<!--
 * @Author: shenxh
 * @Date: 2021-12-13 16:49:22
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-15 15:54:27
 * @Description: HTML 表单
-->

- [表单常用标签](#表单常用标签)
  - [`<form>` 标签](#form-标签)
    - [说明](#说明)
    - [实例](#实例)
    - [常用属性](#常用属性)
  - [`<input>` 标签](#input-标签)
    - [说明](#说明-1)
    - [实例](#实例-1)
    - [常用属性](#常用属性-1)
      - [`type` 属性](#type-属性)
  - [`<textarea>` 标签](#textarea-标签)
    - [说明](#说明-2)
    - [实例](#实例-2)
    - [常用属性](#常用属性-2)
  - [`<select>` 和 `<option>` 标签](#select-和-option-标签)
    - [说明](#说明-3)
    - [实例](#实例-3)
    - [常用属性](#常用属性-3)
  - [`<label>` 标签](#label-标签)
    - [说明](#说明-4)
    - [实例](#实例-4)
    - [常用属性](#常用属性-4)
  - [`<button>` 标签](#button-标签)
    - [说明](#说明-5)
    - [常用属性](#常用属性-5)
- [常用表单示例](#常用表单示例)

# 表单常用标签

## `<form>` 标签

### 说明
+ 表单是一个包含表单元素的区域, 使用表单标签 `<form>` 来设置

### 实例
```
<form>
    <!-- 这里输入 input 元素 -->
</form>
```

### 常用属性
|属性名|属性值|描述|
|-|-|-|
|action|URL|规定当提交表单时向何处发送表单数据|
|method|get<br />post|规定用于发送表单数据的 HTTP 方法|
|name|*text*|规定表单的名称|
|novalidate|novalidate|如果使用该属性，则提交表单时不进行验证|
|target|_blank<br />_self<br />_parent<br />_top|规定在何处打开 action URL|

## `<input>` 标签

### 说明
+ `<input>` 标签规定了用户可以在其中输入数据的输入字段
+ `<input>` 元素在 `<form>` 元素中使用，用来声明允许用户输入数据的 input 控件
+ 输入字段可通过多种方式改变，取决于 `type` 属性

### 实例
```
<form>
    用户名<input name="username" type="text" /><br />
    密码<input name="password" type="password" /><br />
    <input type="submit" value="提交" />
</form>
```

### 常用属性
|属性名|属性值|描述|
|-|-|-|
|autofocus|autofocus|属性规定当页面加载时 <input> 元素应该自动获得焦点|
|checked|checked|checked 属性规定在页面加载时应该被预先选定的 <input> 元素。 (只针对 type="checkbox" 或者 type="radio")|
|disabled|disabled|disabled 属性规定应该禁用的 <input> 元素|
|form|*form_id*|form 属性规定 <input> 元素所属的一个或多个表单|
|max|*number*<br />*date*|属性规定 <input> 元素的最大值|
|maxlength|*number*|属性规定 <input> 元素中允许的最大字符数|
|min|*number*<br />*date*|属性规定 <input> 元素的最小值|
|name|*text*|name 属性规定 <input> 元素的名称|
|pattern|*regexp*|pattern 属性规定用于验证 <input> 元素的值的正则表达式|
|placeholder|*text*|placeholder 属性规定可描述输入 <input> 字段预期值的简短的提示信息|
|readonly|readonly|readonly 属性规定输入字段是只读的|
|required|required|属性规定必需在提交表单之前填写输入字段|
|size|*number*|size 属性规定以字符数计的 <input> 元素的可见宽度|
|step|*number*|step 属性规定 <input> 元素的合法数字间隔|
|**type**|button<br />checkbox<br />color<br />date<br />datetime<br />datetime-local<br />email<br />file<br />hidden<br />image<br />month<br />number<br />password<br />radio<br />range<br />reset<br />search<br />submit<br />tel<br />text<br />time<br />url<br />week|type 属性规定要显示的 <input> 元素的类型|
|value|*text*|指定 <input> 元素 value 的值|

#### `type` 属性
|属性值|描述|
|-|-|
|button|定义可点击的按钮（通常与 JavaScript 一起使用来启动脚本）|
|checkbox|	定义复选框|
|color|定义拾色器|
|date|定义 date 控件（包括年、月、日，不包括时间）|
|datetime|定义 date 和 time 控件（包括年、月、日、时、分、秒、几分之一秒，基于 UTC 时区）|
|datetime-local|定义 date 和 time 控件（包括年、月、日、时、分、秒、几分之一秒，不带时区）|
|email|定义用于 e-mail 地址的字段|
|file|定义文件选择字段和 "浏览..." 按钮，供文件上传|
|hidden|定义隐藏输入字段|
|image|定义图像作为提交按钮|
|month|定义 month 和 year 控件（不带时区）|
|number|定义用于输入数字的字段|
|password|定义密码字段（字段中的字符会被遮蔽）|
|radio|定义单选按钮|
|range|定义用于精确值不重要的输入数字的控件（比如 slider 控件）|
|reset|定义重置按钮（重置所有的表单值为默认值）|
|search|定义用于输入搜索字符串的文本字段|
|submit|定义提交按钮|
|tel|定义用于输入电话号码的字段|
|text|默认。定义一个单行的文本字段（默认宽度为 20 个字符）|
|time|定义用于输入时间的控件（不带时区）|
|url|定义用于输入 URL 的字段|
|week|定义 week 和 year 控件（不带时区）|

## `<textarea>` 标签

### 说明
+ `<textarea>` 标签定义一个多行的文本输入控件。
+ 文本区域中可容纳无限数量的文本，其中的文本的默认字体是等宽字体（通常是 Courier）。
+ 可以通过 `cols` 和 `rows` 属性来规定 `textarea` 的尺寸大小，不过更好的办法是使用 CSS 的 `height` 和 `width` 属性

### 实例
```
<textarea rows="3" cols="20">这里可以写默认内容</textarea>
```

### 常用属性
|属性名|属性值|描述|
|-|-|-|
|autofocus|autofocus|规定当页面加载时，文本区域自动获得焦点|
|cols|*number*|规定文本区域内可见的宽度|
|disabled|disabled|规定禁用文本区域|
|form|*form_id*|定义文本区域所属的一个或多个表单|
|maxlength|*number*|规定文本区域允许的最大字符数|
|name|*text*|规定文本区域的名称|
|placeholder|*text*|规定一个简短的提示，描述文本区域期望的输入值|
|readonly|readonly|规定文本区域为只读|
|required|required|规定文本区域是必需的/必填的|
|rows|*number*|规定文本区域内可见的行数|
|wrap|hard<br />soft|规定当提交表单时，文本区域中的文本应该怎样换行|

## `<select>` 和 `<option>` 标签

### 说明
+ `<select>` 元素用来创建下拉列表
+ `<option>` 标签定义下拉列表中的一个选项

### 实例
```
<select>
    <option value="1">选项1</option>
    <option value="2">选项2</option>
    <option value="3">选项3</option>
    <option value="4">选项4</option>
</select>
```

### 常用属性
+ `<select>`

|属性名|属性值|描述|
|-|-|-|
|autofocus|autofocus|规定在页面加载时下拉列表自动获得焦点|
|disabled|disabled|当该属性为 true 时，会禁用下拉列表|
|form|*form_id*|定义 select 字段所属的一个或多个表单|
|multiple|multiple|当该属性为 true 时，可选择多个选项|
|name|*text*|定义下拉列表的名称|
|required|required|规定用户在提交表单前必须选择一个下拉列表中的选项|
|size|*number*|规定下拉列表中可见选项的数目|

+ `option`

|属性名|属性值|描述|
|-|-|-|
|disabled|disabled|规定此选项应在首次加载时被禁用|
|label|*text*|定义当使用 <optgroup> 时所使用的标注|
|selected|selected|规定选项（在首次显示在列表中时）表现为选中状态|
|value|*text*|定义送往服务器的选项值|

## `<label>` 标签

### 说明
+ `<label>` 标签为 `input` 元素定义标注（标记）。
+ `label` 元素不会向用户呈现任何特殊效果。不过，它为鼠标用户改进了可用性。如果您在 `label` 元素内点击文本，就会触发此控件。就是说，当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上。
+ `<label>` 标签的 `for` 属性应当与相关元素的 `id` 属性相同

### 实例
```
<form>
    <label for="username">用户名</label>
    <input id="username" type="text" />
</form>
```

### 常用属性
|属性名|属性值|描述|
|-|-|-|
|for|*element_id*|规定 label 与哪个表单元素绑定|
|form|*form_id*|规定 label 字段所属的一个或多个表单|

## `<button>` 标签

### 说明
+ `<button>` 标签定义一个按钮。
+ 在 `<button>` 元素内部，您可以放置内容，比如文本或图像。这是该元素与使用 `<input>` 元素创建的按钮之间的不同之处
+ 建议始终为 `<button>` 元素规定 `type` 属性。不同的浏览器对 `<button>` 元素的 `type` 属性使用不同的默认值

### 常用属性
|属性名|属性值|描述|
|-|-|-|
|autofocus|autofocus|规定当页面加载时按钮应当自动地获得焦点|
|disabled|disabled|规定应该禁用该按钮|
|form|*form_id*|规定按钮属于一个或多个表单|
|formmethod|get<br />post|规定用于发送表单数据的 HTTP 方法。覆盖 form 元素的 method 属性。该属性与 type="submit" 配合使用|
|formnovalidate|formnovalidate|如果使用该属性，则提交表单时不进行验证。覆盖 form 元素的 novalidate 属性。该属性与 type="submit" 配合使用|
|formtarget|_blank<br />_self<br />_parent<br />_top|规定在何处打开 action URL。覆盖 form 元素的 target 属性。该属性与 type="submit" 配合使用|
|name|*name*|规定按钮的名称|
|type|button<br />reset<br />submit|规定按钮的类型|
|value|*text*|规定按钮的初始值。可由脚本进行修改|

# 常用表单示例
```
<form
    action="https://www.shenxh0928.cn:3031/user/login"
    method="post"
    target="_blank"
>
    <div class="item">
        <label for="username">用户名</label>
        <input
            id="username"
            name="username"
            type="text"
            required
            autofocus
            placeholder="请输入用户名"
        />
    </div>
    <div class="item">
        <label for="password">密码</label>
        <input
            id="password"
            name="password"
            type="password"
            required
            placeholder="请输入密码"
        />
    </div>
    <div class="item">
        <label for="phone">手机号</label>
        <input
            id="phone"
            name="phone"
            type="tel"
            maxlength="11"
            placeholder="请输入手机号"
        />
    </div>
    <div class="item">
        <label for="email">邮箱</label>
        <input
            id="email"
            name="email"
            type="email"
            placeholder="请输入邮箱"
        />
    </div>
    <div class="item">
        <label for="age">年龄</label>
        <input
            id="age"
            name="age"
            type="number"
            min="18"
            max="60"
            placeholder="请输入年龄"
        />
    </div>
    <div class="item">
        <label for="address">地址</label>
        <select>
            <option value="liaocheng">聊城</option>
            <option value="shanghai">上海</option>
            <option value="hangzhou">杭州</option>
            <option value="qingdao">青岛</option>
            <option value="jinan">济南</option>
        </select>
    </div>
    <div class="item">
        <label for="sex">性别</label>
        <input name="sex" type="radio" value="1" />男
        <input name="sex" type="radio" value="2" />女
    </div>
    <div class="item">
        <label for="birthday">生日</label>
        <input
            name="birthday"
            type="date"
            min="1990-01-01"
            max="2000-12-31"
        />
    </div>
    <div class="item">
        <label for="interest">兴趣</label>
        <input name="interest" type="checkbox" value="1" />电影
        <input name="interest" type="checkbox" value="2" />旅行
        <input name="interest" type="checkbox" value="3" />游戏
        <input name="interest" type="checkbox" value="4" checked />睡觉
    </div>
    <div class="item">
        <label for="color">幸运色</label>
        <input id="color" name="color" type="color" />
    </div>
    <div class="item">
        <label for="file">浏览</label>
        <input id="file" name="file" type="file" />
    </div>
    <div class="item">
        <label for="remark">备注</label>
        <textarea
            id="remark"
            name="remark"
            rows="3"
            cols="22"
        ></textarea>
    </div>

    <div class="item">
        <input type="submit" value="提交" />
        <input type="reset" value="重置" />
    </div>
</form>
```
