Requête de type:GET  

**Petit rappel**  
Ne pas oublier votre [token :-) 

Exemple de code en `jQuery/JavaScript`:  
```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-ban.ign.fr/group",
  "method": "GET",
  "headers": {
    "cookie": "banprodcookie=banprodcookie",
    "content-type": "application/x-www-form-urlencoded",
    "authorization": "Bearer iBLobfsNWVCeZOiQmkJKIPvdvyPy2j"
  },
  "data": {
    "": ""
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

<hr>

### Table 'group'
`https://api-ban.ign.fr/group`

```json
{
	"collection": [
		{
			"addressing": null,
			"alias": [],
			"attributes": {
				"init_source_name": "fantoir"
			},
			"fantoir": "01004B256",
			"id": "ban-group-aa8844957f154493b73382777498c73b",
			"ign": null,
			"kind": "area",
			"laposte": null,
			"municipality": "ban-municipality-6ae6ccf226d24ade9f6c6af87374800a",
			"name": "TERRE GAILLARD",
			"resource": "group",
			"version": 1
		}

...
```

<hr>

### Table 'housenumber'
`https://api-ban.ign.fr/housenumber`

```json
{
	"collection": [
		{
			"attributes": {
				"source_init": "LAPOSTE"
			},
			"cia": "01007_0092__",
			"id": "ban-housenumber-03f2e14d65f84815959f1ebcee86d14d",
			"ign": null,
			"laposte": "010072222E",
			"number": null,
			"ordinal": null,
			"parent": "ban-group-a5a93247b73d4450bae76b05729a22e4",
			"postcode": "ban-postcode-ae76a689fcfc4849b5a9f1e2e9e0deac",
			"resource": "housenumber",
			"version": 1
		}
...
```
<hr>

### Table 'postcode'
`https://api-ban.ign.fr/postcode`

```json
{
	"collection": [
		{
			"alias": [],
			"attributes": {},
			"code": "01000",
			"complement": null,
			"id": "ban-postcode-642794c25d1b4e1eadb6ed6bdb8179c9",
			"municipality": "ban-municipality-b85b336705404267ad9828fc2450e530",
			"name": "BOURG EN BRESSE",
			"resource": "postcode",
			"version": 1
		}
...
```
<hr>

### Table 'position'
`https://api-ban.ign.fr/position`

```json
{
	"collection": [
		{
			"attributes": {},
			"center": {
				"coordinates": [
					5.981473,
					46.18216
				],
				"type": "Point"
			},
			"comment": null,
			"housenumber": "ban-housenumber-b85bf54484a14a4b89077eb947a9ed98",
			"id": "ban-position-ce246ce583da41bd898255ab79211bef",
			"ign": null,
			"kind": "entrance",
			"laposte": null,
			"name": null,
			"parent": null,
			"positioning": "other",
			"resource": "position",
			"source": "DGFIP/BANO (12/2016)",
			"source_kind": "dgfip",
			"version": 1
		}
...
```