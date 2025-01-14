# gocloak-echo
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FNerzal%2Fgocloak-echo.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2FNerzal%2Fgocloak-echo?ref=badge_shield)

Keycloak handler &amp; middleware for echo

This project is still WiP and the interfaces might change pretty often

Use this together with the keycloak client [gocloak](https://github.com/Nerzal/gocloak)

```go
// AuthenticationHandler is used to authenticate with the api
type AuthenticationHandler interface {
	AuthenticateClient(Authenticate) (*gocloak.JWT, error)
	AuthenticateUser(Authenticate) (*gocloak.JWT, error)
	RefreshToken(Refresh) (*gocloak.JWT, error)
}
```

```go
// AuthenticationMiddleWare is used to validate the JWT
type AuthenticationMiddleWare interface {
	CheckToken(next echo.HandlerFunc) echo.HandlerFunc
	CheckScope(next echo.HandlerFunc) echo.HandlerFunc
}
```

## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FNerzal%2Fgocloak-echo.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2FNerzal%2Fgocloak-echo?ref=badge_large)