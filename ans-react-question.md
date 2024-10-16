** All following exams please using JavaScript only **

## 1.

### Question

```javascript=
There is an array, each item has such format:
{ firstName: 'xxx', lastName: 'xxx', customerID: 'xxx', note: 'xxx', profession: ‘xxx’ }
lastName, note can be empty, customerID can only be a set of digital numbers.
profession can only have ‘student’, ‘freelancer’, ‘productOwner’, ‘engineer’ or ‘systemAnalytics’.
**/

/**
Q1. Please follow the principle (‘firstName’ + ‘lastName’ + ‘customerID’) to sort this array and print it out.
**/
```

### Answer

```javascript=
// Function to sort the array
function sortUserName(user) {
  return user.sort((a, b) => {
    const userA = a.firstName + a.lastName + a.customerID;
    const userB = b.firstName + b.lastName + b.customerID;
    return userA.localeCompare(userB);
  });
}

// Sort and print the result
const sortedCustomers = sortUserName(customers);
console.log(sortedCustomers);
```

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

```css=
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

### Answers

#### Explain why does this color not works

#### How to fix it to make it work on the 1st list
A: Instead of using `.container .shop-list .item`, we need to use `.container ol.shop-list .item` to make it work on the 1st list.

#### Write styling make every other line give background color to next one
```css=
.container .shop-list li:nth-child(odd) {
  background-color: white; /* This applies to odd items */
}

.container .shop-list li:nth-child(even) {
  background-color: lightgray; /* This applies to even items */
}
```
    
## 3.

### Question
```javascript=
/**
let items = [1, 1, 1, 5, 2, 3, 4, 3, 3, 3, 3, 3, 3, 7, 8, 5, 4, 9, 0, 1, 3, 2, 6, 7, 5, 4, 4, 7, 8, 8, 0, 1, 2, 3, 1];
Please write down a function to console log unique value from this array.
**/
```

### Answer
```javascript=
function getUniqueNumber (items) {
    console.log(Array.from(new Set(items)));
}
```

## 4.
```
/** Can you explain about Interface and Enum, and where will you be using, please make some examples. **/
```



## 5.
```javascript=
/** Can you explain the problem with the following code, and how to fix it. **/
class Count extends React.Component { constructor(props) {
super(props);
this.state = { count: 0 };
this.handleAddCount = this.handleAddCount.bind(this);
}
handleAddCount(){
  this.setState({
  this.setState({
  this.setState({
}
render() {
  return (
<div>
count: this.state.count + 1 });
count: this.state.count + 1 });
count: this.state.count + 1 });
<h2>{this.state.count}</h2>
<button onClick={this.handleAddCount}>Add</button> </div>
); }
}
ReactDOM.render(
<Count />, document.getElementById('root')
);
```

## 6.
```
/** Please write the sample code to debounce handleOnChange **/
var SearchBox = React.createClass({ render: function() {
return <input type="search" name="p" onChange={this.handleOnChange} />;
},
handleOnChange: function(event) { // make ajax call
} });
```
