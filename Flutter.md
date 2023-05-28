# :wave: Welcome to Flutter Manual's "Introduction to Flutter"

<details><summary>What is Flutter?</summary>
<hr>
  
## What is Flutter?
 - **Flutter** เป็น Framework ในการพัฒนา Mobile Application พัฒนาและสนับสนุนโดย Google สามารถพัฒนา app แบบ cross-platform โดยสามารถสร้างและใช้งานได้ใน iOS, Android, พร้อมกับ Desktop และใน Website Flutter ไม่ได้ compiled โดยตรงไปที่ Android หรือ iOS เลย แอพจะเปิดขึ้นได้ด้วยการทำงานร่วมกันของ rendering engine สร้างจาก C++ และ ใช้ Flutter Design UI ที่สร้างจาก Dart
 - **Tools**
   - [pub.dev](https://pub.dev/) : The official package repository for Dart and Flutter apps.
   - [Icon](https://fonts.google.com/icons) : Material Symbols
</details>
<details><summary>Setup Flutter</summary>
<hr>
  
  ### 1. Install Flutter SDK
   - Get the Flutter SDK at: https://docs.flutter.dev/get-started/install/macos
   - If you setup in Mac Silicon, you must to install Rosetta
  
      ```shell  
      sudo softwareupdate --install-rosetta --agree-to-license
      ```
   - Extract the file in the desired location, for example:

      ```shell
      cd ~/Flutter
      unzip ~/Downloads/flutter_macos_3.3.2-stable.zip
      ```
   - Add the flutter tool to your path with 'pwd => path of flutter':
  
     ```shell
     vim .zshrc
     Press 'I'
        export PATH=/Users/username/Documents/Flutter/ENV/flutter/bin:$PATH
     Press ESC
     Type ':wq!'
     ```
     ```shell
     export PATH="$PATH:/Users/username/Documents/Flutter/ENV/flutter/bin"
     ```
   - Run Flutter doctor:
  
     ```shell
     flutter doctor
     ```
  ### 2. Install Xcode
   - Get the Xcode at: https://developer.apple.com/xcode/.
   - Configure the Xcode command-line tools to use the newly-installed version of Xcode by running the following from the command line:
  
     ```shell
     sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
     sudo xcodebuild -runFirstLaunch
     ```
   - Make sure the Xcode license agreement is signed by either opening Xcode once and confirming or running with command line:
     ```shell
     sudo xcodebuild -license
     ```
   - Set up the iOS simulator. On your Mac, find the Simulator via Spotlight or by using the following command:
  
     ```shell
     open -a Simulator
     ```
   - Install cocoapods
  
     ```shell
     sudo gem install cocoapods
     ```
  ### 3. Install Android Studio
   - Download and install [Android Studio](https://developer.android.com/studio).
   - Set up the Android emulator follow command recommendation.
   - Agree to Android Licenses:
      
     ```shell
     flutter doctor --android-licenses
      ```
  ### 4. Install VS Code
   - Install extension : Flutter, Dart, Highlight Matching Tag, Lorem ipsum, Dart Data Class, GitHub Pull Requests and Issues

</details>
<details><summary>Dart(101)</summary>
<hr>
  
## ⌨️ What is Dart?
  
 - **Dart** คือ ภาษาโปรแกรมที่เอาไว้สำหรับสร้างแอพพลิเคชันบนแพลตฟอร์มที่หลากหลายโดยได้ทั้ง mobile, desktop, server และก็ web ภาษา Dart นี้ถูกสร้างโดย Google และปล่อยให้ใช้งานแบบ open source ทำให้ทุกคนสามารถนำไปใช้งานได้ฟรีๆ และการที่ Dart ถูกออกแบบมาให้ใช้งานได้ง่ายและมีประสิทธิภาพแบบภาษาเชิงวัตถุอื่นๆอย่าง Java C# C++ Dart เป็นภาษาเชิงวัตถุ (Object-oriented programming) ดังนั้งสิ่งที่ขาดไม่ได้เลยก็คือ class นั่นเอง โดยครั้งนี้เรามาลองดูตัวอย่างผ่านการสร้าง class Bicycle

   1️⃣ Define a Bicycle class
     ```dart
     class Bicycle {
       int cadence;
       int _speed = 0;
       int get speed => _speed;
       int gear;

       Bicycle(this.cadence, this.gear);

       void applyBrake(int decrement) {
         _speed -= decrement;
       }

       void speedUp(int increment) {
         _speed += increment;
       }

       @override
       String toString() => 'Bicycle: $_speed mph';
     }
     ```
     
   2️⃣ Main class
     ```dart
     void main() {
       var bike = Bicycle(2,1);
       print('Start : $bike');
       print('Cadence : ${bike.cadence}');
       print('Gear : ${bike.gear}');

       bike.speedUp(20);
       print('Speed after speedUp   : $bike');

       bike.applyBrake(8);
       print('Speed after applyBrake: $bike');
     }
     ```
     
   ☑️ Output
     ```
     Start : Bicycle: 0 km/h
     Cadence : 2
     Gear : 1
     Speed after speedUp   : Bicycle: 20 km/h
     Speed after applyBrake: Bicycle: 12 km/h
     ```
   ⏭️ จากโค้ดนี้จะเห็นว่า มีการประกาศคลาส Bicycle โดยมีตัวแปรที่อยู่ใสคลาสหรือ Attribute ด้วยกัน 3 ตัวคือ cadence (รอบขาในการปั่น), _speed (ความเร็ว), และ gear (เกียร์) ถ้าสังเกตจะเห็นว่าการประกาศคลาสนั้นไม่ต้องระบุ public, private หรือ protected เหมือนในภาษา Java โดยใน Dart นั้นทั้งหมดจะ public เป็นค่าเริ่มต้นอยู่แล้ว นอกจากนี้ยังมี Method ของการเพิ่มและลดความเร็วที่สามารถทำการเรียกใช้เพื่อปรับเปลี่ยนผลลัพธ์ให้กับจักรยานได้
  
## ⌨️ Variable
   - มาตรฐานการตั้งชื่อตัวแปร (Naming Convention)
     - Camel Case: สำหรับการตั้งชื่อตัวแปร โดยตัวแรกเป็นตัวพิมพ์เล็ก คั่นคำต่อไปด้วย ตัวอักษรพิมพ์ใหญ่ เช่น newProductPrice
     - Pascel Case: สำหรับการตั้งชื่อ Class โดยตัวแรกเป็นตัวพิมพ์ใหญ่คั่นคำต่อไปด้วย ตัวอักษรพิมพ์ใหญ่ เช่น MyUserName
     - Snake Case: สำหรับการตั้งชื่อ File or Folder โดยการใช้ตัวพิมพ์เล็ก คั่นคำต่อไปด้วย '_' เช่น number_of_client
   - File and Package name : ใช้การตั้งชื่อด้วยตัวอักษรตัวเล็กทั้งหมดไม่ต้องมี '_' คั่น

## ⌨️ Datatype
   - int : จำนวนเต็ม
   - double : ทศนิยม
   - num : ตัวเลขจำนวนเต็ม และทศนิยม
   - bool : true, false
   - string : ประโยค จะอยู่ใน " " หรือ ' ' (แนะนำให้ใช้แบบ single quote)
   - dynamic : ตัวแปรแบบเปลี่ยนชนิดได้ ซึ่งทุกตัวแปรสามารถเป็น null ได้ สามารถเปลี่ยนแปลง type ได้ตลอด
   - var : เป็นการประกาศชนิดตัวแปรด้วยโปรแกรม เมื่อมีการเลือกเป็น type ไหนแล้วจะเป็น type นั้นจนจบโปรแกรม
   - final : คล้าย var เปลี่ยน type ด้วยโปรแกรม แต่ไม่สามารถเปลี่ยนเป็นค่าอื่นได้ กรณีเป็น Reference/Object Data Types สามารถแก้ไขค่าได้ แต่ไม่สามารถกำหนดค่าให้ตัวแปรใหม่ได้
  
     ```dart
     // Primitive Data Types : int, double, boolean and string
     
     final String name = "NottDev";
     name = "NottDev Edit";  // can't set
     
     // Reference/Object Data Types : List, Map, Object
     
     final List<String> fruits = ['apple', 'orange', 'banana'];
     fruits.removeLast();  // ['apple', 'orange'];
     fruits = [];  // can't set
     ```
   - const : ตัวแปรที่มีกำหนดค่าได้ครั้งเดียว
  
     ```dart
     const Pi = 3.14;
     ```
 - Use => arrow functions.
 - Use {} multi-line functions.
   ฟังก์ชันที่มี return statement เดียวเท่านั้น เราก็สามารถเขียนย่อโดยใช้ Arrow Function ได้ Dart also supports a nice shorthand syntax for any function that has only one expression.
   ```dart
   int add(int x, int y) {
    return x + y;
   }

   // สามารถเขียนย่อได้ว่า

   add(x, y) => x + y;
   ```
 - Use ``//`` for single-line comments and ``/* */`` for multi-line comments.
 - Use ``;`` at the end of statements.
  
</details>
