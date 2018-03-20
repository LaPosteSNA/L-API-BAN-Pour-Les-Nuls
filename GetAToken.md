# BAN

## Test de l'API

### Obtenir un "token"
Pour sécuriser les transactions, il est nécessaire d'avoir un "token" qui vous identifie pendant 60 minutes.

Exemple d'appel via un shell avec la commande 'curl':
```c
curl -X POST https://api-ban.ign.fr/token -H 'Content-Type: application/x-www-form-urlencoded' -d 'grant_type=client_credentials&email=philippe.clech%40laposte.fr&client_id=votre_id&client_secret=c'est un secret&contributor_type=laposte'
```
Si tout se passe bien vous récupérez une structure 'json' :
```json
{
	"grant_type": "client_credentials",
	"client": "C488d198-L0c8-Ia6b-Ebe0-Ne97cTc30d31",
	"token_type": "Bearer",
	"email": "philippe.clech@laposte.fr",
	"client_secret": "c'est un secret",  
	"scope": "municipality_write postcode_write group_write housenumber_write position_write",
	"expires_in": 3600,
	"client_id": "votre_id",
	"access_token": "mMGGByAcNMKz0Dpql2a6uqSEviGKsj",
	"contributor_type": "laposte"
}
```

Lors de l'utilisation du token vous devez impérativement ajouter devant "Bearer " <== Attention à l'espace après.

#### Tester son token :
```c
curl -X GET https://api-ban.ign.fr/postcode -H 'Authorization: Bearer <votre "access_token">'
```
ou
```c
curl -X GET https://api-ban.ign.fr/housenumber/ign:ADRNIVX_0000000264335323 -H 'Authorization: Bearer <votre "access_token">'
```
