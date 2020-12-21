# remove-any-key-in-object
remove any key in object
```
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

function removeTrashKeys(obj) {
  getProp(obj);

  function getProp(arr) {
    for (const prop in arr) {
      if (typeof arr[prop] === "object" ) {
        getProp(arr[prop]);
        if (arr[prop].created) delete arr[prop].created;
        if (arr[prop].updated) delete arr[prop].updated;
      }
    }
  }
}

removeTrashKeys(obj);

console.log(obj);
```
