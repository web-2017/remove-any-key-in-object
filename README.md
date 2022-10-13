# How remove nasted deep key in object

### Array example
```js
const obj = [
  {
    name: "dsad",
    created: "afads",
    updated: "asdf",
    desc: {
      name: "desc",
      created: "afads",
      updated: "asdf",
      newArr: [
        {
          name: "desc",
          created: "afads",
          updated: "asdf"
        }
      ]
    }
  },
  {
    name: "2222",
    created: "afads",
    updated: "asdf"
  },
  {
    name: "333",
    created: "afads",
    updated: "asdf"
  }
];
```

#### Function
```js 
const removeKeys = (props) => {
  getObj(props);

  function getObj(props) {
    for (const key in props) {
      if (typeof props === "object") {
        getObj(props[key]);

        ["data", "id"].forEach((item) => {
          if (props[key][item]) delete props[key][item];
        });

        return props[key];
      }
    }
  }
  return props;
};


const newObj = removeKeys(obj);

console.log(obj);

```
