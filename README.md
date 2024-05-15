# node-typescript

## 1. Init Node
```
npm init -y
```

## 2. Install & Setup Typescript
```
npm install typescript ts-node @types/node --save-dev
npm install tsup --save-dev
```
## 3. Install Express
```
npm install express
npm install @types/express --save-dev
```

## 4. Add tsconfig.json
```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "rootDir": "./src",
    "outDir": "./dist",
    "esModuleInterop": true,
    "strict": true,
    "skipLibCheck": true
  },
   "include": ["src/**/*"]
}
```

## 5. Create `tsup.config.ts`
```javascript
import { defineConfig } from 'tsup';

export default defineConfig({
  entry: ['src/server.ts'],
  format: ['cjs'],
  dts: false,
  clean: true,
  target: 'es6',
  outDir: 'dist',
});

```

## 6. Update `package.json` scripts section
```json
"scripts": {
  "build": "tsup",
  "start": "node dist/server.js",
  "dev": "tsup --watch"
}

```

## 7. Build and Run the Server
Build the TypeScript code using tsup:
```bash
npm run build
```
Run the compiled JavaScript code:

```bash
npm start
```

## 8. Development Mode
Run the server in development mode with tsup watching for changes:

```bash
npm run dev
```

