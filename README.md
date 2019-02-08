# Description

This is a custom dropdown where you can provide your own CSS to dropdown as you cant actually modify native HTML `select` tag. In addtion to this, you can filter through the list of options.

# Usage

- Create an instance of DropDown using
`let myDropdown = new DropDown("My Select", <list of options>, <configurable options>);`
- Use the render method to attach it to your HTML element
`myHTMLElement.appendChild(myDropdown.render());`

## Dropdown list options
DropDown accepts two types of lists:
1. DropDownList can be an array: ["option 1", "option 2", "option 3", ...] OR
2. it can be an Object with key value pairs: {label_1: "value_1", label_2: "value_2", label_3: "value_3", ...}
## Configurable options
Configurable options can be passed to format the dropdown:
- **className**: Customize this dropdown by providing your class name.
- **alphabetical**: Sort the list options by providing `alphabetical: true` in configuration options
- **filter**: provide the filter option to type and narrow down the list
- **callback**: pass your callback function which could be executed when an option is selected
  - Bind your callback function with your object of need for your object context
  - This callback method executes with attribue of `selected option value`
  - Refer to examples to get further insight
- **updateLabel**: On select of a list option, whether to update the display label of dropdown

# Examples
1. Basic example passing list options as an array
```
// your HTML container where you wish to place this dropdown
let selectContainer = document.getElementById('selectContainer');
let myListOptions = ['Bangalore', 'Mumbai', 'Paris', 'London', 'Shanghai', 'Venice'];
let myDropdown = new DropDown('List of cities', myListOptions);
selectContainer.appendChild(myDropdown.render());
```
2. List options as an object of key value pairs
```
// your HTML container where you wish to place this dropdown
let selectContainer = document.getElementByClassName('yourContainer');
let myListOptions = {
        'Bengaluru': 'Bangalore',
        'Mumbai': 'Bombay',
        'New Delhi': 'Delhi',
        'New York': 'new_york',
};
let myDropdown = new DropDown('List of cities', myListOptions);
selectContainer.appendChild(myDropdown.render());
```
3. Using configuration options
```
// your HTML container where you wish to place this dropdown
let selectContainer = document.getElementById('selectContainer');
let myListOptions = ['Bangalore', 'Mumbai', 'Paris', 'London', 'Shanghai', 'Venice'];
let myCallBackFunction = function(selectedValue) {/* Do something with this selected value */};
let config = {
    'className': 'myClass',
    'alphabetical': false,
    'filter': true,
    'callback': myCallBackFunction.bind(this),
    'updateLabel': true
};
let myDropdown = new DropDown('List of cities', myListOptions, config);
selectContainer.appendChild(myDropdown.render());
```

Please refer to [sample HTML file](https://github.com/shashankshovit/selectbox/blob/master/sample.html).


