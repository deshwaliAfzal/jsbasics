### creat database
```
use wecodeacademy ;

```

### creat colloction
```
db.createCollection("batch");

```

### insert data in colloction
```
db.batch.insertMany([
  {batchName : "Node.js", students : ["aafzal", "asfaq", "majeet"],
   duration : 5, fees: 5000, marks : [10,20,30,40,50]},

  {batchName : "Design", students : ["arif", "khalil", "irfan", "adil"],
   duration : 5, fees: 12000, marks : [10,20,30]}, 

  {batchName : "Java", students : ["arif", "khalil", "irfan"],
   duration : 5, fees: 13000, marks : [10,80,60]}, 

  {batchName : "javaScript", students : ["arif", "khalil","adil"],
   duration : 5, fees: 5000, marks : [71,26,99,67]}, 

  {batchName : "ComputerScience", students : ["khalil", "irfan", "adil"],
   duration : 5, fees: 1000, marks : [60,60,60]}])

```

### Vo sare batches ke naam btao jinke student ke marks 50% se kam hai
```
{marks : {$lt : 50}},

```

### marks array me se sirf vhi marks rkhne hain jo 50+ hain. baki sbko remove krdo
```
db.batch.updateMany({},{$pull : {marks : {$lt : 50}}});

```

### marks array me starting se 3rd index se 5 new marks add krne hai
```

```

###  Back/Last se 4th position se 5 new marks add krne hain.
```

```

### Agar marks array me max number 99 hai to thik otherwise max number 99 krdo
```
db.batch.updateMany({}, {$max : {marks : 99}});

```

### fees field ko rename krke totalfees krdo
```
db.batch.updateMany({}, {$rename : {"fees": "totalFee"}});

```

### duration ko 2 se multiply krdo
```
db.batch.updateMany({}, {$mul : {duration : 2}});

```

###  students array me se Irfan, Adil ka naam hai to remove krdo
```
db.batch.updateMany({}, {$pull : {student : {$in : ["irfan", "adil"]}}});

```

### Vo sare students search kro jinke naam me Khan hai aur batchName Designing hai aur fees 12000 se
 jyada hai aur students array ki size 10 ho
 ```


 ```
 
 # TEST-2
 
 ### creating schema
```
db.createCollection("students",{
    validator:{
        $jsonSchema:{
            bsonType: "object",
            required: ["studentName", "fathername" , "dob" , "email" , "mobile" , "batchname" ],
            properties:{
                studentName:{
                    bsonType: 'string',
                    description : "studentName should be string",
                },
                fathername:{
                    bsonType: 'string',
                    description : "Fathername should be string",
                },
                mothername:{
                    bsonType: 'string',
                    description : "Mothername should be string",
                },
                dob:{
                    bsonType: 'string',
                    description : "DOB should be date",
                },
                email:{
                    bsonType: 'string',
                    pattern: "^\\S+@\\S+\\.\\S+$",
                    description : "Email should be valid email address",
                },
                mobile:{
                    bsonType: 'string',
                pattern: "^(\\+91|86)?[6789]\\d{9}$",
                    description : "Mobile should be start with +91 or 86",
                },
                batchname:{
                   enum:['nodejs' ,'designing' , 'javascript' , 'computerscience'],
                    description : "Batchname should be string or enum",
                },
                fees:{
                    bsonType: 'number',
                    description : "fees should be string",
                },
            }
        }
    }
})

```


### inserting document

```
db.students.insertOne({
  "studentName" : "afzal khan",
  "fathername" : "sikander khan",
  "dob" : "2004-02-27",
  "email" : "afzal.deshwali@gmail.com",
  "mobile" : "8619426228",
  "batchname" : "nodejs"
})
```
