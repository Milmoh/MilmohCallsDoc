# Make a call connection

 - Send a email to `email` with the data provided

 - Makes the call to `firstnumber`
 
 - Waits `call_interval` seconds 
 
 <sub>(This makes such that the request takes at least this ammount of time, so configure your timeout accordingly)</sub>
 
 - Makes the call to `seccondnumber` joining both numbers

**URL** : `/call`

**Method** : `POST`

<!-- **Auth required** : No

**Permissions required** : None

**Data constraints** -->

**Header**: `Content-Type: application/json`

**Data** :

```json
{
    "firstnumber": "string",
    "secondnumber": "string",
    "email": "string",
    "nombre_propiedad": "string",
    "nombre_comercializador": "string",
    "url_anuncio": "string",
    "ciudad_propiedad": "string",
    "m2_vivienda": "string",
    "precio_vivienda": "string",
    "call_interval": "integer (seconds)"
}
```

Mandatory fields : `firstnumber`, `secondnumber`, `email`

**Data example** :

Partial data is allowed.

```json
{
    "firstnumber": "+34222222222", 
    "secondnumber": "+34111111111",
    "email": "artur.temporal@milmoh.com", 
    "nombre_propiedad": "Propriedad",
    "nombre_comercializador": "Comercializador",
    "url_anuncio": "milmoh.com",
    "ciudad_propiedad":"Valencia",
    "m2_vivienda": "123",
    "precio_vivienda": "456",
    "call_interval": 15
}
```

## Success Responses

**Condition** : Data provided is valid, email is sent and calls are made.

**Code** : `200 OK`

**Content example** : `Data received successfully`

## Error Response

**Condition** : If provided data is invalid, e.g. a name field is not provided.

**Code** : `400 BAD REQUEST`

**Content example** : 
```json
{
    "Message": "Missing arguments firstnumber: {firstnumber}, secondnumber: {secondnumber}, email: {email}"
}
```
``

**Condition** : An error occured and the call could not be made or the email could not be sent

**Code** : `500 INTERNAL ERROR`

**Content example** : 
    
```json
{
    "Message": "Could not send email to {email}"
}
```
<!-- 
## Notes
 -->
