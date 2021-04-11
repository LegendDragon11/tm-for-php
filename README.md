# tm-for-php Token Manager for your php projects
Using OAuth in your project, presents token and other OAuth stuff. This libary is only for people who want a authorization on the server device! (not for websites)

[![Discord](https://img.shields.io/discord/690934524955197471?label=Discord&logo=discord)](https://discord.gg/MFhh5XEM2b)

## Import
Download the tm folder and put it in your project.
After that you can call the tm with:
```php
require_once( dirname(dirname(__FILE__) ) . "/tm/tm.php");
```
In Some cases you must correct the path. (the ending must be tm.php)
## How to run
Now you can use the functions and make a simple api call with
```php
authorize("your api url with endpoint [authorization]", "your client_id", "your scopes");
```
after the authorization you can access the tokens with:
```php
$access_token = getToken("your api url with endpoint [token]", "your client_id", "your client_secret");
```
after these steps your done!
## Access your data
After the Authorization procress you can get the auth_code with:
```php
$auth_code = getAuthorizeCode();
```
and after the token call you can get the access token with:
```php
$access_token = getToken("your api url with endpoint [token]", "your client_id", "your client_secret");
```
for all informations you can use get...
```php
$access_token = getAccessToken();
$refresh_token = getRefreshToken();
$id_token = getIdToken();
$last_token_call = getLastTokenCall();
$token_type = getTokenType();
$expires_in = getExpiresIn();
$scopes = getScopes();
```
after these steps your done!
## Scope change
If youre api allowes scope chaning you can refresh the token and change your scopes:
```php
$access_token = refreshToken("your api url with endpoint [token]", "your client_id", "your client_secret", "new scopes");
```
