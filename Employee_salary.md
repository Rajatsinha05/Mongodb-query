
 # EMPLOYEE QUERIES MONGODB;

# Count of Men in Engineering

```js
db.employee.find({ gender: "Male", department: "Engineering" }).count();
```

# Count of Women in Engineering who earn less than one million

```js
db.employee.find({ gender: "Female", salary: { $lt: 1000000 } }).count();
```

# Count of people make less than 80k

```js
db.employee.find({ salary: { $lt: 8000 } }).count();
```

# People who belong Accounting and Legal who make less than 100k

```js
db.employee
  .find({
    $or: [{ department: "Accounting" }, { department: "Legal" }],
    salary: { $lt: 100000 },
  })
  .count();
```

# Top 10 earning Men

```js
db.employee.find({ gender: "Male" }).sort({ salary: -1 }).limit(10);
```

# Bottom 10 earning Women

```js
db.employee.find({ gender: "Female" }).sort({ salary: 1 }).limit(10);
```

# Top 5 earning Engineering people

```js
db.employee.find({ department: "Engineering" }).sort({ salary: -1 }).limit(5);
```

# Bottom 5 earning Legal people

```js
db.employee.find({ department: "Legal" }).sort({ salary: 1 }).limit(5);
```

# Women ranked 30 to 50 in terms of salary earned

```js
db.employee.find({ gender: "Female" }).sort({ salary: -1 }).skip(30).limit(50);
```

# Men ranked 50 to 100 in terms of salary earned

```js
db.employee.find({ gender: "Male" }).sort({ salary: -1 }).skip(50).limit(100);
```

# Bottom 50 earning women in Engineering

```c++
db.employee.find({'gender':'Female'}).sort({"salary": 1}).limit(50)
```


# Top 50 earning men in Human Resources
```css
db.employee.find({"department":'Human Resources'}).sort({"salary": -1}).limit(50)
```
