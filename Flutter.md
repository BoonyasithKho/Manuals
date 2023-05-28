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

## ▶️ Navigation Widget
- Navigator Widget คือ กลุ่มของ widget หรือ class ที่ใช้ร่วมกับ route ในการจัดการ widget ย่อย
- มีการจัดวางโครงสร้างแบบ stack ซึ่งเป็นการซ้อนทับตามลำดับจากล่างขึ้นบน โดยแผ่่นที่นำมาเรียงต่อกันคือ ส่วนของ Widget ย่อย แผ่นที่แสดงผลจะถูกแสดงซ้อนทับหน้าอื่น ๆ ไว้
- Operator ของ Stack มีสองตัวคือ
  - Push : เป็นการนำสมาชิกใหม่มาไว้บนสุดของ stack สามารถทำการรับส่งข้อมูลระหว่างกันได้
    ```dart
    Navigator.push(
      context, 
      MaterialPageRoute(
        builder: (
          BuildContext context) {
            return Text("Page 2");
    }));
    ```
  - Pop : เป็นการนำสมาชิกชั้นบนสุดออกจาก stack

      App: page1 -> page2 -> page3(pop)

      To

      App: page1 -> page2 

    <p align="center">
      <img src="https://itome.team/blog/2019/12/flutter-advent-calendar-day10/navigator_stack.png"> 
    </p>
  - PushNamed : เป็นการเรียก widget ย่อย เพื่อให้ไปหน้า route ที่ต้องการ ใช้ในกรณีที่มีจำนวนหน้าซับซ้อน เช่น สมมุติว่าผู้อ่านอยู่ page1 และต้องการเปิดหน้าใหม่ก็จะเจอ page2 พอผู้อ่านอยู่ page2 และต้องการเปิดหน้าใหม่ก็จะเจอ page3 จะเป็นยังงี้ไปเรื่อยๆ

      App: page1(pushNamed(page2)) -> page2(pushNamed(page3) -> page3
 
  - pushReplacementNamed : เป็นการแทนที่หน้าที่เราอยู่ ณ ปัจจุบัน สมมุติว่าผู้อ่านอยู่ page1 เมื่อกด pushReplacementNamed จะมี page อื่นมาแทน โดยไม่สามารถ pop กลับไปก่อนหน้าได้

      App: page1(pushNamed(page2) <- page2

      To

      App: page2
  - popAndPushNamed : เหมือน PushReplacementNamed แต่ข้อแตกต่างคือเรื่องการแสดงผล animation flutter
    - pushReplacementNamed : Enter animation
    - popAndPushNamed : Exit animation
  - pushNamedAndRemoveUntil ใช้ในกรณีที่เราต้องการ push หน้าใหม่ขึ้นมาแล้วทำการลบหน้าที่ซ้อนๆ กันอยู่ด้านล่างของ Stack ทิ้งออกไป เวลากลับจะได้กลับไปหน้าที่ต้องการได้เลย มีลูกเล่นอยู่ 2 แบบคือ 
    - เคลียร์ทุกค่าที่อยู่ใน stack แล้วทำการเปิด page ที่ต้องการ เช่น page4
    ```dart
    Navigator.pushNamedAndRemoveUntil(context, '/page4', (Route<dynamic> route) => false);
    ```

      APP: page1 -> page2 -> page3(pushNamedAndRemoveUntil(page4) -> page4

      To

      App: page4
    - เคลียร์ค่าใน stack ตามที่ต้องการ เช่น ต้องการเปิด page4 แล้วเคลียร์ page2,3
    ```dart
    Navigator.pushNamedAndRemoveUntil(context, '/page4', ModalRoute.withName('/page1'));
    ```

      APP: page1 -> page2 -> page3(pushNamedAndRemoveUntil(page4),ModalRoute.withName(page1) -> page4

      To

      App: page1 -> page4
  - PopUntil : จะเป็นการ pop จนกว่าจะถึง page ที่ต้องการ เช่น pageA
    ```dart
    Navigator.of(context).popUntil(PageA);
    ```

      APP: pageA -> pageB -> pageC

      To

      APP: pageA
    <p align="center">
      <img src="https://itome.team/blog/2019/12/flutter-advent-calendar-day10/navigator_pop_until.png"> 
    </p>
  - SystemNavigator.pop() => ปิดแอพเพื่อออกไปหน้า Menu เครื่อง

</details>
  
<details><summary>API</summary>
<hr>

## ⤵️ API  
- API คือ วิธีเรียกใช้งานโปรแกรม เป็นรูปแบบโปรแกรมกับโปรแกรม เพื่อใช้สำหรับการแลกเปลี่ยนข้อมูลระหว่างกัน ผ่านทาง Internet โดย
    โปรแกรมต้นทาง จะเรียกว่า Server คอยเปิดและให้บริการข้อมูล
    โปรแกรมปลายทาง จะเรียกว่า Client สำหรับเรียกใช้บริการจาก Server
  - การทำงานของ API
    - ผู้ให้บริการจะเป็นคนกำหนดกฏการเรียกใช้งานข้อมูล ซึ่งก่อนทำการเรียกใช้งาน API จะต้องรู้ว่าใช้คำสั่งอะไร (1 คำสั่ง = 1 API) 
    - Request การส่งคำขอเพื่อใช้บริการ API
    - Response การตอบกลับข้อมูลตามคำขอที่ส่งไป (ได้หรือไม่ได้)
  - Open API คือ API ที่เปิดให้คนนอกสามารถเข้าถึงข้อมูลได้
  - Web API คือ การให้บริการข้อมูลผ่าน Website โดย HTTP ซึ่งอยู่ในรูปแบบ XML และ JSON ซึ่งข้อมูล (ภาพ,เสียง,ข้อมูลทางธุรกิจ) จะเรียกว่า Resource
    - HTTP Method คือ ตัวที่บ่งบอกการกระทำกับข้อมูล
      - Get Method สำหรับร้องขอข้อมูล
      - POST Method สำหรับสร้างข้อมูลใหม่
      - PUT Method สำหรับอัพเดทข้อมูล
      - DELETE Method สำหรับลบข้อมูล
    - การใช้งาน Web API ใน Flutter ต้องทำการติดตั้ง HTTP Package เพื่อรับ/ส่ง ข้อมูล
      - เรียกใช้งาน Web API ในส่วนของ initState() 
      - กรอก url ของ API ที่ต้องการ
      - ทำการทดสอบการผลแสดงข้อมูล ถ้าแสดงผลได้ปกติแปลว่าสามารถใช้งาน API นั้นได้ โดยข้อมูลที่เข้ามาถ้าอยู่ในรูปแบบ JSON ต้องทำการแปลงให้สามารถใช้งานใน dart ได้
        ```dart
        import 'package:http/http.dart' as http;  // ต้อง import package ก่อนการเรียกใช้งาน

         @override
         void initState() {
            super.initState();
            getExchangeRate();
         }
         Future<void> getExchangeRate() async {
            var url = "https://covid19.ddc.moph.go.th/api/Cases/today-cases-by-provinces";
            var response = await http.get(Uri.parse(url));
            print(response.body);
         }
         ```
       - แปลง JSON object ไปใช้ใน dart ด้วย https://app.quicktype.io/
  - API and Forward Port
    - Database on XAMPP (phpmyadmin)
    - API Provide with Postman
    - Forward Port with ngrok
       - start with Run ngrok.exe > type "ngrok http 80" for forward port 80
       - copy url at forward to emulator
       - Stop sharing a port on Ngrok with Run ngrok.exe > type "taskkill /f /im ngrok.exe"

  - More information for [Parse JSON in Dart/Flutter](https://codewithandrea.com/articles/parse-json-dart/)
## ⤵️ FutureBuilder
  - FutureBuilder ซึ่งเป็น async widgets
  - การทำงานของ Flutter มี 2 แบบ คือ
    - การทำงานแบบ Synchronous คือ การทำงานแบบตามลำดับ ต้องให้งานก่อนหน้าเสร็จก่อนถึงจะทำงานในขั้นตอนต่อไป
    - การทำงานแบบ Asynchronous หรือ Non-blocking คือ การทำงานที่สามารถสลับไปทำงานอื่นได้โดยไม่ต้องรอกัน ซึ่งต้องมีการพ่วงการใช้งานกับ Future
      - Future คือ การนำค่าที่เกิดขึ้นในอนาคตมาใช้งาน ซึ่งจะทำการเช็คข้อมูลที่เกิดขึ้นผ่าน State เช่น สมบูรณ์ (Complete), ไม่สมบูรณ์ (Incomplete) เป็นต้น เมื่อมีการทำงานแบบ Asynchronous จะมีการใช้งานร่วมกับคำสั่ง async และ await สำหรับรอให้ทำงานจนเสร็จ
        ```dart
        Future <return type> ชื่อ Future async {
            await .....;
        }
        ```
      - จำลองข้อมูลในอนาคตด้วย Future เช่น เราดึงข้อมูลผ่านเครือข่าย ก็จำเป็นจะต้องรอสักพักกว่าข้อมูลจะมา ก็เกิดเวลาที่ต้องรอขึ้น
      - เหตุผลที่ต้องรู้จักกับข้อมูล Future ก็เพราะว่า ตัว FutureBuilder widget ที่จะใช้งานจำเป็นต้องใช้ข้อมูล Future
      - รูปแบบการใช้งาน FutureBuilder
        ```dart
        FutureBuilder<String>( // กำหนดชนิดข้อมูล
          future: _calculation, // ข้อมูล Future, ฟังก์ชันที่ต้องการเรียกใช้ แบบ Future
          builder: (BuildContext context, AsyncSnapshot snapshot) { // สร้าง widget เมื่อได้ค่า snapshot ข้อมูลสุดท้าย
            if (snapshot.hasData) { // ถ้าได้ค่าข้อมูลสุดท้าย
              return Text('Completed');
            } else if (snapshot.hasError) { // ถ้ามี error
              return Text('${snapshot.error}');
            }
            return const CircularProgressIndicator(); // ค่าเริ่มต้น, แสดงตัว Loading. snapshot.connectionState == ConnectionState.waiting
          },
        ),
        ```
## ⤵️ การใช้งาน Http ดึงข้อมูลจาก Server มาแสดงใน Flutter
  - ติดตั้ง http package
  - กำหนดสิทธิ์การขอใช้งานเครือข่าย INTERNET สำหรับ Android : android > app > src > main > AndroidManifest.xml
    ```xml
    <manifest xmlns:android...>
      ...
      <uses-permission android:name="android.permission.INTERNET" />
      <application ...
    </manifest>
    ```
- จัดรูปแบบ Data Model ข้อมูลสำหรับรองรับข้อมูลจาก API
  - ศึกษาโครงสร้างของข้อมูลที่จะนำมาใช้
    ```json
    [
      {
        "userId": 1,
        "id": 1,
        "title": "sunt aut facere repellat provident occaeenderit",
        "body": "quia et suscipitnsuscipit recusatecto"
      }
    ]
    ```
  - จากรูปแบบข้างต้น เพื่อใช้งานก็ได้สามารถกำหนด Data Model สำหรับข้อมูลได้เป็นดังนี้ (โครงสร้างข้อมูล JSON String data ของเรามีด้วยกัน 4 ตัวคือ userID , id , title และ body เวลาสร้าง Data Model ไม่จำเป้นต้องใช้หมดทั้ง 4 ตัวก็ได้ อาจจะกำหนดแค่ id กับ title)
    ```dart
    class Article {
      final int userId;
      final int id;
      final String title;
      final String body;

      Article({
        required this.userId,
        required this.id,
        required this.title,
        required this.body,
      });

      // ส่วนของ name constructor ที่จะแปลง json string มาเป็น Article object
      factory Article.fromJson(Map<String, dynamic> json) {
        return Article(
          userId: json['userId'],
          id: json['id'],
          title: json['title'],
          body: json['body'],
        );
      }
    }
    ```
- กำหนดฟังก์ชันสำหรับดึงข้อมูล api ด้วย http package และการแปลงข้อมูล api ที่ได้มาในรูปแบบ JSON data เป็นในรูปแบบ List<Article> โดยใช้ฟังก์ชั่นของ Flutter มาช่วย
  ```dart
  Future getData() async { // สรัางฟังก์ชั่นดึงข้อมูล คืนค่ากลับมาเป็นข้อมูล Future
    var response = await http.get(Uri.parse([MyConstant.domain](http://27.254.170.14/api1))); // ทำการดึงข้อมูลจาก server ตาม url ที่กำหนด
    var jsonData = jsonDecode(response.body);
    List<APIData> apiData = [];
    for (var u in jsonData) {
      APIData _getData = APIData(u["id"].toInt(), u["geom"], u["descriptio"], DateTime.parse(u["time"]), u["copyright"], u["province"], u["stationnam"], u["rainfall_v"].toInt(), u["rainfall_u"], u["temperatur"].toInt(), u["temperat_1"], u["geojson"]);
      apiData.add(_getData);
    }
    return apiData; // return list of data
  }
  ```
- ฟังก์ชันทำการดึงข้อมูลให้ได้ข้อมูล JSON String data มาแล้วอ่านข้อมูลจากแต่ละ tag เพื่อนำมาใส่ใน _getData
- นำไปแสดงหรือใช้งานร่วมกับ FutureBuilder
- การใช้งาน ListView Widget
  - ListView Widget เป็น widget ที่ใช้ในการสร้างลิสรายการที่สามารถเลือนได้ โดยเรียงต่อกันเป็นแนว สามารถกำหนดลิสรายการเป็น widget ต่างๆ ส่วนใหญ่จะพบเห็นใช้บ่อยในการสร้างเป็นลิสรายการข้อความ  widget ยอ่ยหรือลิสรายการแต่ละรายการจะเรียงต่อหลังกันไปเรื่อยๆ ตามทิศทางการเลื่อน scroll ซึ่งเป็นได้ทั้งในแนวตั้งและแนวนอน ขึ้นอยู่กับการกำหนด
      - การใช้งาน ListView() โดยทั่วไปจะใช้เป็น ListTile ที่จะมีรูปแบบที่สามารถกำหนด ส่วนของ leading, title, subtitle และ trailing เหมาะสำหรับรายการที่มีจำนวนไม่มาก เช่น 4 - 10 รายการหรือไม่ควรเกินขอบเขต
        <p align="center">
            <img src="https://i.imgur.com/TVFnolv.png"> 
        </p>
      - การใช้งาน ListView.builder() คล้ายกับ ListView แต่ลิสรายการจะไม่ถูกเรียกมาแสดงทั้งหมดในครั้งเดียว จะแสดงเฉพาะบางส่วนให้เต็มพื้นที่ที่มองเห็น และเมื่อทำการเลื่อน scroll ลงไปเพื่อแสดงรายการที่เหลือ ``ต้องกำหนด itemCount ไม่อย่างงั้นจะเกิด Range error นั่นคือไปวนลูปเพิ่มรายการเกินขอบเขตหรือเกินจำนวนที่มีจริง, itemBuilder จะสร้างรายการโดยเรียกใช้งานฟังก์ชั่น IndexedWidgetBuilder() โดยตัวฟังก์ชัน IndexedWidgetBuilder นี้จะวนลูป List หรืออาเรย์ของ context เมื่อเลื่อน scroll ลงไปเพื่อแสดงรายการเพิ่มเติม ก็จะทำการวนลูปแสดงรายการจาก index ที่เหลือต่อไปเรื่อยๆ
        <p align="center">
            <img src="https://i.imgur.com/9GVwUhs.png"> 
        </p>
      - การใช้งาน ListView.separated()
      - การใช้งาน ListView.custom()
</details>
 
<details><summary>Database</summary>
<hr>

- Local Database : การเก็บข้อมูลในพื้นที่เก็บข้อมูลในเครื่องนั้น ๆ สามารถเรียกใช้งานเมื่อต้องการ แต่ถ้าทำการลบหรือล้างแอพในเครื่องข้อมูลก็จะสูญหายไปด้วย
- รูปแบบการเก็บข้อมูล
  - SQL : Table, Row, Column, Primary Key
  - NoSQL : Collections, Document, Field, ObjectID
- ติดตั้ง Package สำหรับใช้งานฐานข้อมูล ดังนี้
  - Sembast : จัดการฐานข้อมูล
  - Path_Provider : ดึงตำแหน่งฐานข้อมูลของเครื่อง
  - Path : อ้างอิงตำแหน่งที่เก็บฐานข้อมูล
- การสร้าง Store คือ การระบุที่จัดเก็บข้อมูลในแอพว่าชื่ออะไร มีรูปแบบการจัดเก็บข้อมูลแบบใด (คล้ายๆกับการสร้างตารางในฐานข้อมูล) โดยใช้ intMapStoreFactory
- การทำงานของ Snapshot เป็นส่วนของการแก้ปัญหาการเก็บข้อมูลที่มีสภาพแวดล้อมที่แตกต่างกัน เช่น การเก็บข้อมูลใน Android หรือ iOS สภาพแวดล้อมของแต่ละ Platform แตกต่างกันโดยสิ้นเชิง ส่งผลให้การจัดการข้อมูลมีความยุ่งยากไปด้วย จึงมีแนวคิดในการสร้างประเภทข้อมูลที่สามารถทำให้ข้อมูลทำงานได้ในสภาพแวดล้อมต่างกันที่เรียกว่า RecordSnapshot
</details>

      
<details><summary>Form and Validate</summary>
<hr>

## ⏭️ Form
- การสร้างแบบฟอร์ม คือ การรับข้อมูล (Input) จากผู้ใช้ เช่น ข้อความ ตัวเลข วันเวลา หรือตัวเลือกต่าง ๆ ซึ่งมีโครงสร้าง 2 ส่วน คือ แบบฟอร์มและส่วนควบคุมการทำงานของแบบฟอร์ม (Controller)
- การจัดรูปแบบฟอร์ม
  - autofocus : สั่งโฟกัสที่ช่องรับข้อมูลในตอนเริ่มต้น
  - keyboardtype : กำหนดรูปแบบของช่องรับข้อมูล
- สร้างฟอร์ม key หรือ id ของฟอร์มสำหรับอ้างอิง
  ```
  final _formKey = GlobalKey<FormState>();
  ```
- สร้าง Form ด้วย widget
  ```dart
  Form(
    key: _formKey,
    child: Column(
      children: <Widget>[
      // กำหนด widget ที่จะใช้งานกับฟอร์ม, Add TextFormFields and ElevatedButton here.
      ],
    ),
  );
  ```
- การอ้างอิงฟอร์มที่กำลังใช้งาน ตรวจสอบความถูกต้องข้อมูลในฟอร์ม
  ```dart
  if (_formKey.currentState!.validate()) { //หากผ่าน 
    // แสดงข้อความ
  } else {}
  ```
- หลักการทำงานเบื้องต้น ถ้ายังไม่ได้กรอกข้อมูล เมื่อกดปุ่ม submit ฟอร์มก็จะตรวจสอบข้อมูลโดยทำการ validate และแจ้งให้กรอกข้อมูลก่อนส่ง หลังกรอกข้อมูล และกดส่งใหม่อีกครั้ง
- การใช้งาน TextFormField ซึ่งเป็น widget หลักที่มีการใช้งานร่วมกับฟอร์ม 
  ```dart
  TextFormField(
    cursorColor: Theme.of(context).cursorColor,
    initialValue: 'Input text', // ค่าเริ่มต้น
    maxLength: 20, // จำกัดความยาวตัวอักษร
    decoration: InputDecoration( // ตกแต่งการแสดงผล
      icon: Icon(Icons.favorite),
      labelText: 'Label text',
      labelStyle: TextStyle(
        color: Color(0xFF6200EE),
      ),
      helperText: 'Helper text',
      suffixIcon: Icon(
        Icons.check_circle,
      ),
      enabledBorder: UnderlineInputBorder( // การใส่กรอบให้พื้นที่แสดงผล
        borderSide: BorderSide(color: Color(0xFF6200EE)),
      ),
    ),
  ),
  ```
- ปัญหาพื้นที่กับการใช้งาน Form ใน Flutter จะมีในเรื่องของการใช้งานแป้นพิมพ์ เข้ามาเกี่ยวข้องเมื่อมีการกรอกข้อมูล และถ้าส่วนของข้อมูลในฟอร์มมีการเปลี่ยนแปลงในเรื่องของขนาดหรือพื้นที่การแสดงข้อมูล ซึ่งอาจจะมาจากการซ่อนหรือแสดงข้อความ error หรืออื่นๆ ดังนั้นต้องกำหนดการใช้งาน SingleChildScrollView widget ครอบส่วนของ ฟอร์มอีกที เพื่อให้รองรับการปรับขนาดของพื้นที่ให้สามารถเลื่อนได้ ก็จะไม่เกิดปัญหาในเรื่องของพื้นที่แสดงข้อมูล ดังนี้
  ```dart
  body: SingleChildScrollView(
    child: Form(  // ใช้งาน Form
      key: _formKey, // กำหนด key
  ....
  ```
- การรับค่าจากข้อมูลจาก TextFormField จะมีที่จะกำหนดหลักๆ อยู่ 3 - 4  จุด คือ
  1. กำหนดตัวแปรสำหรับ controller หรือเรียกว่าตัวควบคุม
  2. นำ controller ผูกกับฟอร์มฟิลด์ที่ต้องการ
      ```dart
      / กำหนดตัวแปรรับค่า
      final _text1 = TextEditingController();
      
      ....
      TextFormField(
        controller: _text1, // ผูกกับ TextFormField ที่จะใช้
        validator: Validators.required('Please enter some text'),
      ),
      ```
  3. อ้างอิงค่า และใช้งานผ่าน controller
  4. ยกเลิกการใช้งาน
      ```dart
      @override
      void dispose() {
        _text1.dispose(); // ยกเลิกการใช้งานที่เกี่ยวข้องทั้งหมดถ้ามี
        super.dispose();
      }
      ```

## ⏭️ Validate
- การ validate หรือการตรวจสอบความถูกต้องของข้อมูลใน TextFormField จะกำหนด callback ฟังก์ชั่นให้กับ validator property เงื่อนไขการตรวจสอบก็ขึ้นกับรูปแบบตามที่ต้องการ
- callback ฟังก์ชัน จะทำงานเมื่อฟอร์มมีการตรวจสอบความถูกต้อง หรือก็คือเมื่อใช้คำสั่ง validate() อย่างในตัวอย่าง
  ```dart
  if (_formKey.currentState!.validate()) { // ตรวจสอบความถูกต้องของข้อมูลในฟอร์ม
  ```
- กรณีต้องการให้เรียกใช้งานทันทีที่มีการกรอกข้อมูล การกำหนดลักษณะนี้ จะทำให้การกรอกและส่งข้อมูลเป็นไปอย่างรวดเร็ว เพราะหากเงื่อนไขผ่านในขณะกรอกข้อมูล ก็ไม่ต้องย้อนกลับมาแก้ไข เหมือนกรณีที่เช็คด้วย validate() จากฟอร์ม นั่นคือไม่ต้องรอกดปุ่ม submit ก็รู้ได้เลยว่าข้อมูลที่กรอกอยู่นั้นผ่านหรือยังไม่ผ่านการตรวจสอบ สามารถกำหนด
  ```dart
  autovalidateMode: AutovalidateMode.always,
  ```
- การกำหนด Form Validation ด้วย ``mixin`` สร้าง class ที่จัดการเกี่ยวกับการตรวจสอบความถูกต้องของข้อมูลในฟอร์ม โดยใช้ชื่อว่า validations.dart ดังนี้
  ```dart
  // เนื่องจากข้อมูลข้อความ error ที่ validator ต้องการเป็น FormFieldValidator<String> จึงต้องกำหนดการใช้งาน FormFieldValidator โดยใช้จาก widgets ดึงมาเฉพาะที่ต้องการโดยใช้คำว่า show FormFieldValidator
  import 'package:flutter/widgets.dart' show FormFieldValidator;

  // เนื่องจากไม่ได้กำหนด constructor และ property ใดๆ จึงใช้งานเป็น mixin เป็นรูปแบบหนึ่งของ class
  mixin Validators {
    // กำหนดฟังก์ชั่น สำหรับระบุฟิลด์ที่ต้องกรอก
    static FormFieldValidator<String> required(String errMsg) {
      return (value) {
          if(value == null){
            return errMsg;
          }else if(value.isEmpty){
            return errMsg;
          }
      };
    }

    // กำหนดฟังก์ชั่น สำหรับระบุฟิลด์ต้องกรอกตัวเลขต่ำสุดอย่างน้อย
    static FormFieldValidator<String> min(int min,String errMsg) {
      return (value) => (int.parse(value!) >= 0 && int.parse(value) < min) ? errMsg : null;
    }  

    // กำหนดฟังก์ชั่น สำหรับระบุฟิลด์ต้องกรอกตัวเลขสูงสุดอย่างน้อย
    static FormFieldValidator<String> max(int max,String errMsg) {
      return (value) => (int.parse(value!) >= 0 && int.parse(value) > max) ? errMsg : null;
    } 

    // กำหนดฟังก์ชั่น สำหรับระบุฟิลด์ต้องกรอกตัวอักษรยาวน้อยสุด
    static FormFieldValidator<String> minLength(int minLength,String errMsg) {
      return (value) => (value!.isNotEmpty && value.length < minLength) ? errMsg : null;
    }  

    // กำหนดฟังก์ชั่น สำหรับระบุฟิลด์ต้องกรอกตัวอักษรยาวมากสุดไม่เกิน
    static FormFieldValidator<String> maxLength(int maxLength,String errMsg) {
      return (value) => (value!.isNotEmpty && value.length > maxLength) ? errMsg : null;
    }   

    // กำหนดฟังก์ชั่น สำหรับระบุฟิลด์ต้องกรอกข้อมูลตามรูปแบบ RegEex
    static FormFieldValidator<String> pattern(RegExp pattern,String errMsg) {
      return (value) => (value!.isNotEmpty && !pattern.hasMatch(value) ) ? errMsg : null;
    } 

    // กำหนดฟังก์ชั่น สำหรับระบุฟิลด์ต้องกรอกข้อมูลอีเมลที่ถูกต้องตามรูปแบบ
    static FormFieldValidator<String> email(String errMsg) {
      final emailPattern = RegExp(r"^[a-zA-Z0-9.a-zA-Z0-9.!#$%&'*+-/=?^_`{|}~]+@[a-zA-Z0-9]+\.[a-zA-Z]+");
      return (value) => (value!.isNotEmpty && !emailPattern.hasMatch(value) ) ? errMsg : null;
    }

    // กำหนดฟังก์ชั่น สำหรับระบุฟิลด์ต้องใช้งานการตรวจสอบหลายๆ คำสั่งรวมกัน
    static FormFieldValidator<String> compose(List<FormFieldValidator<String>> validators) {
      return (value) {
        for (final validator in validators) {
          if (validator(value) != null) return validator(value);
        }
        return null;
      };
    }

  }
  ```
  - ตัวอย่างการใช้งานใน TextFormField การกำหนดแบบหลายเงื่อนไขเพื่อให้ทำงานแบบมีประสิทธิภาพ ควรลำดับการตรวจสอบด้วย เช่น สมมติข้างต้นต้องการให้กรอกปี ค.ศ. ตั้งแต่ 2000 - 3000 อย่างแรกก็ต้องให้กรอกข้อมูล ต่อมาต้องเป็นตัวเลข ต่อมาต้องเป็นตัวเลข 4 ตัวขึ้นไป ต่อมาต้องเป็น ต่ำสุด และสูงสุด ตามลำดับ เพราะสมมติว่า ถ้า minLength หรือจำนวนตัวอักขระที่กรอก 4 ตัวขึ้นก่อนการเช็คว่าเป็นตัวเลข  ก็จะกลายเป็นว่า กรอกเป็นตัวอักษร ก็ผ่านแต่ไม่ผ่านต้องเป็นตัวเลข ดังนั้นก็ให้ไม่ผ่านตั้งแต่กรอกตัวอักษรเลย จะเป็นวิธีที่ถูกต้อง
    ```dart
    TextFormField(
      autovalidateMode: AutovalidateMode.always,
      // validator: Validators.required('Please enter some text'), // แบบกำหนดเงื่อนไขเดียว
      validator: Validators.compose([ // แบบกำหนดหลายเงื่อนไข 
        Validators.required('Please enter some text'),
        // Validators.email('Please enter a valid email'),
        Validators.pattern(RegExp(r'^([0-9])+$'), 'Only numberic'),
        Validators.minLength(4,'Please enter 4 digit'),
        Validators.min(2000,'Please enter a number between 2000 and 3000 '),
        Validators.max(3000,'Please enter a number between 2000 and 3000 '), 
      ])
    ),
    ```
- การกำหนด Form Validation ด้วย form_field_validator package ตัวช่วยในการจัดการตรวจสอบความถูกต้องของข้อมูลฟอร์มเบื้องต้น
  - ติดตั้ง form_field_validator
  - ตัวอย่างการเรียกใช้งาน
    ```dart
    // แบบเงื่อนไขเดียว
    TextFormField(
      autovalidateMode: AutovalidateMode.always,
      validator: RequiredValidator(errorText: 'this field is required'),
    ),

    // แบบหลายเงื่อนไข
    TextFormField(
      autovalidateMode: AutovalidateMode.always,
      validator: MultiValidator([  
        RequiredValidator(errorText: 'Please enter some text'),
        // EmailValidator(errorText: 'Please enter a valid email'),  
        MinLengthValidator(4, errorText: 'Please enter 4 digit'),  
        PatternValidator(r'^([0-9])+$', errorText: 'Only numberic'),
        RangeValidator(min: 2000, max: 3000, errorText: 'Please enter a number between 2000 and 3000'),
     ]),
    ```
</details>
