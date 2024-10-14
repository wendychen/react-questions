## 2.

```html=
<div class="container">
    <div class="header">5/8 外出確認表</div>
        <div class="content">
            <ol class="shop-list">
                <li class="item">麵包</li>
                <li class="item">短袖衣服</li>
                <li class="item">飲用水</li>
                <li class="item">帳篷</li>
            </ol>
            <ul class="shop-list">
                <li class="item">暈車藥</li>
                <li class="item">感冒藥</li>
                <li class="item">丹木斯</li>
                <li class="item">咳嗽糖漿</li>
            </ul>
        </div>
    <div class="footer">以上僅共參考</div>
</div>
```

```css
.container {
  font-size: 14px;
}
.container .header {
  font-size: 18px;
}
.container .shop-list {
   list-style: none;
   margin-left: -15px;
}
.container .shop-list li.item { color: green;
}
.container .shop-list .item {
    /* Explain why does this color not works, and how to fix make it work on 1st list */
   color: blue;
}
/* Write styling make every other line give background color to next one */
```

Q: How to fix it to make it work on the 1st list?
A: Instead of using `.container .shop-list .item`, we need to use `.container .shop-list ol.item` to make it work on the 1st list.
    
## 3.
/**
let items = [1, 1, 1, 5, 2, 3, 4, 3, 3, 3, 3, 3, 3, 7, 8, 5, 4, 9, 0, 1, 3, 2, 6, 7, 5, 4, 4, 7, 8, 8, 0, 1, 2, 3, 1];
Please write down a function to console log unique value from this array.
**/
function getUniqueNumber (items) {
    console.log(Array.from(new Set(items)));
}
