# 이번 주에 배운 내용
noSQL은 SQL보다 확장성, 성능, 속도면에서 더 좋다. 

MongoDB는 document기반 데이터베이스이다. 테이블형태가 아니라 key: value의 형태로 나타낸다.


## MongoDB 사용
* 데이터베이스 생성
``` 
use DB명
``` 

* [ ]를 이용해 두 개 이상의 value값을 입력할 수 있다.
``` 
groups:["Korea", "Seoul"]
```

* 데이터 생성
``` 
하나 입력: db.컬렉션명.insertOne()
여러 항목 입력: db.컬렉션명.insertMany()
``` 

* 데이터 조회
``` 
전체 조회: db.컬렉션명.find()
항목 조회: db.myCollection.find({x:1})
id 안보이게 조회: db.myCollection.find({x:1}, {_id:false})
``` 

* 커서를 사용해 데이터에 접근할 수 있다.
```
커서 생성: var cursor = db.컬렉션명.find()
커서 이동: cursor.next()
다음 도큐먼트가 있는지 확인: cursor.hasNext()
  true면 존재 false면 없음.
``` 

* 데이터를 배열로 이용
``` 
db.컬렉션명.find().toArray()
``` 

* 데이터 수정
``` 
한 개만 수정: db.컬렉션명.replaceOne()
여러 개 수정: db.컬렉션명.replaceMany()
데이터 없을 때 새로 추가: {upsert: true}
데이터 업데이트: db.컬렉션명.updateMany()
db.myCollection.updateMany({x:6}, {$set:{"y.$[e]": 17}}, {arrayFilters:[{e:7}]})
``` 

* 데이터 삭제
``` 
하나 삭제: db.컬렉션명.deleteOne()
ex)db.myCollection.deleteOne(x:4)
전체 삭제: db.컬렉션명.deleteMany({})
``` 

* 컬럼 삭제
``` 
db.컬럼명.drop()
``` 

* 데이터베이스 삭제
``` 
db.dropDatabase()
``` 


# 문제가 발생하거나 고민한 내용
도큐먼트를 생성하고 id를 저장하려고 했는데 ObjectId()가 뜨지 않았다. 'insertedId'를 해야 하는데 'insertId'를 하고 있어서 되지 않았다.


## 과제 링크 
https://youtu.be/Lv2AW_X2-pc

\+
``` 
MongoDB Compass 사용이 편리하다.
```
\-
```
MongoDB에 한글을 넣으려고 하면 이상하게 저장된다.
```
!
```
cmd 사용이 귀찮다.
```
