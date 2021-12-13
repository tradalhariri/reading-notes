# JSON Web Tokens

## What is JSON Web Token?
![](https://miro.medium.com/max/1400/1*WrMX8PcUWaRwF00deECtzQ.png)
- JSON Web Token (`JWT`) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object.
- This information can be verified and trusted because it is digitally signed.
- JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using `RSA` or `ECDSA`.
- Although JWTs can be encrypted to also provide secrecy between parties, we will focus on signed tokens.
- Signed tokens can verify the integrity of the claims contained within it, while encrypted tokens hide those claims from other parties.

## When should you use JSON Web Tokens?

- `Authorization`
  1. This is the most common scenario for using JWT.
  2.Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token.
  3. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.

- `Information Exchange`  - JSON Web Tokens are a good way of securely transmitting information between parties.
  1. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are.
  2. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.

## What is the JSON Web Token structure?

- In its compact form, JSON Web Tokens consist of three parts separated by dots (.), which are:
  1. Header
  2. Payload
  3. Signature

- Header

> The header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA.

- Payload

> The second part of the token is the payload, which contains the claims.

>Claims are statements about an entity (typically, the user) and additional data.

- `Signature`

> To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

- `Putting all together`

> The output is three Base64-URL strings separated by dots that can be easily passed in HTML and HTTP environments, while being more compact when compared to XML-based standards such as SAML.

## How do JSON Web Tokens work?

<br>

- In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned.
- Since tokens are credentials, great care must be taken to prevent security issues.
- Whenever the user wants to access a protected route or resource, the user agent should send the JWT, typically in the Authorization header using the `Bearer schema`.
- If the token is sent in the Authorization header, Cross-Origin Resource Sharing (CORS) won't be an issue as it doesn't use cookies.
- The application or client requests authorization to the authorization server. This is performed through one of the different authorization flows.
- When the authorization is granted, the authorization server returns an access token to the application.
- The application uses the access token to access a protected resource (like an API).
 


# DRF JWT Authentication
- The JWT is acquired by exchanging an username + password for an access token and an refresh token
- The access token is usually short-lived (expires in 5 min or so, can be customized though).
- The refresh token lives a little bit longer (expires in 24 hours, also customizable). It is comparable to an authentication session. After it expires, you need a full login with username + password again.
- It’s a security feature and also it’s because the JWT holds a little bit more information. If you look closely the example I gave above, you will see the token is composed by three parts `xxxxx.yyyyy.zzzzz`.
- Those are three distinctive parts that compose a JWT `header.payload.signature`.

## Installation & Setup

- settings.py

```py
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```

- urls.py

```py
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

## Usage

1. I will be using HTTPie to consume the API endpoints via the terminal. But you can also use cURL (readily available in many OS) to try things out locally.
2. Obtain Token
3. First step is to authenticate and obtain the token. The endpoint is /api/token/ and it only accepts POST requests. `http post http://127.0.0.1:8000/api/token/ username=vitor password=123`.
4. After that you are going to store both the access token and the refresh token on the client side, usually in the localStorage.
5. In order to access the protected views on the backend (i.e., the API endpoints that require authentication), you should include the access token in the header of all requests.

- Refresh Token

   - To get a new access token, you should use the refresh token endpoint `/api/token/refresh/` posting the refresh token:


## What’s The Point of The Refresh Token?
1. At first glance the refresh token may look pointless, but in fact it is necessary to make sure the user still have the correct permissions.
2. If your access token have a long expire time, it may take longer to update the information associated with the token.
3. That’s because the authentication check is done by cryptographic means, instead of querying the database and verifying the data.
4. So some information is sort of cached.


### References
[JSON Web Tokens](https://jwt.io/introduction/)
<br />

[DRF JWT Authentication](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)
<br />

[Django Runserver Is Not Your Production Server](https://vsupalov.com/django-runserver-in-production/)

