# MongoDB Queries

### All users whose gender is male

```bash
db.users.find({gender:'Male'})
```

### All users whose ID is even

```bash
db.users.find({id:{$mod:[2,0]}})
```

### Users who currently live in Japan

```bash
db.users.find({native:'Japan'})
```

### Users who are female and live in India

```bash
db.users.find({native:'India',gender:'Female'})
```

### Users who are more than 25 years old

```bash
db.users.find({age:{$gt:25}})
```

### Users who are less than 50 years old and live in United State

```bash
db.users.find({native:'United States',age:{$lt:50}})
```

### Total number of users who want to relocate to France (count only)

```bash
db.users.find({relocate_to:'France'}).count()
```

### Total number of users who are from USA and want to relocate to russia, sort them by age in ascending order

```bash
 db.users.find({native:'United States',relocate_to:'Russia'}).sort({age:1})
```

### get all users, sort them by total number of family member ASC and age DESC order

```bash
db.users.find().sort({family_members: 1,age:-1})
```
