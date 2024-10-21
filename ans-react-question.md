** All following exams please using JavaScript only **

## 1.

### Question 1

```javascript
/**
There is an array, each item has such format:
{ firstName: 'xxx', lastName: 'xxx', customerID: 'xxx', note: 'xxx', profession: 'xxx' }
lastName, note can be empty, customerID can only be a set of digital numbers.
profession can only have ‘student’, ‘freelancer’, ‘productOwner’, ‘engineer’ or ‘systemAnalytics’.
**/

/**
Q1. Please follow the principle (‘firstName’ + ‘lastName’ + ‘customerID’) to sort this array and print it out.
**/
```

### Answer 1

```javascript
// customers is an array, each item has the format mentioned in the question.
/*
// Sample array
const customers = [
  { firstName: 'John', lastName: 'Doe', customerID: '123', note: '', profession: 'engineer' },
  { firstName: 'Alice', lastName: 'Smith', customerID: '456', note: 'VIP', profession: 'freelancer' },
  { firstName: 'Bob', lastName: '', customerID: '789', note: 'New', profession: 'student' },
  { firstName: 'John', lastName: 'Smith', customerID: '101', note: '', profession: 'productOwner' },
  { firstName: 'Jane', lastName: 'Doe', customerID: '102', note: 'Important', profession: 'systemAnalytics' }
];
*/

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

### Question 2

```javascript
/**
Q2. Please sort by ‘profession’ to follow the principle. (‘systemAnalytics’ > ‘engineer’ > ‘productOwner’ > ‘freelancer’ > ‘student’’)
**/
```

### Answer 2

```javascript
// Sample array
/*
const customers = [
  { firstName: 'John', lastName: 'Doe', customerID: '123', note: '', profession: 'engineer' },
  { firstName: 'Alice', lastName: 'Smith', customerID: '456', note: 'VIP', profession: 'freelancer' },
  { firstName: 'Bob', lastName: '', customerID: '789', note: 'New', profession: 'student' },
  { firstName: 'John', lastName: 'Smith', customerID: '101', note: '', profession: 'productOwner' },
  { firstName: 'Jane', lastName: 'Doe', customerID: '102', note: 'Important', profession: 'systemAnalytics' }
];
*/

// Custom profession ranking
const professionRank = {
  'systemAnalytics': 5,
  'engineer': 4,
  'productOwner': 3,
  'freelancer': 2,
  'student': 1
};

// Sorting logic based on profession ranking
customers.sort((a, b) => {
  return professionRank[b.profession] - professionRank[a.profession];
});

// Print the sorted array
console.log(customers);

```

## 2.

```html
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
.container .shop-list li.item {
  color: green;
}
.container .shop-list .item {
    /* Explain why does this color not works, and how to fix make it work on 1st list */
  color: blue;
}
/* Write styling make every other line give background color to next one */
```

### Answers

#### Explain why does this color not works
The selector `.container .shop-list .item` has lower specificity than the selector `.container .shop-list li.item`, so the latter option will be used.

#### How to fix it to make it work on the 1st list
A: Instead of using `.container .shop-list .item`, we need to use `.container ol.shop-list .item` to make it work on the 1st list.

#### Write styling make every other line give background color to next one
```css
.container .shop-list li:nth-child(odd) {
  background-color: green; /* This applies to odd items */
}

.container .shop-list li:nth-child(even) {
  background-color: blue; /* This applies to even items */
}
```
    
## 3.

### Question
```javascript
/**
let items = [1, 1, 1, 5, 2, 3, 4, 3, 3, 3, 3, 3, 3, 7, 8, 5, 4, 9, 0, 1, 3, 2, 6, 7, 5, 4, 4, 7, 8, 8, 0, 1, 2, 3, 1];
Please write down a function to console log unique value from this array.
**/
```

### Answer
```javascript
function getUniqueNumber (items) {
  console.log(Array.from(new Set(items)));
}
```

## 4.
### Question
```javascript
/** Can you explain about Interface and Enum, and where will you be using, please make some examples. **/
```
### Answer

- `Interface` and `Enum` are commonly used in TypeScript, while TypeScript is a superset of JavaScript.
- `Interface` is to define the structure of an object.
- `Enum` is to define a set of name constants, and each represents a distinct value.

#### Example of Interface
```javascript
interface Customer {
  customerID: number;
  name: string;
  email: string;
  isActive: boolean;
}

const newCustomer: Customer = {
  customerID: 101,
  name: "Alice Johnson",
  email: "alice.johnson@example.com",
  isActive: true,
};

function displayCustomerInfo(customer: Customer) {
  console.log(`Customer ID: ${customer.customerID}`);
  console.log(`Name: ${customer.name}`);
  console.log(`Email: ${customer.email}`);
  console.log(`Active: ${customer.isActive ? "Yes" : "No"}`);
}

displayCustomerInfo(newCustomer);
```

#### Example of Enum

```javascript
enum Weekday {
  Sunday,
  Monday,
  Tuesday,
  Wednesday,
  Thursday,
  Friday,
  Saturday
}

function isWeekend(day: Weekday): boolean {
  return day === Weekday.Saturday || day === Weekday.Sunday;
}

const today: Weekday = Weekday.Friday;

console.log(`Is today the weekend? ${isWeekend(today) ? "Yes" : "No"}`);
```

#### Example of Interface and Enum

```javascript
enum MembershipLevel {
  Basic,
  Silver,
  Gold,
  Platinum
}

interface Customer {
  customerID: number;
  name: string;
  email: string;
  membership: MembershipLevel;  // Use enum as a property type
}

const customer1: Customer = {
  customerID: 1,
  name: "John Doe",
  email: "john.doe@example.com",
  membership: MembershipLevel.Gold  // Assign enum value
};

function displayCustomerDetails(customer: Customer) {
  console.log(`Customer Name: ${customer.name}`);
  console.log(`Membership Level: ${MembershipLevel[customer.membership]}`);  // Convert enum to string
}

displayCustomerDetails(customer1);
```

## 5.
### Question
```javascript
/** Can you explain the problem with the following code, and how to fix it. **/
class Count extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
    this.handleAddCount = this.handleAddCount.bind(this);
  }
  handleAddCount(){
    this.setState({ count: this.state.count + 1 });
    this.setState({ count: this.state.count + 1 });
    this.setState({ count: this.state.count + 1 });
  }
  render() {
    return (
      <div>
        <h2>{this.state.count}</h2>
        <button onClick={this.handleAddCount}>Add</button>
      </div>
    );
  }
}

ReactDOM.render(
  <Count />,
  document.getElementById('root')
);
```

### Answer
All the 3 statements, `this.setState({ count: this.state.count + 1 });`, inside `handleAddCount()`, will set the state to `1` instead of incrementing it to `3`. The reason is that, `setState` is asynchronous, therefore, the state won't be immediately updated.
To fix this problem, we need to catch the current state first. Let's revise the code:

```javascript
handleAddCount() {
  this.setState((prevState) => ({ count: prevState.count + 3 }));
}
```

## 6.
### Question
```javascript
/** Please write the sample code to debounce handleOnChange **/
```

### Answer
```javascript
var SearchBox = React.createClass({
  timeout: null, // To store the timeout ID
  
  render: function() {
    return <input type="search" name="p" onChange={this.handleOnChange} />;
  },
  
  handleOnChange: function(event) { 
    const query = event.target.value;
    
    // Clear any previous timeout
    if (this.timeout) {
      clearTimeout(this.timeout);
    }

    // make ajax call (debounced)
    this.timeout = setTimeout(() => {
      // Perform the ajax call here with the search query
      console.log('Search query:', query); // Placeholder for actual ajax call
    }, 300); // 300ms debounce delay
  }
});
```
