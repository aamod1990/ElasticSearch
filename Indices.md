### How to Create Indices
```bash
URL : http://localhost:9200/your_index_name
Method: Put
```
### How to create type and mapping
```bash
URL: http://localhost:9200/your_index_name/_mapping/your_type_name
Method: Put
body: {
	"user_details": {
		"properties": {
			"name": {
				"type": "keyword"
			},
			"lastName": {
				"type": "keyword"
			},
			"email": {
				"type": "keyword"
			},
			"phone": {
				"type": "keyword"
			}
		}
	}
}
Note: Here user_details is type name
```

### How to insert data in elastic search
```bash
URL : http://localhost:9200/your_index_name/your_type_name/1
Method: Put
body:{
	"name": "Aamod",
	"lastName": "Tiwari",
	"email": "aamod1990@gmail.com",
	"phone": "7987561490"
}
Note:- here 1 is numeric _id which you can provide manual but if you want to create auto generated then you 
       can pass method os post
```

### How to get single and multiple records
```bash
#### For Single
URL : http://localhost:9200/learning/user_details/1
Method: get
#### For multiple records
http://localhost:9200/learning/user_details/_search?size=100
Method: get
Note:- 
```

### How to delete single and multiple records
```bash
#### For Single
URL : http://localhost:9200/learning/user_details/1
Method: delete
#### For multiple records
http://localhost:9200/learning/user_details/_delete_by_query
Method: post
body: {
  "query": {
    "match_all": {}
  }
}

Note:- 
```