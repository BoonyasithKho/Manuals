React

- Software Installation
Node.js https://nodejs.org
Visual Studio Code https://code.visualstudio.com/

เริ่มต้นเขียน React
สร้างโปรเจค
npm create vite@latest
config Project name -> React -> Javascript
cd Project name
npm i
npm run dev <-- for check build

In vite.config.js
add server in defineConfig for change port

export default defineConfig({
  server: {port:3000},
  plugins: [react()],
})

