# :wave: Welcome to React Manual's

<detail><summary>What is React?</summary>
<hr>

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

</detail>

<details><summary>Install Node.js</summary>
<hr>
 
   - NodeJS Cross Platform Runtime Environment เป็นชุดเครื่องมือในการแปลคำสั่งของ JavaScript ทำให้สามารถไปรันใน OS ได้ โดยไม่ขึ้นกับ Web Browser เพียงอย่างเดียว
   - Javascript คือ ภาษาคอมพิวเตอร์ที่ใช้ในการพัฒนาเว็บร่วมกับ HTML เพื่อให้เว็บมีลักษณะแบบไดนามิก ตอบสนองกับผู้ใช้งาน
   - Node.js ถูกสร้างขึ้นมาเพื่อทำงานฝั่ง Server เป็นหลัก
   - ผู้พัฒนาสามารถควบคุมการทำงานของเว็บ ทั้งฝั่ง Frontend และ Backend ได้โดยใช้ JavaScript เพียงภาษาเดียว
   - Frontend คือ การพัฒนาส่วนระบบหน้าบ้าน (UI : User Interface หรือ หน้าตาของแอพพลิเคชั่น) โดยผู้ใช้งานสามารถมองเห็น และโต้ตอบผ่าน Web Browser
   - Backend คือ การพัฒนาโปรแกรมหลังบ้าน หรือการทำงานเบื้องหลังในแอพ โดยผู้ใช้งานไม่สามารถมีส่วนร่วมหรือโต้ตอบได้
   - Get Visual Studio Code in https://code.visualstudio.com/
   - Get the Node.js in https://nodejs.org/en (LST version is recommended)
   - After installed Node.js, you can use node and npm (Node Package Manager) which check it by 
      ```shell
          node -v
          npm -v
      ```
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

 








