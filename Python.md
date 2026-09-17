- Python Virtual Environment (venv) คือ การจำลองสภาพแวดล้อม Python แยกต่างหากสำหรับแต่ละโปรเจกต์ ช่วยให้เราเก็บไลบรารีและแพ็กเกจไว้ใน "กล่อง" ของโปรเจกต์นั้น ๆ โดยไม่ไปปะปนกับเครื่องหลักหรือโปรเจกต์อื่น

  > สร้างและเข้าไปในโฟลเดอร์โปรเจกต์
    ```
      mkdir my_project
      cd my_project
    ```

  > สร้าง venv
    ```
    python3 -m venv env
    ```

  > เปิดใช้งาน (Activate) venv
    ```
    source env/bin/activate
    ```

  > ปิดการใช้งาน (Deactivate)
    ```
    deactivate
    ```

- ขั้นตอนการติดตั้งและบันทึกแพ็กเกจ (หลังจาก Activate venv แล้ว)

  > วิธีติดตั้งแพ็กเกจด้วย pip
  ```
  pip install pandas
  ```

  > วิธีบันทึกแพ็กเกจลงไฟล์ requirements.txt

  ```
  pip freeze > requirements.txt
  ```

  > วิธีติดตั้งแพ็กเกจทั้งหมดจากไฟล์ requirements.txt (สำหรับย้ายเครื่องหรือแชร์ให้คนอื่น)
  ```
  pip install -r requirements.txt
  ```

- วิธีเชื่อมต่อ venv เข้ากับ VS Code
  > กดปุ่ม Cmd + Shift + P บนคีย์บอร์ดพร้อมกันเพื่อเปิด Command Palette
  > พิมพ์คำว่า Python: Select Interpreter แล้วกด Enter
  > เลือกตัวเลือกที่มีคำว่า ('env': venv) หรือ (.venv) นำหน้า

- 
