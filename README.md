# Missing dependencies in generated `package-lock.json` file

## Steps to reproduce

- checkout the code
- `cd nx-missing-deps-in-build`
- install deps: `npm i`
- build the code: `npx nx run backend:build`
- install dependencies using generated `package.json` and `package-lock.json`: `cd dist/apps/backend && npm ci`

You will get:
```text
npm ERR! code EUSAGE
npm ERR!
npm ERR! `npm ci` can only install packages when your package.json and package-lock.json or npm-shrinkwrap.json are in sync. Please update your lock file with `npm install` before continuing.
npm ERR!
npm ERR! Missing: string-width-cjs@4.2.3 from lock file
npm ERR! Missing: strip-ansi-cjs@6.0.1 from lock file
npm ERR! Missing: wrap-ansi-cjs@7.0.0 from lock file
```
