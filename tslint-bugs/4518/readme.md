### Bug Report

- __TSLint version__: 5.11.0
- __TypeScript version__: 2.9.2
- __Running TSLint via__:  CLI / (Visual Studio - does not show this error)

#### TypeScript code being linted
Multiple classes with a leading line that is empty. This line only contains line endings when analyzed (e.g. \r\n)
```ts

export class User {
    userName: string;
}
```

with `tslint.json` configuration:

```json
{
  "defaultSeverity": "error",
  "extends": "tslint:recommended",
  "jsRules": {},
  "rules": {
    "quotemark": [
      true,
      "single",
      "avoid-escape"
    ],
    "member-access": [
      true,
      "no-public"
    ],
    "object-literal-sort-keys": [
      false
    ],
    "object-literal-shorthand": [
      true,
      "never"
    ],
    "ordered-imports": [
      false
    ],
    "trailing-comma": [
      true,
      {
        "esSpecCompliant": true
      }
    ]
  },
  "rulesDirectory": [],
  "linterOptions": {
    "exclude": [
      "src/test.ts",
      "src/main.ts",
      "src/polyfills.ts"
    ]
  }
}
```

#### Actual behavior
Multiple results identical to the following

`ERROR: ClientApp/src/app/models/ActionItem.ts:1:1 - trailing whitespace`

#### Expected behavior
No results generated