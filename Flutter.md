# :wave: Welcome to Flutter Manual's "Introduction to Flutter"

<details><summary>What is Flutter?</summary>
<hr>
  
## What is Flutter?
 - **Flutter** เป็น Framework ในการพัฒนา Mobile Application พัฒนาและสนับสนุนโดย Google สามารถพัฒนา app แบบ cross-platform โดยสามารถสร้างและใช้งานได้ใน iOS, Android, พร้อมกับ Desktop และใน Website Flutter ไม่ได้ compiled โดยตรงไปที่ Android หรือ iOS เลย แอพจะเปิดขึ้นได้ด้วยการทำงานร่วมกันของ rendering engine สร้างจาก C++ และ ใช้ Flutter Design UI ที่สร้างจาก Dart
 - **Tools**
   - [pub.dev](https://pub.dev/) : The official package repository for Dart and Flutter apps.
   - [Icon](https://fonts.google.com/icons) : Material Symbols
 - **Create Project**
    1. Open VS Code.
    2. Invoke View > Command Palette.
    3. Type “flutter”, and select the Flutter: New Project.
    4. Select Application.
    5. Create or select the parent directory for the new project folder.
    6. Enter a project name, ``training`` and press Enter. Note! The name should be all lowercase, with underscores to separate words (my_first_app).
    7. Wait for project creation to complete and the main.dart file to appear.
 - **Run the app**
    1. Locate the VS Code status bar. Select a device from the Device Selector area.
    2. Invoke Run > Start Debugging or press F5
    3. Wait for the app to launch—progress is printed in the Debug Console view.
    4. After the app build completes, you’ll see the starter app on your device.
    5. Change the string 
       ``You have `pushed` the button this many times``
      to
       ``You have `clicked` the button this many times``
    6. Save your changes.
    7. Emulator will show first Project of flutter for press '+' to increase counter result.
    8. Structure of Project
  
        📁 folder ``lib`` เก็บไฟล์ที่แยกหน้าแอพต่าง ๆ ที่นามสกุล .dart ซึ่งการทำงานบนหน้าจอต่าง ๆ จะอยู่ในโฟลเดอร์นี้
  
        📁 folder ``android``, ``ios`` ใช้สำหรับการเก็บโปรเจคของ Application แต่ละระบบ เมื่อทำการรันจะมีการเก็บลงตามระบบปฏิบัติการที่รัน ซึ่งสามารถทำการแก้ไขในแต่ละระบบปฏิบัติการ เช่น ถ้าหากเปลี่ยนชื่อ App ใน Android จะเปลี่ยนได้เฉพาะใน Android แต่ไม่ได้เปลี่ยนใน iOS ดังนั้น ชื่อแอพใน 2 ระบบปฏิบัติการจะไม่เหมือนกัน หากต้องการให้เหมือนกันต้องเปลี่ยนทั้ง 2 โฟลเดอร์
          - ``android`` This folder contains the Android-specific configuration and code for your Flutter project. It includes the AndroidManifest.xml file, build.gradle files, and other resources required for building and running your app on Android devices.
          - ``ios`` This folder contains the iOS-specific configuration and code for your Flutter project. It includes the Info.plist file, build settings files, and other resources required for building and running your app on iOS devices.
  
        📁 folder ``assets`` This folder contains any static assets, such as images or fonts, that are required by your app.
  
        🗄️ file ``pubspec.yaml`` ใช้สำหรับการตั้งค่าต่าง ๆ ให้กับโปรเจคหรือการเรียกใช้งานไลบราลีต่าง ๆ การประกาศไลบราลี ไอคอน ต้องทำการตั้งค่าในไฟล์นี้
  
        🗄️ file ``README.md`` This file provides information about your Flutter project, such as how to install and run it.

 - **First Project with Flutter**
    1. We've created Demo project with Material App. Material App's built which has Statefulwidget class. It has scafold widget is home of material app.
    2. In MyHomePage (Stateful widget) has incrementCouter function for set value of counter.
    3. In Scaffold Widget has AppBar and Body. Body has center widget with column of Text and counter value.
    4. In body, FloatactionButton with onpressed 'incrementCouter' and Icon widget to child.
     ```dart
     import 'package:flutter/material.dart';

     void main() {
       runApp(const MyApp());
     }

     class MyApp extends StatelessWidget {
       const MyApp({super.key});

       // This widget is the root of your application.
       @override
       Widget build(BuildContext context) {
         return MaterialApp(
           title: 'Flutter Demo',
           theme: ThemeData(
             // This is the theme of your application.
             //
             // Try running your application with "flutter run". You'll see the
             // application has a blue toolbar. Then, without quitting the app, try
             // changing the primarySwatch below to Colors.green and then invoke
             // "hot reload" (press "r" in the console where you ran "flutter run",
             // or simply save your changes to "hot reload" in a Flutter IDE).
             // Notice that the counter didn't reset back to zero; the application
             // is not restarted.
             primarySwatch: Colors.blue,
           ),
           home: const MyHomePage(title: 'Flutter Demo Home Page'),
         );
       }
     }

     class MyHomePage extends StatefulWidget {
       const MyHomePage({super.key, required this.title});

       // This widget is the home page of your application. It is stateful, meaning
       // that it has a State object (defined below) that contains fields that affect
       // how it looks.

       // This class is the configuration for the state. It holds the values (in this
       // case the title) provided by the parent (in this case the App widget) and
       // used by the build method of the State. Fields in a Widget subclass are
       // always marked "final".

       final String title;

       @override
       State<MyHomePage> createState() => _MyHomePageState();
     }

     class _MyHomePageState extends State<MyHomePage> {
       int _counter = 0;

       void _incrementCounter() {
         setState(() {
           // This call to setState tells the Flutter framework that something has
           // changed in this State, which causes it to rerun the build method below
           // so that the display can reflect the updated values. If we changed
           // _counter without calling setState(), then the build method would not be
           // called again, and so nothing would appear to happen.
           _counter++;
         });
       }

       @override
       Widget build(BuildContext context) {
         // This method is rerun every time setState is called, for instance as done
         // by the _incrementCounter method above.
         //
         // The Flutter framework has been optimized to make rerunning build methods
         // fast, so that you can just rebuild anything that needs updating rather
         // than having to individually change instances of widgets.
         return Scaffold(
           appBar: AppBar(
             // Here we take the value from the MyHomePage object that was created by
             // the App.build method, and use it to set our appbar title.
             title: Text(widget.title),
           ),
           body: Center(
             // Center is a layout widget. It takes a single child and positions it
             // in the middle of the parent.
             child: Column(
               // Column is also a layout widget. It takes a list of children and
               // arranges them vertically. By default, it sizes itself to fit its
               // children horizontally, and tries to be as tall as its parent.
               //
               // Invoke "debug painting" (press "p" in the console, choose the
               // "Toggle Debug Paint" action from the Flutter Inspector in Android
               // Studio, or the "Toggle Debug Paint" command in Visual Studio Code)
               // to see the wireframe for each widget.
               //
               // Column has various properties to control how it sizes itself and
               // how it positions its children. Here we use mainAxisAlignment to
               // center the children vertically; the main axis here is the vertical
               // axis because Columns are vertical (the cross axis would be
               // horizontal).
               mainAxisAlignment: MainAxisAlignment.center,
               children: <Widget>[
                 const Text(
                   'You have pushed the button this many times:',
                 ),
                 Text(
                   '$_counter',
                   style: Theme.of(context).textTheme.headlineMedium,
                 ),
               ],
             ),
           ),
           floatingActionButton: FloatingActionButton(
             onPressed: _incrementCounter,
             tooltip: 'Increment',
             child: const Icon(Icons.add),
           ), // This trailing comma makes auto-formatting nicer for build methods.
         );
       }
     }
     ```
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
<details><summary>Widgets and Layouts</summary>
<hr>

## ▶️ Widget
 - **Widget** คือ ส่วนที่ถูกใช้สร้างเป็นหน้าตาของ App หรือ User Interface (UI) โดยนำมาประกอบเรียงกันเป็นลำดับขั้นขึ้นเป็นโครงสร้าง แต่ละ widget จะถูกวางซ้อนอยู่ภายใน Parent widget และได้รับการส่งต่อสืบทอดคุณสมบัติ (Properties) ต่างๆ จาก Parent อีกที แม้กระทั้ง application object ก็ถือเป็น widget ซึ่งเราเรียกว่า root widget 
 - **Flutter** จะมองทุกอย่างเกือบทั้งหมดเป็น widget มี ``MaterialApp`` เป็น root widget หรือ Widget หลัก ที่ทำหน้าที่กำหนดส่วนต่าง ๆ ของแอพ 
 - Widget แต่ละตัวจะมีส่วนที่เรียกว่า Properties สำหรับกำหนดคุณสมบัติให้กับ Widget นั้น ๆ ซึ่ง Widget แต่ละตัวก็มี Properties ที่หลากหลายให้เราใช้งานแตกต่างกันออกไป 
 - Widget สามารถจำแนกตามการใช้งาน ได้ดังนี้
    - ใช้กำหนดโครงสร้าง (Structural Element) เช่น ปุ่ม button หรือ menu
    - ใช้กำหนดลักษณะ หรือรูปแบบ (Stylistic Element) เข่น font หรือ color
    - ใช้จัดวาง และกำหนดมุมมองเลเอาท์ (Aspect of Layout) เช่น padding หรือ alignment

## ▶️ Layouts
 - **Layouts in Flutter**
  - Row และ Column -> Widget สำหรับการจัด Layout ที่ใช้บ่อยที่สุดในการกำหนดตำแหน่ง widget โดย Row Widget ใช้ในการแสดงผลในแนวนอน ส่วน Column Widget ใช้ในการแสดงผลในแนวตั้ง
    - แต่ละ Row และ Column มี child widget ได้หลายตัว
    - สำหรับจัดการ Layout ของหน้าแอพ แบบ Row เป็นการจัดเรียง Widget แบบซ้าย-ขวา ส่วน Column เป็นการจัดเรียงแบบบน-ล่าง ตามรูป
    <p align="center">
      <img src="https://docs.flutter.dev/assets/images/docs/ui/layout/pavlova-diagram.png"> 
    </p>
    
    - Aligning widgets ของ Row และ Column ตามภาพ
    <p align="center">
      <img src="https://docs.flutter.dev/assets/images/docs/ui/layout/row-diagram.png"> 
 
      <img src="https://docs.flutter.dev/assets/images/docs/ui/layout/column-diagram.png"> 
    </p>
    
    - หากมีการแสดงผลมากเกินขนาดของหน้าจอต้องเปลี่ยน Row หรือ Column ให้เป็น ListView เพื่อให้สามารถทำการ Scroll ดูข้อมูลได้
     ```dart
      scrollDirection: Axis.horizontal  // เลื่อนในแนวนอน
      scrollDirection: Axis.vertical,   // เลื่อนในแนวตั้ง
     ```
  - Wrap -> Widget สำหรับการจัด Layout เมื่อมีการแสดงผลที่เกินขอบเขตการแสดงผลของหน้าจอ โดยจะทำการจัดเรียง Widget ให้มีจำนวนข้อมูลที่พอดีกับขอบเขตหน้าจอ คล้ายกับการทำ Row และ Column รวมกัน
  - Container -> Widget ทำหน้าที่เป็นพื้นที่สำหรับการรวม Widget ต่างๆ เอาไว้ (กล่องใส่ของ) มี Widget ภายในสามารถแบ่งออกเป็น Layer เรียงลำดับที่อยู่ของ Properties จากด้านนอกเข้าสู่ด้านในจะเป็น Margin > Border > Padding > Content ได้แบบนี้
    <p align="center">
      <img src="https://toupawa.com/content/images/2021/02/margin-padding-border-9616dd0d7af45b95e6fcface25cd933b6b4a0fda51c1ab1bb9287bc8ed92c356.png">
    </p>
    
    - มี Properties ที่ชื่อ child ซึ่งสามารถบรรจุ Widget ได้หลายชนิด เช่น Row, Column, Image หรือว่าเป็น Container เอง ตัวใดตัวหนึ่งได้เพียงตัวเดียว
      <p align="center">
        <img src="https://docs.flutter.dev/assets/images/docs/ui/layout/sample-flutter-layout.png"> 
      </p>
    - ใช้ BoxDecoration สำหรับกำหนดรูปร่างของ Container เช่น สี ลักษณะรูปร่างของ Container
      ```dart
      Container(
        decoration: BoxDecoration(
          color: Colors.green,
          borderRadius: BorderRadius.circular(40),
        ),
        height: 50,
      ),
      ```
    - ใช้ Padding กำหนดระยะห่างของ Widget ออกจากขอบของ Layout
      ```dart
      Padding(
          padding: const EdgeInsets.all(8.0),
          child: Column(...),
      ),
      ```
    - ใช้ margin กำหนดระยะห่างของ Widget ออกจากขอบของหน้าจอแสดงผล
  - Stack -> สร้างลำดับการซ้อนทับของ Layout เวลาใช้งานให้มองภาพ 2D ให้เป็น 3D แล้วเรียบเรียงด้านหน้า-ด้านหลังของ Widget นั้น
  - ListView −> แสดงผล children widget เป็นแบบ list เมื่อมีการแสดงผลเกินพื้นที่หน้าจอสามารถทำการเลื่อนหน้าจอหรือ Scroll Down ได้
  - GridView −> แสดงผล children widget เป็นแบบ gallery
  - Expanded −> ใช้สำหรับการขยายความสูง children widget เพื่อให้เต็มพื้นที่การแสดงผล ผ่าน flex Properties
  - Table −> แสดงผลข้อมูลในรูปแบบตาราง
  - Flow −> แสดงผลข้อมูลในรูปแบบคลิกเพื่อแสดงข้อมูล
  - SizedBox -> ใช้สำหรับการกำหนดขนาดการแสดงผลของ Widget ที่อยู่ภายใน จะคล้ายกับการใช้งาน Container แต่จะกิน RAM น้อยกว่า แต่จะสามารถกำหนดได้เฉพาะความกว้าง ความยาวเท่านั้น กำหนดค่าอื่น ๆ ไม่ได้
  - Widget อื่น ๆ สามารถศึกษาเพิ่มเติมได้ที่ https://docs.flutter.dev/reference/widgets เช่น
    - Image Widget ที่เกี่ยวข้องกับรูปภาพ
      - Image.asset() ภาพจาก Package เดียวกับ App
      - Image.file() ภาพจาก การถ่ายรูปหรือดึงรูปภาพจากคลังภาพ
      - Image.memort() ภาพจาก ภาพที่มีการเข้ารหัส base64 ซึ่งเป็นในรูปแบบตัวอัีกษร การใช้งานต้องแปลงอักษรเหล่านี้ให้เป็นรูปภาพ
      - Image.network() ภาพจาก แหล่งภาพ online
    - Text Widget เกี่ยวข้องกับการใช้ตัวอักษร
    - Card Widget แสดงผลแบบการ์ด มีการกำหนด Attribution ที่ชื่อว่า elevation ในการกำหนดเงาให้การ์ด

## ▶️ State Widget
 - Stateless Widget เป็น Widget ที่ไม่มีการเปลี่ยนแปลงตัวเอง การแสดงผลจะมีลักษณะคงที่ไม่เปลี่ยนแปลง
 - Stateful Widget เป็น Widget ที่มีการเปลี่ยนแปลงของ state โดยจะมีการใช้งานคำสั่ง setState() เพื่อกำหนดการเปลี่ยนแปลง เป็นการบอกให้ flutter รู้ว่ามีบางอย่างเปลี่ยนแปลงเกิดขึ้นกับ State และ App ต้องทำการ rerun หรือทำคำสั่ง build() ใหม่ จึงได้รับผลจากการเปลี่ยนแปลงที่เกิดขึ้น
 - State Management : การจัดการ State ในหลาย ๆ หน้า มี 2 ส่วน คือ
    Provider : ดูแลและจัดการข้อมูลแล้วนำไปส่งให้ Consumer
    Consumer : นำข้อมูลที่ได้จาก Provider ไปสร้างหรือแสดงผลใน หน้าแอพหรือ widget ต้องทำการติดตั้ง package เพิ่มเติม คือ provider

## ▶️ Scaffold Widget
 - Scaffold คือ Widget หน้าต่างสำเร็จรูปสำหรับจัดการ Layout หรือโครงสร้างของหน้าแอป (มีการคำนวณระยะห่างของแอปกับหน้าจอ Emulator ให้อัตโนมัติ)
 - AppBar, which is a horizontal bar typically shown at the top of an app using the appBar property.
 - Body, The primary content of the scaffold.
 - FloatingActionButton ปุ่มที่มีลักษณะการแสดงผลแบบลอย ๆ ในมุมล่างขวามือ การใช้ปุ่มสามารถใส่ icon ได้ ด้วยการนำใส่ไปใน child:icon
   ```dart
   floatingActionButton: FloatingActionButton(
          onPressed: () {},
          child: Icon(Icons.add),
   )
   ```
   หากต้องการให้มีการเปลี่ยน State หลังจากการกด floattingButton ให้มีการกำหนดการเปลี่ยน state ใน onPressed
   ```dart
   ....
       onPressed: (){
         setState(() {
           number++;
         )};
       },
   ```
   สามารถทำการแยก setState() ออกเป็นฟังก์ชันแยกได้ เพื่อให้สะดวกต่อการแก้ไข
 - BottomNavigationBar, which is a horizontal array of buttons typically shown along the bottom of the app using the bottomNavigationBar property.
  
</details>
