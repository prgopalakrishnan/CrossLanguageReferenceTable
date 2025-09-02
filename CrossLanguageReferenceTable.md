# Cross-Language Reference (Java, Ruby, JavaScript, Python)

| **Concept** | **Java** | **Ruby** | **JavaScript** | **Python** |
|-------------|----------|----------|----------------|------------|
| **Common Data Types** | ```java
int x = 10;
double pi = 3.14;
boolean flag = true;
String name = "Alice";
``` | ```ruby
x = 10
pi = 3.14
flag = true
name = "Alice"
``` | ```js
let x = 10;
let pi = 3.14;
let flag = true;
let name = "Alice";
``` | ```python
x = 10
pi = 3.14
flag = True
name = "Alice"
``` |
| **Collections** | ```java
int[] arr = {1,2,3};
List<String> list = List.of("a","b");
Map<String,Integer> map = Map.of("a",1);
Set<Integer> set = Set.of(1,2,3);
``` | ```ruby
arr = [1,2,3]
hash = { "a" => 1, "b" => 2 }
set = Set.new([1,2,3])
``` | ```js
let arr = [1,2,3];
let obj = {a:1, b:2};
let map = new Map([["a",1]]);
let set = new Set([1,2,3]);
``` | ```python
arr = [1,2,3]
dict_obj = {"a":1, "b":2}
set_obj = {1,2,3}
tuple_obj = (1,2,3)
``` |
| **For Loop** | ```java
for (int i=0; i<5; i++) {
    System.out.println(i);
}
``` | ```ruby
for i in 0...5 do
  puts i
end
``` | ```js
for (let i=0; i<5; i++) {
  console.log(i);
}
``` | ```python
for i in range(5):
    print(i)
``` |
| **For-Each Loop** | ```java
for (String s : list) {
    System.out.println(s);
}
``` | ```ruby
arr.each do |x|
  puts x
end
``` | ```js
arr.forEach(x => console.log(x));
``` | ```python
for x in arr:
    print(x)
``` |
| **While Loop** | ```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
``` | ```ruby
i = 0
while i < 5 do
  puts i
  i += 1
end
``` | ```js
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
``` | ```python
i = 0
while i < 5:
    print(i)
    i += 1
``` |
| **HTTP GET** | ```java
HttpClient client = HttpClient.newHttpClient();
HttpRequest req = HttpRequest.newBuilder(URI.create("https://api.example.com"))
  .GET().build();
HttpResponse<String> res = client.send(req, HttpResponse.BodyHandlers.ofString());
System.out.println(res.body());
``` | ```ruby
require 'net/http'
uri = URI('https://api.example.com')
res = Net::HTTP.get(uri)
puts res
``` | ```js
fetch("https://api.example.com")
  .then(res => res.json())
  .then(data => console.log(data));
``` | ```python
import requests
res = requests.get("https://api.example.com")
print(res.json())
``` |
| **HTTP POST** | ```java
String json = "{\"key\":\"value\"}";
HttpRequest req = HttpRequest.newBuilder()
  .uri(URI.create("https://api.example.com"))
  .header("Content-Type", "application/json")
  .POST(HttpRequest.BodyPublishers.ofString(json))
  .build();
HttpResponse<String> res = client.send(req, HttpResponse.BodyHandlers.ofString());
System.out.println(res.body());
``` | ```ruby
require 'net/http'
require 'json'
uri = URI('https://api.example.com')
res = Net::HTTP.post(uri, { key: "value" }.to_json, "Content-Type" => "application/json")
puts res.body
``` | ```js
fetch("https://api.example.com", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ key: "value" })
})
.then(res => res.json())
.then(data => console.log(data));
``` | ```python
import requests
res = requests.post("https://api.example.com", json={"key": "value"})
print(res.json())
``` |
