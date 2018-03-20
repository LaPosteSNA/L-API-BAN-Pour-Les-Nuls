# Ajouter une commune

On commence avec la table municipality:
url:`https://api-ban.ign.fr/municipality`  
type:POST  
Dans le header de la requête pensé a mettre le 'Content-Type' > 'application/json'  
```
Authorization: {{ token  }}
Content-Type: application/json
```

Les paramètres minimums sont:
```json
{
    "insee":"99995",
    "name":"Dark-Vador"
}
```

Si tous ce passe bien...
```json
{
	"alias": [],
	"attributes": null,
	"created_at": "2018-03-16T16:10:54.608329+00:00",
	"created_by": {
		"client": "test_projet_ban_laposte",
		"contributor_type": "laposte",
		"id": 889620,
		"user": null
	},
	"id": "ban-municipality-90d25613d1c9413ba25ff915dea0adb7",
	"insee": "99995",
	"modified_at": "2018-03-16T16:10:54.608329+00:00",
	"modified_by": {
		"client": "test_projet_ban_laposte",
		"contributor_type": "laposte",
		"id": 889620,
		"user": null
	},
	"name": "Dark-Vador",
	"postcodes": [],
	"siren": null,
	"status": "active",
	"version": 1
}
```
ou pas bien..."Vous avez pensé a renouveller le token ? ^^"
```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 3.2 Final//EN">
<title>401 Unauthorized</title>
<h1>Unauthorized</h1>
<p>The server could not verify that you are authorized to access the URL requested.  You either supplied the wrong credentials (e.g. a bad password), or your browser doesn't understand how to supply the credentials required.</p>
```

## Ajouter un code postal à cette nouvelle commune
url:`https://api-ban.ign.fr/postcode`  
type:POST  
Les paramètres minimums sont:
Pour la proprièté "municipality", récupérer le code `"id": "ban-municipality-90d25613d1c9413ba25ff915dea0adb7",` qui se trouve dans le retour lors de la création de la commune.
```json
{
	"insee":"99995",
	"name":"Dark-Vador",
	"municipality":"ban-municipality-90d25613d1c9413ba25ff915dea0adb7",
	"code":"66600"
}
```

## Voir la nouvelle commune
url:`https://api-ban.ign.fr/municipality/insee:99995`  
type:GET  

```json
Voici ce que l'on a pour l'instant :
{
	"alias": [],
	"attributes": null,
	"created_at": "2018-03-16T16:10:54.608329+00:00",
	"created_by": {
		"client": "test_projet_ban_laposte",
		"contributor_type": "laposte",
		"id": 889620,
		"user": null
	},
	"id": "ban-municipality-90d25613d1c9413ba25ff915dea0adb7",
	"insee": "99995",
	"modified_at": "2018-03-16T16:10:54.608329+00:00",
	"modified_by": {
		"client": "test_projet_ban_laposte",
		"contributor_type": "laposte",
		"id": 889620,
		"user": null
	},
	"name": "Dark-Vador",
	"postcodes": [],
	"siren": null,
	"status": "active",
	"version": 1
}
```
## Modifier le nom de la commune
url:`https://api-ban.ign.fr/municipality/ban-municipality-90d25613d1c9413ba25ff915dea0adb7`  
type:PUT  

Le json à envoyer:  
```json
{
	"insee": "99995",
	"name": "Palpatine",
	"version": "2" 
}
```

## Modifier une L5
url:`https://api-ban.ign.fr/municipality/`  
type:PUT  

json:
```json
{
    
}
```

