# Repetiore-GraphQL

Update User Profile
Update the profile for a specific user account.

PUT /account/{userId}/profile

Headers
AuthSessionId - Identifier for current session
AuthSessionSecret - Secret for current session
Parameters
userId - Identifier for current user
Body
username - Username to update to
email - E-mail address to update to
Response
userId - Identifier for the user
Errors
ErrorCode1 - Caused by missing identifier
ErrorCode2 - Username was not given
ErrorCode3 - Server exploded
Example Request
GET /account/1692/profile

{
username: "NewUsername",
email: "Email@Email.com"
}
Example Response
200 OK

{
userId: 1692
}
