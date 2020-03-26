# computer-networks-2

# HTTP/S

Exercitiul 1:

```python
import requests

def functie(nume):
    payload = {'name': nume}
    headers = {'accept': 'application/dns-json'}
    r = requests.get('https://1.1.1.1/dns-query', params=payload, headers=headers)
    print(r.json()['Answer'][0]['data'])


functie('fmi.unibuc.ro')
```

Exercitiul 2:

![](images/HTTP.2.png)

*Exercitiu 3:*

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
