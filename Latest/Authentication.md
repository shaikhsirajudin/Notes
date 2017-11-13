
# JSON Web Token (JWT)


A JSON Web Token (JWT) is a JSON object that is defined in RFC 7519 as a safe way to represent a set of information between two parties. The token is composed of a header, a payload, and a signature.

![how JWT works](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/jwt.png)

The user first signs into the authentication server using the authentication server’s login system (e.g. username and password, Facebook login, Google login, etc). The authentication server then creates the JWT and sends it to the user. When the user makes API calls to the application, the user passes the JWT along with the API call. In this setup, the application server would be configured to verify that the incoming JWT are created by the authentication server (the verification process will be explained in more detail later). So, when the user makes API calls with the attached JWT, the application can use the JWT to verify that the API call is coming from an authenticated user.