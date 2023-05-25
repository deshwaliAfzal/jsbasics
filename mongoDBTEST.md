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
db.batches.insertMany([
  {batchName : "Node.js", student : ["arif", "sher mohammad", "khalil"],
   duration : 5, fees: 5000, marks : [10,20,30,40,50]},

  {batchName : "Design", student : ["arif", "khalil", "irfan", "adil"],
   duration : 5, fees: 12000, marks : [10,20,30]}, 

  {batchName : "Java", student : ["arif", "khalil", "irfan"],
   duration : 5, fees: 13000, marks : [10,80,60]}, 

  {batchName : "javaScript", student : ["arif", "khalil","adil"],
   duration : 5, fees: 5000, marks : [71,26,99,67]}, 

  {batchName : "ComputerScience", student : ["khalil", "irfan", "adil"],
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
