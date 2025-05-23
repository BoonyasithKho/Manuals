# :wave: Welcome to React Manual's

<details><summary>Do you Know...</summary>
<hr>

## What is Javascript?
 - Javascript คือ ภาษาคอมพิวเตอร์ที่ใช้ในการพัฒนาเว็บร่วมกับ HTML เพื่อให้เว็บมีลักษณะแบบไดนามิกและสามารถโต้ตอบกับผู้ใช้งานได้

## What is React?
 - React เป็นไลบรารี JavaScript ที่พัฒนาโดย Facebook เพื่อช่วยสร้าง User Interface (UI)
 - React เหมาะสำหรับการพัฒนาแอปพลิเคชันเว็บที่มีขอบเขตใหญ่หรือซับซ้อน โดยเฉพาะอย่างยิ่งเมื่อต้องการในการจัดการข้อมูลแบบ Real-time หรือการสร้าง UI ที่ตอบสนองต่อเหตุการณ์ต่าง ๆ อย่างรวดเร็ว
 - React จะใช้ JSX (JavaScript XML) เป็นส่วนหนึ่งของโค้ด ดังนั้นความเข้าใจใน HTML จะช่วยให้สามารถสร้างและจัดการ Element ใน React ได้อย่างเหมาะสม
 - React ไม่ได้รวม CSS (Cascading Style Sheets) เข้าไปในตัวเอง ดังนั้น การมีความเข้าใจใน CSS จะช่วยให้สามารถสร้างสไตล์และการจัดการกับสไตล์ของ Component ได้อย่างมีประสิทธิภาพ
 - React ใช้แนวคิดการสร้าง Component ที่เป็นส่วนประกอบของ UI และสามารถใช้ซ้ำได้ โดยแต่ละ Component สามารถเก็บสถานะ (state) และเมทอด (methods) ต่างๆ เพื่อการจัดการกับข้อมูลและการแสดงผล วิธีการจัดการสถานะของ Component ซึ่งมีหลายวิธี เช่น useState, useContext, Redux ฯลฯ การรู้จักและเลือกใช้วิธีการจัดการสถานะที่เหมาะสมกับโปรเจคจะช่วยให้การพัฒนาเป็นไปอย่างราบรื่นขึ้น
 - React เป็นเครื่องมือที่มีประสิทธิภาพสำหรับการพัฒนาเว็บแอปพลิเคชันที่ยืดหยุ่นและมีประสิทธิภาพ การใช้งาน React ร่วมกับไลบรารีและเครื่องมืออื่น ๆ จะช่วยให้การพัฒนาเป็นไปอย่างมีประสิทธิภาพ Library สำหรับใช้งานร่วมกับ React
   - Redux: สำหรับจัดการสถานะของแอปพลิเคชันขนาดใหญ่
   - React Router: สำหรับจัดการเส้นทางของแอปพลิเคชัน
   - Axios: สำหรับการทำ HTTP requests
   - Styled-components: สำหรับการสร้าง CSS ใน JavaScript
   - Material-UI หรือ Ant Design: สำหรับ component library ที่มีองค์ประกอบ UI พร้อมใช้งาน
   - [MUI](https://mui.com/) offers a comprehensive suite of free UI tools to help you ship new features faster. Start with Material UI, our fully-loaded component library, or bring your own design system to our production-ready components.

## What is Node.js?
   - Node.js เป็น Cross Platform Runtime Environment ที่ใช้ในการแปลคำสั่งของ JavaScript เพื่อให้รันใน OS ได้ โดยไม่จำเป็นต้องใช้กับ Web Browser เพียงอย่างเดียว
   - เริ่มแรก Node.js ถูกสร้างขึ้นมาเพื่อทำงานฝั่ง Server เป็นหลัก แต่ต่อมาก็พัฒนาให้สามารถควบคุมการทำงานของเว็บ ทั้งฝั่ง Frontend และ Backend ได้โดยใช้ JavaScript เพียงภาษาเดียว

## Difference Between NodeJS vs ReactJS
   - React และ NodeJS เป็นเทคโนโลยี JavaScript ที่ได้รับความนิยม แต่ก็มีความแตกต่างกัน
   - ส่วนการทำงาน : React จะทำงานบนเบราว์เซอร์เพื่อจัดการและเรนเดอร์ส่วนประกอบ UI ในขณะที่ Node จะทำงานบนเซิร์ฟเวอร์เพื่อจัดการการทำงานด้านเซิร์ฟเวอร์และ backend logic
   - ส่วนการแสดงผล : React.js จะใช้ Virtual DOM เพื่อเพิ่มประสิทธิภาพการเรนเดอร์และการอัปเดต UI ในขณะที่ NodeJS จะไม่เรนเดอร์ UI แต่ใช้ร่วมกับเฟรมเวิร์ก เช่น Express.js เพื่อให้บริการหน้าเว็บแทน
   - การทำงานร่วมกันระหว่าง React และ Node.js จะสร้าง web application ที่เชื่อมโยงกันและตอบสนองได้ดี โดย React จะแสดงส่วนประกอบ UI ในส่วนหน้าบ้าน ขณะที่ Node.js จะทำหน้าที่จัดการการสื่อสารข้อมูลฝั่งเซิร์ฟเวอร์

## What is frontend/backend?
   - Frontend คือ การพัฒนาส่วนระบบหน้าบ้าน (UI : User Interface หรือ หน้าตาของแอพพลิเคชั่น) โดยผู้ใช้งานสามารถมองเห็น และโต้ตอบผ่าน Web Browser
   - Backend คือ การพัฒนาโปรแกรมหลังบ้าน หรือการทำงานเบื้องหลังในแอพ โดยผู้ใช้งานไม่สามารถมีส่วนร่วมหรือโต้ตอบได้
<hr>
</details>

<details><summary>Setup Node.js</summary>
<hr>
 
## Setup Node.js?
   - Get Visual Studio Code in https://code.visualstudio.com/
   - Get the Node.js in https://nodejs.org/en (LST version is recommended) and install
## Checking
   - After installed Node.js, you can use node and npm (Node Package Manager) which check it by 
      ```shell
          node -v
          npm -v
      ```
<hr>
</details>

<details><summary>เริ่มต้นเขียน React</summary>
<hr>

  ### 1. Create Project
   - Make Directory for workspace
   - If fullstack development, you can seperate folder in backend and frontend

     <details><summary>Frontend</summary>
       
       - Create Project of work with vite. Vite is build tool and development server for frontend application. It's easy and quick to start React Application from command:
          ```shell
          npm create vite@latest
          ```
       - Config for React by select
         ```shell
         Project Name : 'Name of your Project'
         Select a framework : React
         Select a variant : JavaScript
         ```
       - Open project created directory and type command:
         ```shell
         npm i
         ```
       - Build project for first check
         ```shell
         npm run dev
         ```
       - In vite.config.js add server in defineConfig for change port
         ```javascript
          export default defineConfig({
            server: {port:3000},
            plugins: [react()],
          })
         ```
     </details>
       
     <details><summary>Backend</summary>
       
       
     </details>

</details>

 








