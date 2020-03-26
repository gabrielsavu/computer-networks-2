# computer-networks-2

# HTTP/S

**Exercitiul 1:**

```python
import requests

def functie(nume):
    payload = {'name': nume}
    headers = {'accept': 'application/dns-json'}
    r = requests.get('https://1.1.1.1/dns-query', params=payload, headers=headers)
    print(r.json()['Answer'][0]['data'])


functie('fmi.unibuc.ro')
```

**Exercitiul 2:**

![](images/HTTP.2.png)

**Exercitiu 3:**

![](images/HTTP.3-1.png)

Modificari la functia post_method din rt1:
```python
@app.route('/post', methods=['POST'])
def post_method():
    r = request.get_json()
    print("Got from user: ", r)
    return jsonify({'value': int(r['value']) ** 2})
```

Requestul facut din rt2:

```python
import requests

payload = {'value': 10}
r = requests.post('http://rt1:8001/post', json=payload)
print(r.json())
```

![](images/HTTP.3-2.png)


**Exercitiul 4:**

Le-am citit si le stiam.



# UDP

**Exercitiul 1:**

![](images/UDP.1.png)

**Exercitiul 2:**

```python
port = 10000
adresa = '172.9.0.1'
server_address = (adresa, port)
```

![](images/UDP.2.png)

**Exercitiul 3:**

![](images/UDP.3.png)

**Exercitiul 4:**

```python
port = 10000
adresa = 'rt1'
server_address = (adresa, port)
```

**Exercitiul 5:**

![](images/UDP.5.png)

**Exercitiul 6:**

![](images/UDP.6.png)


**Exercitiul 7:**

```
18:40:20.858635 IP (tos 0x0, ttl 64, id 29532, offset 0, flags [DF], proto UDP (17), length 41)
    172.9.1.1.60564 > 172.9.0.2.8001: [bad udp cksum 0x593c -> 0xf1a3!] UDP, length 13
	0x0000:  4500 0029 735c 4000 4011 6e52 ac09 0101  E..)s\@.@.nR....
	0x0010:  ac09 0002 ec94 1f41 0015 593c 6d65 7361  .......A..Y<mesa
	0x0020:  6a20 6465 2074 6573 74                   j.de.test
18:40:20.859073 IP (tos 0x0, ttl 64, id 46690, offset 0, flags [DF], proto UDP (17), length 41)
    172.9.0.2.8001 > 172.9.1.1.60564: [bad udp cksum 0x593c -> 0xf1a3!] UDP, length 13
	0x0000:  4500 0029 b662 4000 4011 2b4c ac09 0002  E..).b@.@.+L....
	0x0010:  ac09 0101 1f41 ec94 0015 593c 6d65 7361  .....A....Y<mesa
	0x0020:  6a20 6465 2074 6573 74                   j.de.test
```

![](images/UDP.7.png)