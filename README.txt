STEPS to initialize React app with Typescript and SCSS
*******************************************************

//1. To initialize npm
npm init -y  

//2. To install React library
npm install react react-dom

//3. To install Typescript dependency
npm install --save-dev typescript @types/react @types/react-dom

//4. To Generate tsconfig.json
npx tsc --init

//5. Basic tsconfig.json
{
  "compilerOptions": {
    "target": "ESNext",
    "module": "ESNext",
    "jsx": "react-jsx",
    "moduleResolution": "Node",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  },
  "include": ["src"],
  "exclude": ["node_modules"]
}


//6. To Install Vite Plugin

npm install vite @vitejs/plugin-react

//7. Create vite.config.ts

import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';

export default defineConfig({
  base: '/',
  plugins: [react()],
  server: {
    port: 3000, // or your preferred port
  },
});


//8. Project structure
my-app/
│
├── src/
│   ├── components/
│   │   └── App.tsx
│   ├── styles/
│   │   ├── globals.scss
│   │   └── variables.scss
│   ├── main.tsx
│   └── index.html
│
├── tsconfig.json
├── package.json
└── vite.config.ts

//9. Create index.html in the root director

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>React App</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>


//10. main.tsx (src)

import React from 'react';
import ReactDOM from 'react-dom/client';
import './styles/global.scss'; // If using SCSS
import App from './App';

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);


//11. App.tsx (src)

import React from 'react';

const App = () => {
  return <h1>Hello, React with TypeScript and Vite!</h1>;
};

export default App;


//12. Add scripts to package.json

"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview"
}

//13. Install SCSS

npm install sass


//14. Start development server
npm run dev




