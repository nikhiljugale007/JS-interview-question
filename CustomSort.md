## ques : the output should be sorted by name if name is same then smaller age first:
``` 
const input = [
    { name: "Sreekanth", age: 30, gender: "M" },
    { name: "Sai", age: 30, gender: "M" },
    { name: "Shaik", age: 30, gender: "F" },
    { name: "Sreekanth", age: 24, gender: "M" },
    { name: "Sai", age: 21, gender: "F" }
  ];
const output = [
    {"name":"Sai","age":21,"gender":"F"},
    {"name":"Sai","age":30,"gender":"M"},
    {"name":"Shaik","age":30,"gender":"F"},
    {"name":"Sreekanth","age":24,"gender":"M"},
    {"name":"Sreekanth","age":30,"gender":"M"}
]
```

## Solution1 :
 ```
const customSort = (person1, person2) => {
    if(person1.name < person2.name) {
        return -1;
    }
    else if(person2.name > person1.name){
        return 1;
    }
    else{
        if(person1.age < person2.age){
            return -1;
        }
        else{
            return 1;
        }
    }
    return 0;
}
console.log(input.sort(customSort));
```
## Solution2:
```
  const output = input.sort((firstPersonObj,secondPersonObj)=>{
    if(firstPersonObj.name.toLowerCase()<secondPersonObj.name.toLowerCase())
    {
        return -1
    }
    else
    {
        if(firstPersonObj.name.toLowerCase()===secondPersonObj.name.toLowerCase())
        {
            if(firstPersonObj.age<secondPersonObj.age)
            {
                return -1
            }
        }
        else
        {
            return 1
        }
    }
})

console.log(output)
```

## Must read: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort
