# jQuery

- 是一个js的类库，简化了DOM操作，动画操作，兼容性，数据请求操作

## 选择器
     $ -> jquery对象
     $() -> fn() 函数调用   获取的是jquery对象，因为是jquery对象就可以使用jquery的内置方法

```javascript
     $('#box') 获取ID
     $('li') 获取所有li元素
     $('.active') 获取
     $('input[type="button"]') 属性选择器
     even偶数，但是js从0开始计数（所以它看上去是生活中的奇数）
     $('#ul li:even') 偶数，js从0开始
     $('#ul li:odd') 奇数，js从0开始
     $(':button') 伪类选择器
```

```
     $('')
```

### 属性操作
- attr getAttribute，setAttribute
- removeAttr  -> removeAttribute
- prop -> 表单的状态布尔值（表单元素用）
- val -> value
- html() -> innerHtml
- text() -> innerText

### 样式操作
- css()  设置行间的样式 -> style
```批量设置样式
     $('#box').css({
          width:200,
          height:100,
          border:'1px solid #000' //=>用逗号和引号
     })  

     $('#box').hide(); //=>display:none;隐藏
     $('#box').show();//=>display:block;显示
     $('#box').css('width')   -> 获取style的宽度
     $('#box').css('width',200) -> 设置宽度



```

### jQuery和原生对象的互转
```
     原生对象转jQuery只需要包$()即可


     jquery对象转原生对象

     $box -> $('box') 就变成了jquery对象

     事件中得this.jquery 元素都可以


     $box ->  $box.get(0)  ||  $box[0]



```

### jQuery原生
- 