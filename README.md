# Спринт 8. 

## Задание 1. Реализуйте PKCE. 

В файл [realm-export.json](keycloak%2Frealm-export.json) добавлен новый аттрибут:
```json
        "attributes": {
          "pkce.code.challenge.method": "S256"
        }
```

А так же во frontend приложении добавлена опция для `ReactKeycloakProvider`:
```ts
<ReactKeycloakProvider authClient={keycloak} initOptions={{pkceMethod: 'S256' }}>
```

