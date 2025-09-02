# Cross-language Reference: Java, Ruby, JavaScript, Python

This table highlights equivalents across languages for:
- Primitive Data Types
- Looping Constructs
- Collections
- HTTP GET/POST (sync + async/await)

---

| Concept | Java | Ruby | JavaScript | Python |
|---------|------|------|------------|--------|
| **Primitive Types** | `int a = 10;`<br>`double d = 3.14;`<br>`String s = "hello";`<br>`boolean flag = true;` | `a = 10`<br>`d = 3.14`<br>`s = "hello"`<br>`flag = true` | `let a = 10;`<br>`let d = 3.14;`<br>`let s = "hello";`<br>`let flag = true;` | `a = 10`<br>`d = 3.14`<br>`s = "hello"`<br>`flag = True` |
| **For Loop** | `for (int i=0; i<5; i++) { System.out.println(i); }` | `for i in 0...5 do puts i end` | `for (let i=0; i<5; i++) { console.log(i); }` | `for i in range(5): print(i)` |
| **While Loop** | `int i=0; while (i<5) { i++; }` | `i = 0; while i < 5 do i += 1 end` | `let i=0; while (i<5) { i++; }` | `i = 0; while i < 5: i += 1` |
| **Collections: Arrays / Lists** | `int[] arr = {1,2,3};`<br>`List<String> list = Arrays.asList("a","b");` | `arr = [1,2,3]` | `let arr = [1,2,3];` | `arr = [1,2,3]` |
| **Collections: Hash/Map/Dict** | `Map<String,Integer> map = new HashMap<>(); map.put("a",1);` | `h = {"a" => 1, "b" => 2}` | `let obj = {"a": 1, "b": 2};` | `d = {"a": 1, "b": 2}` |
| **HTTP GET (sync)** | `HttpClient c = HttpClient.newHttpClient(); HttpRequest r = HttpRequest.newBuilder(URI.create("https://api.example.com")).GET().build(); HttpResponse<String> res = c.send(r, HttpResponse.BodyHandlers.ofString()); System.out.println(res.body());` | `require 'net/http'; res = Net::HTTP.get(URI('https://api.example.com')); puts res` | `fetch("https://api.example.com").then(res => res.json()).then(d => console.log(d));` | `import requests; res = requests.get("https://api.example.com"); print(res.text)` |
| **HTTP POST (sync)** | `HttpRequest r = HttpRequest.newBuilder(URI.create("https://api.example.com")).POST(HttpRequest.BodyPublishers.ofString("{\"key\":\"value\"}")).header("Content-Type","application/json").build(); HttpResponse<String> res = c.send(r, HttpResponse.BodyHandlers.ofString()); System.out.println(res.body());` | `require 'net/http'; require 'json'; uri = URI('https://api.example.com'); res = Net::HTTP.post(uri, {key:'value'}.to_json, {"Content-Type"=>"application/json"}); puts res.body` | `fetch("https://api.example.com",{method:"POST",headers:{"Content-Type":"application/json"},body:JSON.stringify({key:"value"})}).then(res=>res.json()).then(d=>console.log(d));` | `import requests; res = requests.post("https://api.example.com", json={"key":"value"}); print(res.json())` |
| **HTTP GET (async/await)** | `HttpClient c = HttpClient.newHttpClient(); HttpRequest r = HttpRequest.newBuilder(URI.create("https://api.example.com")).GET().build(); c.sendAsync(r, HttpResponse.BodyHandlers.ofString()).thenAccept(res -> { System.out.println(res.body()); });` | `require 'async'; require 'httpx'; Async do; res = HTTPX.get("https://api.example.com"); puts res.to_s; end` | `async function getData(){ const res = await fetch("https://api.example.com"); const d = await res.json(); console.log(d);} getData();` | `import aiohttp, asyncio; async def main(): async with aiohttp.ClientSession() as s: async with s.get("https://api.example.com") as res: print(await res.text()); asyncio.run(main())` |
| **HTTP POST (async/await)** | `HttpRequest r = HttpRequest.newBuilder(URI.create("https://api.example.com")).POST(HttpRequest.BodyPublishers.ofString("{\"key\":\"value\"}")).header("Content-Type","application/json").build(); c.sendAsync(r, HttpResponse.BodyHandlers.ofString()).thenAccept(res -> { System.out.println(res.body()); });` | `require 'async'; require 'httpx'; Async do; res = HTTPX.post("https://api.example.com", json:{key:"value"}); puts res.to_s; end` | `async function sendData(){ const res = await fetch("https://api.example.com",{method:"POST",headers:{"Content-Type":"application/json"},body:JSON.stringify({key:"value"})}); const d = await res.json(); console.log(d);} sendData();` | `import aiohttp, asyncio; async def main(): async with aiohttp.ClientSession() as s: async with s.post("https://api.example.com", json={"key":"value"}) as res: print(await res.json()); asyncio.run(main())` |

---
