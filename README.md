# rune-mediamtx-metadata

Rune product instructions metadata for MediaMTX.

The integration API is expected to supply `CredentialEmail` and `CredentialPassword` components before rendering.

### Workflow

1. Static JSON generated by Rune at GitHub Action and saved as an artifact
2. Integration API build process fetches the JSON artifact from GitHub artifact
3. Integration API appends it's own components manually in the static JSON
4. Final JSON returned to the browser app
5. Browser app renders the content

### `UserCredentialDetails`

```json
[
   ...rune JSON...
  {
    "name": "CredentialEmail",
    "type": "Component"
    "body": "foo@example.fi"
  ],
  {
    "name": "CredentialPassword",
    "type": "Component"
    "body": "!secret!"
  ],
]
```
