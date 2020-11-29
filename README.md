# Barong

Barong is an authentication service for microservice architectures using JWT standard.
It's focused on security and rich KyC features.

Barong drastically reduce the time to build a new project, it takes care of the user flow:
- User registration
- Email verification
- User login
- Reset password
- Account 2FA protection
- Support documents upload/review to implement your own KyC flow

When a user login to Barong, he receives a cookie that is then used to keep track of his session.
Every request made to a microservice of the stack goes through AuthZ service which validates the session and add a JWT the the header.
A JWT is a signed json token containing basic user informations:
- UID
- email
- role
- KyC level
- state

Microservices verify the signature of the JWT to validate the authenticity of the received information.

This way you can focus on the core functionalities of your product and delegate the user management flow to Barong.

# Overview

It includes the following features:

- Registration of users
- Role based access control (RBAC)
- Embedded KyC process
- Integrated [KycAID KyC plugin](https://www.openware.com/sdk/docs/barong/kycaid)
- Mailing system: event based, support multi-language, secured by cryptographic signatures
- [Service accounts](https://www.openware.com/sdk/docs/barong/service-accounts)
- Focused on user privacy: sensitive informations are encrypted in database using vault, masks are applied on fields in user API endpoints
- UI to manage users and KyC process: [Tower](https://www.openware.com/sdk/changelogs/tower.html)

# Examples of use-cases

- Openware [crypto exchange software](https://www.openware.com) stack
- [OpenDAX](https://github.com/openware/opendax) docker compose
