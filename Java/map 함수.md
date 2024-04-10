**HashMap 선언**
```java
//HashMap 생성
HashMap<String, String> map1 = new HashMap<String, String>();

//new에서 파라미터 타입 생량 가능
HashMap<String, String> map2 = new HashMap<String, String>();

//map1에서 모든 값을 가진 HashMap 생성
HashMap<String,String> map3 = new HashMap<>(map1);

//초기 용량(capacity) 지정
HashMap<String, String> map4 = new HashMap<>(10);

//초기 capacity, load factor 지정
//load factor : 해시 테이블 전체에서 얼마나 원소가 차 있는지를 나타내는 수치
HashMap<String, String> map5 = new HashMap<>(10, 0.7f);

//초기값 지정
HashMap<String, String> map6 = new HashMap<String, String>() {{
put("a", "b");
}};
```

**HashMap 추가**
```java
HashMap<Integer, String> map = new HashMap<>();

map.put(1, "쥐");
map.put(2, "바나나");
map.put(3, "호랑이");

System.out.println(map); //{1=쥐, 2=바나나, 3=호랑이}
```

**HashMap 삭제**
```java
map.remove(1);
System.out.println(map); //{2=바나나, 3=호랑이}

map.clear();
System.out.println(map); //{}


```

**HashMap 값 출력**
```java
// 특정 Key값의 Value를 가져올때
get(key)
System.out.println(map.get(1));
        
//전체 출력
entrySet()
        
for (Entry<Integer, String> entry : map.entrySet()) {
System.out.println("[Key]:" + entry.getKey() + " [Value]:" + entry.getValue());
}
keySet()

for(Integer i : map.keySet()){
System.out.println("[Key]:" + i + " [Value]:" + map.get(i));
}
Iterator

//entrySet().iterator()
Iterator<Entry<Integer, String>> entries = map.entrySet().iterator();
while(entries.hasNext()){
Map.Entry<Integer, String> entry = entries.next();
System.out.println("[Key]:" + entry.getKey() + " [Value]:" +  entry.getValue());
}

//keySet().iterator()
Iterator<Integer> keys = map.keySet().iterator();
while(keys.hasNext()){
int key = keys.next();
System.out.println("[Key]:" + key + " [Value]:" +  map.get(key));
}
```