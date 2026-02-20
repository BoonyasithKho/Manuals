# :wave: Welcome to Flutter Manual's "Introduction to Flutter"

<details><summary><b>Introduction to Flutter</b></summary>
<hr>

<details><summary>📍 What is Flutter?</summary>

- **Flutter** คือ framework สำหรับพัฒนาแอปแบบ cross-platform (iOS, Android, Web, Desktop) มีการทำงานแบบ **“render UI ด้วย engine ของตัวเอง”** (ไม่ใช่แค่เอา widget ไปแปะ native UI ตรง ๆ) และในโหมด release จะ compile Dart เป็น native (AOT) เพื่อประสิทธิภาพที่ดีบนอุปกรณ์จริง
- **จุดเด่น:**
  - Hot Reload ปรับ UI ได้เร็วมากระหว่างพัฒนา
  - โค้ดชุดเดียวรันได้หลายแพลตฟอร์ม
  - UI ทำได้ยืดหยุ่นและสวย (Material / Cupertino / Custom)
  </details>

<details><summary>📍 Tools</summary>

- [pub.dev](https://pub.dev/) : The official package repository for Dart and Flutter apps.
- [Icon](https://fonts.google.com/icons) : Material Symbols
- IDE แนะนำ: VS Code หรือ Android Studio
</details>

<details><summary>📍 Setup Flutter</summary>
<br>
<blockquote>
  <details><summary>🏷️ Install Flutter SDK</summary>

- Get the Flutter SDK at: [https://docs.flutter.dev/get-started/install/macos](https://docs.flutter.dev/install)
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

</details>

<details><summary>🏷️ ตรวจสอบด้วย Flutter doctor</summary>

- ถ้ามีสถานะ [!] ให้แก้ทีละอันจนเป็น [✓] ตามคำแนะนำ

  ```shell
  flutter doctor
  ```

  </details>

<details><summary>🏷️ Install Xcode (สำหรับ MacOS)</summary>

- Get the Xcode at: https://developer.apple.com/xcode/.
- Configure the Xcode by running the following from the command line:

  ```shell
  sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
  sudo xcodebuild -runFirstLaunch
  sudo xcodebuild -license
  ```

  </details>

<details><summary>🏷️ CocoaPods (จำเป็นสำหรับ iOS plugins)</summary>

- Flutter แนะนำใช้ CocoaPods ในงาน iOS โดยเฉพาะโปรเจกต์ที่มี plugins
- ติดตั้ง (วิธี gem แบบคลาสสิก)

  ```shell
  sudo gem install cocoapods
  ```

  </details>

<details><summary>🏷️ Install Android Studio (สำหรับ Android)</summary>

- Download and install [Android Studio](https://developer.android.com/studio)
- Set up the Android emulator follow command recommendation.
- Agree to Android Licenses:

  ```shell
  flutter doctor --android-licenses
  ```

  </details>

<details><summary>🏷️ Install VS Code + Extensions</summary>
  - Download and install [VSCode](https://code.visualstudio.com/Download)
  - Extensions แนะนำ:
    - Flutter
    - Dart
    - Flutter Widget Snippet
    - Error lens
    - GitHub Pull Requests and Issues
  </details>
</blockquote>
</details>

<details><summary>📍 Create Project</summary>
<blockquote>

<details><summary>🏷️ วิธี VS Code</summary>

1. Open VS Code > Invoke View > Command Palette
2. Type “flutter”, and select the **Flutter: New Project**
3. Select Application
4. Select directory for project > Enter a project name **Note!** The name should be all lowercase, with underscores to separate words (my_first_app)
5. Wait for project creation to complete and the main.dart file to appear
</details>

<details><summary>🏷️ วิธี CLI</summary>

```bash
  flutter create my_first_app
  cd my_first_app
  flutter run
```

</details>

  </blockquote>
    </details>

<details><summary>📍 Structure of Project</summary>

- 📁 `lib\` เก็บไฟล์ที่แยกหน้าแอพต่าง ๆ ที่นามสกุล .dart ซึ่งการทำงานบนหน้าจอต่าง ๆ จะอยู่ในโฟลเดอร์นี้
- 📁 `test\` unit/widget tests
- 📁 `android\` และ `ios\` ใช้สำหรับการเก็บโปรเจคของ Application แต่ละระบบ เมื่อทำการรันจะมีการเก็บลงตามระบบปฏิบัติการที่รัน ซึ่งสามารถทำการแก้ไขในแต่ละระบบปฏิบัติการ
- 📁 `assets\` This folder contains any static assets, such as images or fonts, that are required by your app
- 🗄️ `pubspec.yaml` ใช้สำหรับการตั้งค่าต่าง ๆ ให้กับโปรเจคหรือการเรียกใช้งานไลบราลีต่าง ๆ การประกาศไลบราลี ไอคอน ต้องทำการตั้งค่าในไฟล์นี้
- 🗄️ `README.md` This file provides information about your Flutter project, such as how to install and run it

</details>

<details><summary>📍 Run the app</summary>

- เลือก device/simulator จากแถบล่างของ VS Code
- Invoke Run > Start Debugging
- Wait for the app to launch—progress is printed in the Debug Console view
- After the app build completes, you’ll see the starter app on your device
- Change the string `` You have `pushed` the button this many times `` > `` You have `clicked` the button this many times ``
- Save and Hot Reload
</details>

<details><summary>📍 First Project with Flutter</summary>

1. We've created Demo project with Material App. Material App's built which has Statefulwidget class. It has scafold widget is home of material app.
2. In MyHomePage (Stateful widget) has incrementCouter function for set value of counter.
3. In Scaffold Widget has AppBar and Body. Body has center widget with column of Text and counter value.
4. In body, FloatactionButton with onpressed 'incrementCouter' and Icon widget to child.

```dart
   import 'package:flutter/material.dart';

   void main() => runApp(const MyApp());

   class MyApp extends StatelessWidget {
    const MyApp({super.key});

    @override
    Widget build(BuildContext context) {
      return MaterialApp(
        title: 'Flutter Demo',
        theme: ThemeData(primarySwatch: Colors.blue),
        home: const MyHomePage(title: 'Home'),
      );
    }
   }

   class MyHomePage extends StatefulWidget {
    const MyHomePage({super.key, required this.title});
    final String title;

    @override
    State<MyHomePage> createState() => \_MyHomePageState();
   }

   class _MyHomePageState extends State<MyHomePage> {
    int counter = 0;
    void increment() => setState(() => counter++);

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: AppBar(title: Text(widget.title)),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              const Text('You clicked this many times:'),
              Text('$counter', style: Theme.of(context).textTheme.headlineMedium),
            ],
          ),
        ),
        floatingActionButton: FloatingActionButton(
          onPressed: increment,
          child: const Icon(Icons.add),
        ),
      );
    }
   }
```

</details>
<hr>
</details>

<details><summary><b>Dart(101)</b></summary>
<hr>
  
<details><summary>💡 What is Dart?</summary>

- **Dart** คือ ภาษา OOP ของ Google ใช้ทำ mobile/web/desktop/server ซึ่งเป็นภาษาสำหรับการพัฒนา Flutter

</details>

<details><summary>💡 Naming Convention</summary>

- `camelCase` : สำหรับการตั้งชื่อตัวแปร โดยตัวแรกเป็นตัวพิมพ์เล็ก คั่นคำต่อไปด้วย ตัวอักษรพิมพ์ใหญ่ เช่น newProductPrice
- `PascalCase` : สำหรับการตั้งชื่อ Class โดยตัวแรกเป็นตัวพิมพ์ใหญ่คั่นคำต่อไปด้วย ตัวอักษรพิมพ์ใหญ่ เช่น MyUserName
- `snake_case` : สำหรับการตั้งชื่อ File or Folder โดยการใช้ตัวพิมพ์เล็ก คั่นคำต่อไปด้วย '\_' เช่น number_of_client
- ชื่อ package : ตัวพิมพ์เล็กทั้งหมด
</details>

<details><summary>💡 Datatype</summary>

- `int` : จำนวนเต็ม
- `double` : ทศนิยม
- `num` : ตัวเลขจำนวนเต็ม และทศนิยม
- `bool` : true, false
- `string` : ประโยค จะอยู่ใน " " หรือ ' ' (แนะนำให้ใช้แบบ single quote)
- `dynamic` : ตัวแปรแบบเปลี่ยนชนิดได้ ซึ่งทุกตัวแปรสามารถเป็น null ได้ สามารถเปลี่ยนแปลง type ได้ตลอด
- `var` : เป็นการประกาศชนิดตัวแปรด้วยโปรแกรม เมื่อมีการเลือกเป็น type ไหนแล้วจะเป็น type นั้นจนจบโปรแกรม
- `final` : คล้าย var เปลี่ยน type ด้วยโปรแกรม แต่ไม่สามารถเปลี่ยนเป็นค่าอื่นได้ กรณีเป็น Reference/Object Data Types สามารถแก้ไขค่าได้ แต่ไม่สามารถกำหนดค่าให้ตัวแปรใหม่ได้
- `const` : ค่าคงที่ compile-time

</details>
<hr>
</details>

<details><summary>Widgets and Layouts</summary>
<hr>

<details><summary>▶️ Widget</summary>

- ทุกอย่างใน Flutter คือ Widget เป็นส่วนที่ถูกใช้สร้างเป็นหน้าตาของ App หรือ User Interface (UI)
- แต่ละ widget จะถูกวางซ้อนอยู่ภายใน Parent widget และได้รับการส่งต่อสืบทอดคุณสมบัติ (Properties) ต่างๆ จาก Parent อีกที
- `MaterialApp` เป็น root widget หรือ Widget หลัก ที่ทำหน้าที่กำหนดส่วนต่าง ๆ ของแอป
- Widget แต่ละตัวจะมีส่วนที่เรียกว่า Properties สำหรับกำหนดคุณสมบัติ
</details>

<details><summary>▶️ State Widget</summary>

- Stateless Widget เป็น Widget ที่ไม่มีการเปลี่ยนแปลงตัวเอง การแสดงผลจะมีลักษณะคงที่ไม่เปลี่ยนแปลง
- Stateful Widget เป็น Widget ที่มีการเปลี่ยนแปลงของ state โดยสามารถใช้คำสั่ง setState() เพื่อกำหนดการเปลี่ยนแปลง
</details>

<details><summary>▶️ Layouts</summary>

- `Row` / `Column` สำหรับการจัด Layout ใช้บ่อยที่สุด โดย Row Widget ใช้ในการแสดงผลในแนวนอน ส่วน Column Widget ใช้ในการแสดงผลในแนวตั้ง
- `Wrap` สำหรับการจัด Layout เมื่อมีการแสดงผลที่เกินขอบเขตการแสดงผลของหน้าจอ โดยจะทำการจัดเรียง Widget ให้มีจำนวนข้อมูลที่พอดีกับขอบเขตหน้าจอ คล้ายกับการทำ Row และ Column รวมกัน
- `Container` ทำหน้าที่เป็นพื้นที่สำหรับการรวม Widget ต่างๆ เอาไว้
- `Sizebox` สำหรับการกำหนดขนาดการแสดงผล จะคล้ายกับการใช้งาน Container แต่จะกิน RAM น้อยกว่า แต่จะสามารถกำหนดได้เฉพาะความกว้าง ความยาวเท่านั้น
- `Stack` สำหรับสร้างลำดับการซ้อนทับของ Layout
- `ListView` / `GridView` สำหรับแสดงผล children widget เป็นแบบ list/gallery
- `Expanded` / `Flexible` สำหรับแบ่งพื้นที่ตาม flex
- ถ้า content ยาวเกินจอ ให้ใช้ `ListView` หรือ `SingleChildScrollView`
- `ListView` เป็นการสร้างลิสรายการที่สามารถเลือนได้ โดยเรียงต่อกันเป็นแนว แต่ละรายการจะเรียงต่อหลังกันไปเรื่อยๆ ตามทิศทางการเลื่อน scroll ซึ่งเป็นได้ทั้งในแนวตั้งและแนวนอน ขึ้นอยู่กับการกำหนด แต่ละรายการในลิส จะเรียกว่า ListTile ที่สามารถกำหนด ส่วนของ leading, title, subtitle และ trailing มีหลายแบบ เช่น

  - `ListView.builder()` เหมาะกับ “รายการยาว/ไม่รู้จำนวนแน่ชัด/มาจาก API” เพราะสามารถสร้างเฉพาะ item ที่อยู่ในหน้าจอ ทำให้ลื่นและประหยัดหน่วยความจำกว่า และเมื่อทำการเลื่อน scroll ลงไปเพื่อแสดงรายการที่เหลือ ต้องกำหนด
    - `itemCount` ไม่อย่างงั้นจะเกิด Range error ซึ่งเป็นผลจากการวนลูปเพิ่มรายการเกินขอบเขตหรือเกินจำนวนที่มีจริง
    - `itemBuilder` จะสร้างรายการโดยเรียกใช้งานฟังก์ชัน IndexedWidgetBuilder() ซึ่งจะวนลูป List หรืออาเรย์ของ context เมื่อเลื่อน scroll ลงไปเพื่อแสดงรายการเพิ่มเติม ก็จะทำการวนลูปแสดงรายการจาก index ที่เหลือต่อไปเรื่อยๆ

  ```dart
  		ListView.builder(
  		  itemCount: items.length,
  		  itemBuilder: (context, index) {
  		    final item = items[index];
  		    return ListTile(
  		      title: Text(item.title),
  		      subtitle: Text(item.subtitle),
  		    );
  		  },
  		);
  ```

  - `ListView.separated()` มีลักษณะเหมือน builder แต่มี separatorBuilder เพิ่มมา เพื่อสร้าง “ตัวคั่นระหว่างรายการ” เช่น Divider, spacing, header เล็ก ๆ โดย ไม่ต้องแทรก divider เองใน itemBuilder ทำให้โค้ดสะอาด ต้องมีการกำหนด `sepatatorBuilder` โดยจะถูกเรียก ระหว่าง item เท่านั้น (จำนวน separator = itemCount - 1) เพิ่มเข้ามาด้วย

  ```dart
  		ListView.separated(
  		  itemCount: items.length,
  		  itemBuilder: (context, index) {
  		    final item = items[index];
  		    return ListTile(title: Text(item.title));
  		  },
  		  separatorBuilder: (context, index) {
  		    return const Divider(height: 1);
  		  },
  		);
  ```

  - `ListView.custom()` เป็น ListView ที่ยืดหยุ่นที่สุด เพราะสามารถเลือก SliverChildDelegate เองได้ (เช่น SliverChildBuilderDelegate, SliverChildListDelegate) และตั้งค่าละเอียดได้มากขึ้น เหมาะสำหรับกรณี advanced ซึ่งต้องการควบคุมการ build/rebuild แบบละเอียด ตามตัวอย่าง

  ```dart
  		// ตัวอย่าง 1: ใช้แบบ lazy (คล้าย builder)
  		ListView.custom(
  		  childrenDelegate: SliverChildBuilderDelegate(
  		    (context, index) {
  		      final item = items[index];
  		      return ListTile(title: Text(item.title));
  		    },
  		    childCount: items.length,
  		  ),
  		);

  		// ตัวอย่าง 2: ใช้แบบมี children list (คล้าย ListView(children: ...))
  		ListView.custom(
  		  childrenDelegate: SliverChildListDelegate(
  		    [
  		      const ListTile(title: Text('A')),
  		      const ListTile(title: Text('B')),
  		      const ListTile(title: Text('C')),
  		    ],
  		  ),
  		);
  ```

  - `TextFormField` เป็น widget หลักที่มีการใช้งานร่วมกับฟอร์ม

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

  - `webview` เป็น widget ที่ใช้สำหรับแสดงหน้าเว็บเพจใน flutter ต้องติดตั้ง WebView package และ กำหนด API level ของ android ต่ำสุดที่รองรับ จะต้องกำหนดเป็น 19 หรือ 20 ขึ้นไป โดยให้ไปแก้ไขที่ไฟล์ build.gradle กำหนด minSdkVersion เป็น 19 ตามรูป ถ้าเราไม่กำหนด จะไม่สามารถ build ผ่านได้
  <p align="center">
    <img src="https://i.imgur.com/qNrcSfY.jpg"> 
  </p>
  - Ref: https://www.ninenik.com/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99_WebView_%E0%B9%81%E0%B8%AA%E0%B8%94%E0%B8%87%E0%B9%80%E0%B8%A7%E0%B9%87%E0%B8%9A%E0%B9%84%E0%B8%8B%E0%B8%95%E0%B9%8C_%E0%B9%83%E0%B8%99_Flutter-1043.html
  </details>

<details><summary>▶️ Scaffold</summary>

- โครงหน้าสำเร็จรูป ประกอบด้วย
  - `AppBar` : A horizontal bar typically shown at the top of an app using the appBar property
  - `Body` : The primary content of the scaffold
  - `FloatingActionButton` : ปุ่มที่มีลักษณะการแสดงผลแบบลอย ๆ ในมุมล่างขวามือ การใช้ปุ่มสามารถใส่ icon ได้
  - `BottomNavigationBar` : A horizontal array of buttons typically shown along the bottom of the app using the bottomNavigationBar property

</details>
<hr>
</details>
  
<details><summary>Navigation</summary>

- ใช้ร่วมกับ route ในการจัดการหน้าต่างย่อย
- มีการจัดวางโครงสร้างแบบ stack ซึ่งเป็นการซ้อนทับตามลำดับจากล่างขึ้นบน โดยแผ่่นที่นำมาเรียงต่อกันคือ ส่วนของ Widget ย่อย แผ่นที่แสดงผลจะถูกแสดงซ้อนทับหน้าอื่น ๆ ไว้
- Operator ของ Stack:

  - `push` : เป็นการนำหน้าใหม่มาไว้บนสุดของ stack สามารถทำการรับส่งข้อมูลระหว่างกันได้
  - `pop` : เป็นการนำหน้าชั้นบนสุดออกจาก stack
  <p align="center">
    <img src="https://itome.team/blog/2019/12/flutter-advent-calendar-day10/navigator_stack.png"> 
  </p>

  - `pushNamed` : เป็นการเรียก route ที่ต้องการ ใช้ในกรณีที่มีจำนวนหน้าซับซ้อน เช่น สมมุติว่าผู้อ่านอยู่ page1 และต้องการเปิดหน้าใหม่ก็จะเจอ page2 พอผู้อ่านอยู่ page2 และต้องการเปิดหน้าใหม่ก็จะเจอ page3 จะเป็นแบบนี้ไปเรื่อยๆ
  - `pushReplacementNamed` : เป็นการแทนที่หน้าที่เราอยู่ ณ ปัจจุบัน สมมุติว่าผู้อ่านอยู่ page1 เมื่อกด pushReplacementNamed จะมี page อื่นมาแทน โดยไม่สามารถ pop กลับไปก่อนหน้าได้
  - `pushNamedAndRemoveUntil` : ใช้ในกรณีที่เราต้องการ push หน้าใหม่ขึ้นมาแล้วทำการลบหน้าที่ซ้อนๆ กันอยู่ด้านล่างของ Stack ทิ้งออกไป
  - `popUntil` : จะเป็นการ pop จนกว่าจะถึง page ที่ต้องการ
  <p align="center">
    <img src="https://itome.team/blog/2019/12/flutter-advent-calendar-day10/navigator_pop_until.png"> 
  </p>

  - `systemNavigator.pop()` : ปิดแอพเพื่อออกไปหน้า Menu เครื่อง

</details>

<details><summary>API & FutureBuilder</summary>
  <hr>

<details><summary>⤵️ API คืออะไร</summary>

- วิธีเรียกใช้งานโปรแกรม เป็นรูปแบบโปรแกรมกับโปรแกรม เพื่อใช้สำหรับการแลกเปลี่ยนข้อมูลระหว่างกัน ผ่านทาง Internet โดย
  โปรแกรมต้นทาง จะเรียกว่า Server คอยเปิดและให้บริการข้อมูล
  โปรแกรมปลายทาง จะเรียกว่า Client สำหรับเรียกใช้บริการจาก Server
- การทำงานของ API
- ผู้ให้บริการจะเป็นคนกำหนดกฏการเรียกใช้งานข้อมูล ซึ่งก่อนทำการเรียกใช้งาน API จะต้องรู้ว่าใช้คำสั่งอะไร (1 คำสั่ง = 1 API)
- Request การส่งคำขอเพื่อใช้บริการ API
- Response การตอบกลับข้อมูลตามคำขอที่ส่งไป (ได้หรือไม่ได้)
- Open API คือ API ที่เปิดให้คนนอกสามารถเข้าถึงข้อมูลได้
- Web API คือ การให้บริการข้อมูลผ่าน Website โดย HTTP ซึ่งอยู่ในรูปแบบ XML และ JSON ซึ่งข้อมูล (ภาพ,เสียง,ข้อมูลทางธุรกิจ) จะเรียกว่า Resource
- `Get` สำหรับร้องขอข้อมูล
- `POST` สำหรับสร้างข้อมูลใหม่
- `PUT` สำหรับอัพเดทข้อมูล
- `DELETE` สำหรับลบข้อมูล
- การใช้งาน API ต้องทำการติดตั้ง HTTP Package

  ```dart
  import 'dart:convert';
  import 'package:http/http.dart' as http;

  @override
  void initState() {
     super.initState();
      getData();
  }
  Future<List<dynamic>> getData() async {
      final url = Uri.parse('YOUR_API_URL');
  	   final res = await http.get(url);

     if (res.statusCode != 200) {
     		throw Exception('HTTP ${res.statusCode}');
     }
     return jsonDecode(res.body) as List<dynamic>;
  }
  ```

- การกำหนดสิทธิ์การขอใช้งานเครือข่าย INTERNET สำหรับ Android : android > app > src > main > AndroidManifest.xml
  ```xml
  <manifest xmlns:android...>
    ...
    <uses-permission android:name="android.permission.INTERNET" />
    <application ...
  </manifest>
  ```
- นำไฟล์ JSON object ไปใช้ใน dart ด้วย https://app.quicktype.io/ และทำ Data Model ข้อมูล
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
- จากรูปแบบข้างต้น โครงสร้างข้อมูล JSON String data มีด้วยกัน 4 ตัวคือ userID , id , title และ body เวลาสร้าง Data Model ไม่จำเป้นต้องใช้หมดทั้ง 4 ตัวก็ได้ อาจจะกำหนดแค่ id กับ title ได้

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

- More information for [Parse JSON in Dart/Flutter](https://codewithandrea.com/articles/parse-json-dart/)
</details>

<details><summary>⤵️ FutureBuilder</summary>

- การทำงานของ Flutter มี 2 แบบ คือ
  - การทำงานแบบ Synchronous คือ การทำงานแบบตามลำดับ ต้องให้งานก่อนหน้าเสร็จก่อนถึงจะทำงานในขั้นตอนต่อไป
  - การทำงานแบบ Asynchronous หรือ Non-blocking คือ การทำงานที่สามารถสลับไปทำงานอื่นได้โดยไม่ต้องรอกัน ซึ่งต้องมีการพ่วงการใช้งานกับ Future
    - Future คือ การนำค่าที่เกิดขึ้นในอนาคตมาใช้งาน ซึ่งจะทำการเช็คข้อมูลที่เกิดขึ้นผ่าน State เช่น สมบูรณ์ (Complete), ไม่สมบูรณ์ (Incomplete) เป็นต้น เมื่อมีการทำงานแบบ Asynchronous จะมีการใช้งานร่วมกับคำสั่ง async และ await สำหรับรอให้ทำงานจนเสร็จ
- FutureBuilder ใช้กับข้อมูล async (Future)
- แยก state: loading / error / done

- การดึงข้อมูล api ด้วย http package และการแปลงข้อมูล api ที่ได้มาในรูปแบบ JSON data เป็นในรูปแบบ List<Article> โดยใช้ฟังก์ชั่นของ Flutter มาช่วย
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
- ฟังก์ชันทำการดึงข้อมูลให้ได้ข้อมูล JSON String data มาแล้วอ่านข้อมูลจากแต่ละ tag เพื่อนำมาใส่ใน getData นำไปแสดงหรือใช้งานร่วมกับ FutureBuilder
  ```dart
  FutureBuilder(
    future: getData(),
    builder: (context, snapshot) {
      if (snapshot.connectionState == ConnectionState.waiting) {
        return const Center(child: CircularProgressIndicator());
      }
      if (snapshot.hasError) {
        return Text('Error: ${snapshot.error}');
      }
      final data = snapshot.data as List<dynamic>;
      return ListView.builder(
        itemCount: data.length,
        itemBuilder: (_, i) => ListTile(title: Text('${data[i]}')),
      );
    },
  )
  ```
  </details>
  <hr>
  </details>

<details><summary>Form and Validate</summary>
<hr>

<details><summary>⏭️ Form</summary>

- การสร้างแบบฟอร์ม คือ การรับข้อมูล (Input) จากผู้ใช้ เช่น ข้อความ ตัวเลข วันเวลา หรือตัวเลือกต่าง ๆ
- การจัดรูปแบบฟอร์ม
  - autofocus : สั่งโฟกัสที่ช่องรับข้อมูลในตอนเริ่มต้น
  - keyboardtype : กำหนดรูปแบบของช่องรับข้อมูล
- สร้างฟอร์ม key หรือ id ของฟอร์มสำหรับอ้างอิง (validate)
- สร้าง Form ด้วย widget เพื่อรับค่า

  ```dart
  final formKey = GlobalKey<FormState>();
  final nameCtrl = TextEditingController();

  Form(
    key: formKey,
    child: Column(
      children: [
        TextFormField(
          controller: nameCtrl,
          validator: (v) => (v == null || v.isEmpty) ? 'Required' : null,
        ),
        ElevatedButton(
          onPressed: () {
            if (formKey.currentState!.validate()) {
              // OK
            }
          },
          child: const Text('Submit'),
        )
      ],
    ),
  )
  ```

- การอ้างอิงฟอร์มที่กำลังใช้งาน ตรวจสอบความถูกต้องข้อมูลในฟอร์ม
  ```dart
  if (_formKey.currentState!.validate()) { //หากผ่าน
    // แสดงข้อความ
  } else {}
  ```
- หลักการทำงานเบื้องต้น ถ้ายังไม่ได้กรอกข้อมูล เมื่อกดปุ่ม submit ฟอร์มก็จะตรวจสอบข้อมูลโดยทำการ validate และแจ้งให้กรอกข้อมูลก่อนส่ง หลังกรอกข้อมูล และกดส่งใหม่อีกครั้ง
- ปัญหาพื้นที่กับการใช้งาน Form ใน Flutter จะมีในเรื่องของการใช้งานแป้นพิมพ์ เข้ามาเกี่ยวข้องเมื่อมีการกรอกข้อมูล และถ้าส่วนของข้อมูลในฟอร์มมีการเปลี่ยนแปลงในเรื่องของขนาดหรือพื้นที่การแสดงข้อมูล ซึ่งอาจจะมาจากการซ่อนหรือแสดงข้อความ error หรืออื่นๆ ดังนั้นต้องกำหนดการใช้งาน SingleChildScrollView widget ครอบส่วนของ ฟอร์มอีกที เพื่อให้รองรับการปรับขนาดของพื้นที่ให้สามารถเลื่อนได้ ก็จะไม่เกิดปัญหาในเรื่องของพื้นที่แสดงข้อมูล ดังนี้
  ```dart
  body: SingleChildScrollView(
    child: Form(  // ใช้งาน Form
      key: _formKey, // กำหนด key
  ....
  ```
- การรับค่าจากข้อมูลจาก TextFormField จะมีที่จะกำหนดหลักๆ อยู่ 3 - 4 จุด คือ

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
     `dart
@override
void dispose() {
  _text1.dispose(); // ยกเลิกการใช้งานที่เกี่ยวข้องทั้งหมดถ้ามี
  super.dispose();
}
`
     </details>

<details><summary>⏭️ Validate</summary>

- การ validate หรือการตรวจสอบความถูกต้องของข้อมูลใน TextFormField จะกำหนด callback ฟังก์ชั่นให้กับ validator property เงื่อนไขการตรวจสอบก็ขึ้นกับรูปแบบตามที่ต้องการ
- callback ฟังก์ชัน จะทำงานเมื่อฟอร์มมีการตรวจสอบความถูกต้อง หรือก็คือเมื่อใช้คำสั่ง validate() อย่างในตัวอย่าง
  ```dart
  if (_formKey.currentState!.validate()) { // ตรวจสอบความถูกต้องของข้อมูลในฟอร์ม
  ```
- กรณีต้องการให้เรียกใช้งานทันทีที่มีการกรอกข้อมูล การกำหนดลักษณะนี้ จะทำให้การกรอกและส่งข้อมูลเป็นไปอย่างรวดเร็ว เพราะหากเงื่อนไขผ่านในขณะกรอกข้อมูล ก็ไม่ต้องย้อนกลับมาแก้ไข เหมือนกรณีที่เช็คด้วย validate() จากฟอร์ม นั่นคือไม่ต้องรอกดปุ่ม submit ก็รู้ได้เลยว่าข้อมูลที่กรอกอยู่นั้นผ่านหรือยังไม่ผ่านการตรวจสอบ สามารถกำหนด
  ```dart
  autovalidateMode: AutovalidateMode.always,
  ```
- การกำหนด Form Validation ด้วย `mixin` สร้าง class ที่จัดการเกี่ยวกับการตรวจสอบความถูกต้องของข้อมูลในฟอร์ม โดยใช้ชื่อว่า validations.dart ดังนี้

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

  - ตัวอย่างการใช้งานใน TextFormField การกำหนดแบบหลายเงื่อนไขเพื่อให้ทำงานแบบมีประสิทธิภาพ ควรลำดับการตรวจสอบด้วย เช่น สมมติข้างต้นต้องการให้กรอกปี ค.ศ. ตั้งแต่ 2000 - 3000 อย่างแรกก็ต้องให้กรอกข้อมูล ต่อมาต้องเป็นตัวเลข ต่อมาต้องเป็นตัวเลข 4 ตัวขึ้นไป ต่อมาต้องเป็น ต่ำสุด และสูงสุด ตามลำดับ เพราะสมมติว่า ถ้า minLength หรือจำนวนตัวอักขระที่กรอก 4 ตัวขึ้นก่อนการเช็คว่าเป็นตัวเลข ก็จะกลายเป็นว่า กรอกเป็นตัวอักษร ก็ผ่านแต่ไม่ผ่านต้องเป็นตัวเลข ดังนั้นก็ให้ไม่ผ่านตั้งแต่กรอกตัวอักษรเลย จะเป็นวิธีที่ถูกต้อง
    ```dart
    TextFormField(
      autovalidateMode: AutovalidateMode.always,
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

        ````dart
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
        ````

    </details>
    <hr>
    </details>

<details><summary>Map</summary>
<hr>

<details><summary>🗺️ Google Map</summary>

- การติดตั้ง Google Maps for Flutter เบื้องต้น
  1. ขอ API Key จากลิงค์ https://cloud.google.com/maps-platform/
  2. ทำการ Enable เพื่อที่จะเรียกใช้ API (Enable Maps SDK for Android / iOS)
  3. เข้าไปที่เมนู Credentials เพื่อที่จะสร้าง API Key เอาไปแปะในโค้ดให้เชื่อมต่อกับ Google Cloud Platform
     Create Credentials -> API Key
- นำ API Key มาใช้

  - Android : เพิ่ม API Key ที่ไฟล์ AndroidManifest.xml ในโฟลเดอร์ android/app/src/main/AndroidManifest.xml

    ```xml
    <manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.fluttergooglemap">
    // ส่วนที่เพิ่มเติม เพื่อทำการกำหนด Permission
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>

    <application
        android:name="io.flutter.app.FlutterApplication"
        android:label="fluttergooglemap"
        android:icon="@mipmap/ic_launcher">
        // ส่วนที่เพิ่มเติม นำ API Key ที่ได้มาแทนใน "YOUR API KEY"
        <meta-data android:name="com.google.android.geo.API_KEY"
            android:value="YOUR API KEY"/>

        <activity
            android:name=".MainActivity"
            ...
    ```

    Set the minSdkVersion in android/app/build.gradle:

    ```
    android {
       defaultConfig {
           minSdkVersion 20 // เดิมเป็น minSdkVersion flutter.minSdkVersion
         }
     }
    ```

  - iOS : เข้าไปที่ไฟล์ AppDelegate.swift (ios/Runner/AppDelegate.swift) เพิ่ม API KEY เข้าไป GMSServices.provideAPIKey("YOUR KEY HERE")
    ```
    @UIApplicationMain
    @objc class AppDelegate: FlutterAppDelegate {
      override func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
      ) -> Bool {
      GMSServices.provideAPIKey("YOUR API KEY")
        GeneratedPluginRegistrant.register(with: self)
        return super.application(application, didFinishLaunchingWithOptions: launchOptions)
      }
    }
    ```
    และเข้าไปที่ไฟล์ info.plist เพิ่มคำสั่ง เพื่อขอ permission
    ```xml
    <dict>
     <key>NSLocationWhenInUseUsageDescription</key>
          <string>This app needs your location to test the location feature of the Google Maps plugin.</string>
          <key>io.flutter.embedded_views_preview</key>
          <true/>
     ...
    ```
  - ติดตั้ง google_maps_flutter จาก pub.dev ใน pubspec.yaml
  - import Library
    ```dart
    import 'package:google_maps_flutter/google_maps_flutter.dart';
    ```
  - สร้างตัวแปรประเภท GoogleMapController โดยเป็น class ที่เอาไว้สร้าง Future สำหรับควบคุมการทำงาน
    ```dart
    class _MyHomePageState extends State<MyHomePage> {
      Completer<GoogleMapController> _controller = Completer();
    ```
  - การใช้งาน GoogleMap จะต้องทำการ initialCameraPosition เสมอ เพื่อกำหนดพิกัดจุดเริ่มต้นสถานที่ให้ GoogleMap ทำการแสดงผล
    `dart
body: GoogleMap(
    initialCameraPosition: CameraPosition(
      target: LatLng(13.757429, 100.502465), //กำหนดพิกัดเริ่มต้นบนแผนที่
      zoom: 15, //กำหนดระยะการซูม สามารถกำหนดค่าได้ 0-20
    ),
    onMapCreated: (GoogleMapController controller) {
      _controller.complete(controller);
    },
  ),
`
    </details>

<details><summary>🗺️ Flutter Map</summary>

- Mapping package for Flutter, based off of 'leaflet.js'. Simple and easy to learn, yet completely customizable and configurable, it's the best choice for mapping in your Flutter app.
- Demonstration
  This code snippet demonstrates everything you need for a simple map - of course, FlutterMap is much more customisable than just this!
  ```dart
  return FlutterMap(
      options: MapOptions(
         center: LatLng(51.509364, -0.128928),
         zoom: 9.2,
      ),
      nonRotatedChildren: [
         TileLayer(
             urlTemplate: 'https://tile.openstreetmap.org/{z}/{x}/{y}.png',
         ),
     ],
  );
  ```
- Map Layer
  ```
  Sphere Basemap > 'https://basemap.sphere.gistda.or.th/tiles/sphere_streets/EPSG3857/{z}/{x}/{y}.png?key=test2022'
  Sphere Satellite > 'https://basemap.sphere.gistda.or.th/tiles/thailand_images/EPSG3857/{z}/{x}/{y}.jpeg?key=test2022'
  Google Basemap > 'https://mt1.google.com/vt/lyrs=r&x={x}&y={y}&z={z}'
  Google Satellite > 'https://mt1.google.com/vt/lyrs=y&x={x}&y={y}&z={z}'
  ```
- Marker Layer
  ```dart
  FlutterMap(
      options: MapOptions(),
      children: [
         MarkerLayer(
             markers: [
                Marker(
                  point: LatLng(30, 40),
                  width: 80,
                  height: 80,
                  builder: (context) => FlutterLogo(),
                ),
             ],
         ),
      ],
  ),
  ```
- Get data from API
- More data [Flutter Map Document](https://docs.fleaflet.dev/)
</details>

<details><summary>🗺️ Sphere Map</summary>

การเริ่มต้น sphere map flutter

- Get package sphere_maps_flutter(lastest version) from pub.dev and install
  การเพิ่ม Sphere map widget
- Define parameter
  ```
  final map = GlobalKey<SphereMapState>();
  final GlobalKey<ScaffoldMessengerState> messenger = GlobalKey<ScaffoldMessengerState>();
  ```
- import Spheremap to body
  ```
  SphereMapWidget(
    apiKey: "", // use sphere key
    bundleId: "",
    key: map,
  ),
  ```
- ปิดการหมุนแผนที่
  ```dart
  widget.map.currentState?.call("Renderer.touchZoomRotate.disableRotation");
  ```
- ปิดการใช้งานเครื่องมือแผนที่มาตรฐานของ Sphere map
  ```dart
  options: {
              "ui": Sphere.SphereStatic("UiComponent", "None"),
            },
  ```
- การเรียกใช้งาน WMS จาก ArcGIS Server ต้องกำหนด "id" เนื่องจาก ArcGIST Server มีการกำหนดชื่อ Layer เป็นตัวเลข ทำให Spheremap มองเห็นเป็น layer เดียวกัน
  ```dart
      final layerPM = Sphere.SphereObject("Layer", args: [
      "0",
      {
        "url": pmMap,
        "type": Sphere.SphereStatic("LayerType", "WMS"),
        "opacity": 0.8,
        "zIndex": 5,
        "id": "unique_1",
      }
    ]);
  ```
- More data [GISTDA sphere Map API](https://sphere.gistda.or.th/docs/)
</details>
<hr>
</details>

<details><summary>Datetime</summary>
<hr>

1. การใช้ dateformat ต้องติดตั้ง Package intl
   ```dart
   import 'package:intl/intl.dart';
   ```
2. ประกาศ ตัวแปรชนิด String เพื่อรับ DateFormat
   ```dart
   String dateTime = DateFormat("dd MMMM yyyy").format(DateTime.now());
   ```
3. นำ datetime ไปใส่ใน Text widget
4. Change date with datepicker with icon `Icons.arrow_drop_down`

   ```dart
       IconButton(
           onPressed: () async {
               DateTime? pickedData = await showDatePicker(
                   context: context,
                   initialDate: DateTime.now(),
                   firstDate: DateTime(2000),
                   lastDate: DateTime(2050),
               );
               if (pickedData != null) {
                   setState(() {
                       dateTime = DateFormat("dd MMMM yyyy").format(pickedData);
                   });
               }
           },
           icon: const Icon(Icons.arrow_drop_down),
       ),
   ```

   <hr>

  </details>

<details><summary>Change Application Icon</summary>
<hr>

1. Call Package `flutter_launcher_icons` and install package
2. Create a folder called asset in the root directory. Inside the asset folder create one more folder called icons and place your launcher icon inside. `Hint: It’s recommended to use a higher resolution image, for example, the image of 1024*1024.`
3. Add flutter_icons inside the pubspec.yaml to reference the new launcher icon. `Note: foreground icon is smaller than image size with color background`

   ```yaml
   flutter_icons:
     android: true
     ios: true
     image_path: "assets/icons/bar-chart.png"
     adaptive_icon_background: "#ed1e79"
     adaptive_icon_foreground: "assets/icons/bar-chart_fore.png"
   ```

4. In terminal, use `flutter pub run flutter_launcher_icons:main` for run the app and verify the new launcher icon updated in the launcher app for both Android and iOS.

<hr>
</details>

<details><summary>Chart</summary></summary>
<hr>

<details><summary>Syncfusion_flutter_charts</summary>

1. Get package `syncfusion_flutter_charts` and install
2. Add SfCartesianChart or other type to code
   ```dart
   SfCartesianChart(
     title: ChartTitle(text: 'Half yearly sales analysis'),
     legend: Legend(isVisible: true),
     primaryXAxis: CategoryAxis(),
     series: <ChartSeries>[
       // Initialize line series
       LineSeries<ChartData, String>(
         enableTooltip: true,
         dataSource: [
           // Bind data source
           ChartData('Jan', 35),
           ChartData('Feb', 28),
           ChartData('Mar', 34),
           ChartData('Apr', 32),
           ChartData('May', 40)
         ],
         xValueMapper: (ChartData data, _) => data.x,
         yValueMapper: (ChartData data, _) => data.y,
         dataLabelSettings: const DataLabelSettings(isVisible: true),
       ),
     ],
   ),
   ```
3. Create class ChartData for model of data
   ```dart
   class ChartData {
     ChartData(this.x, this.y);
     final String x;
     final double? y;
   }
   ```
4. Add tooltip for show information of point with parameter
   ```dart
   late TooltipBehavior _tooltipBehavior;
   ```
5. Get TooltipBehavior at initial state
   ```dart
   _tooltipBehavior = TooltipBehavior(enable: true);
   ```
6. In chart widget, add \_tooltipBehavior for tooltipBehavior
   ```dart
   tooltipBehavior: _tooltipBehavior,
   ```
   </details>

<details><summary>Charts_flutter</summary>

1. Get package `charts_flutter` and install [ref.](https://google.github.io/charts/flutter/gallery.html)
2. Create class ChartData for model of data

   ```dart
   import 'package:charts_flutter/flutter.dart' as charts;

   class ChartData {
     final String id;
     final String year;
     final int sales;
     final charts.Color barColor;

     ChartData({
       required this.id,
       required this.year,
       required this.sales,
       required this.barColor,
     });
   }
   ```

3. Create class ChartsFlutter for config chart style

   ```dart
   import 'package:flutter/material.dart';
   import 'package:charts_flutter/flutter.dart' as charts;
   import 'datamodel.dart';

   class ChartsFlutter extends StatelessWidget {
     final List<List<ChartData>> data;
     const ChartsFlutter({super.key, required this.data});

     @override
     Widget build(BuildContext context) {
       List<charts.Series<ChartData, String>> series = [];
       for (var element = 0; element < data.length; element++) {
         series.add(
           charts.Series(
             id: data[element].first.id,
             data: data[element],
             domainFn: (ChartData series, _) => series.year,
             measureFn: (ChartData series, _) => series.sales,
             colorFn: (ChartData series, _) => series.barColor,
           ),
         );
       }
       return Container(
         height: 300,
         padding: const EdgeInsets.all(20),
         child: Card(
           child: Column(
             children: [
               Text(
                 'World of Flutter Subscribers by Year',
                 style: Theme.of(context).textTheme.headlineSmall,
               ),
               Expanded(
                 child: charts.BarChart(series,
                   animate: true,
                   barGroupingType: charts.BarGroupingType.grouped,
                   vertical: true, // 'false' in horizontal
                   behaviors: [
                     charts.SeriesLegend(
                       position: charts.BehaviorPosition.bottom,
                     ),
                   ],
                   defaultRenderer: charts.BarRendererConfig(
                     // By default, bar renderer will draw rounded bars with a constant radius of 100.
                     // To not have any rounded corners, use [NoCornerStrategy]
                     // To change the radius of the bars, use [ConstCornerStrategy]
                     cornerStrategy: const charts.ConstCornerStrategy(10),
                   ),
                   primaryMeasureAxis: const charts.NumericAxisSpec(
                     tickProviderSpec: charts.BasicNumericTickProviderSpec(
                       desiredTickCount: 5,
                     ),
                   ),
                 ),
               ),
             ],
           ),
         ),
       );
     }
   }
   ```

4. Add example data of saling to code and show ChartsFlutter in body
`dart
    class _MyHomePageState extends State<MyHomePage> {
      final desktopSalesData = [
        ChartData(
          id: 'Desktop',
          year: '2014',
          sales: 5,
          barColor: charts.ColorUtil.fromDartColor(Colors.blue),
        ),
        ChartData(
          id: 'Desktop',
          year: '2015',
          sales: 25,
          barColor: charts.ColorUtil.fromDartColor(Colors.blue),
        ),
        ChartData(
          id: 'Desktop',
          year: '2016',
          sales: 100,
          barColor: charts.ColorUtil.fromDartColor(Colors.blue),
        ),
        ChartData(
          id: 'Desktop',
          year: '2017',
          sales: 75,
          barColor: charts.ColorUtil.fromDartColor(Colors.blue),
        ),
      ];
      final tabletSalesData = [
        ChartData(
          id: 'Tablet',
          year: '2014',
          sales: 25,
          barColor: charts.ColorUtil.fromDartColor(Colors.red),
        ),
        ChartData(
          id: 'Tablet',
          year: '2015',
          sales: 50,
          barColor: charts.ColorUtil.fromDartColor(Colors.red),
        ),
        ChartData(
          id: 'Tablet',
          year: '2016',
          sales: 10,
          barColor: charts.ColorUtil.fromDartColor(Colors.red),
        ),
        ChartData(
          id: 'Tablet',
          year: '2017',
          sales: 20,
          barColor: charts.ColorUtil.fromDartColor(Colors.red),
        ),
      ];
      final mobileSalesData = [
        ChartData(
          id: 'Mobile',
          year: '2014',
          sales: 10,
          barColor: charts.ColorUtil.fromDartColor(Colors.yellow),
        ),
        ChartData(
          id: 'Mobile',
          year: '2015',
          sales: 15,
          barColor: charts.ColorUtil.fromDartColor(Colors.yellow),
        ),
        ChartData(
          id: 'Mobile',
          year: '2016',
          sales: 50,
          barColor: charts.ColorUtil.fromDartColor(Colors.yellow),
        ),
        ChartData(
          id: 'Mobile',
          year: '2017',
          sales: 45,
          barColor: charts.ColorUtil.fromDartColor(Colors.yellow),
        ),
      ];
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          body: Center(
            child: ChartsFlutter(
              data: [desktopSalesData, tabletSalesData, mobileSalesData],
            ),
          ),
        );
      }
    }
    `
</details>
<hr>
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
<hr>
</details>

<details><summary>Flutter Firebase</summary>
<hr>
<details><summary>What is Firebase?</summary>
1.  Firebase คือ ฐานข้อมูลประเภท NoSQL ซึ่งไม่ใช้ภาษา SQL ในการจัดการข้อมูล ถูกออกแบบให้มีความยืดหยุ่นต่อการใช้งานและเน้นความรวดเร็วในการใช้งาน มีการเก็บข้อมูลในรูปแบบของ JSON ทำให้สามารถเพิ่มข้อมูลไปใน Object ใดๆ ก็ได้ แต่จะไม่สามารถเก็บเป็น Array ได้ ถ้าต้องการเพิ่มข้อมูลแบบอาร์เรย์จะต้องใช้การ Put ข้อมูลเข้าไปต่อท้ายเรื่อยๆ และจะมีการสร้าง Key ไว้ใช้สำหรับการอ้างอิง
2.  โครงสร้างการเก็บข้อมูลบน Cloud Firebase จะมีการเก็บแบบ Document Database ทั้งหมด 3 ส่วน คือ
    - Collection : เป็นเหมือน Folder ที่ไว้เก็บเอกสาร และมีชื่อบอกว่าเก็บเอกสารเกี่ยวกับอะไร
    - Document : เป็นเหมือนกระดาษไว้สำหรับเก็บข้อมูล โดยเก็บข้อมูลเป็น Object มีชื่อบอกว่าเก็บข้อมูลเกี่ยวกับอะไร และยังสามารถเก็บ Folder (Collection) ได้อีกด้วย
    - Data : เป็นที่เก็บข้อมูล
3.  รูปแบบของข้อมูลบน Firestore
    - String
    - Number
    - Boolean
    - Map
    - Array
    - Null
    - Timestamp
    - Geopoint
4.  ขั้นตอนการสร้างโปรเจค Firebase

    1. สร้าง Account ที่ https://firebase.google.com/
    2. สร้างโปรเจคใหม่ คลิก Add Project ตั้งชื่อ Project แล้วคลิก Continue
    3. ปิด Google Analytics for this project แล้วคลิก Create project
    4. ทำการ Register App ตามระบบปฏิบัติการที่ใช้ โดยสามารถเลือกใช้ Flutter ได้ด้วย จากนั้นทำการติดตั้งตามคำแนะนำ ซึ่งจะช่วยให้การติดตั้งสะดวกมากขึ้น
    5. ในขั้นตอนการติดตั้ง Firebase for Flutter จะต้องทำการสร้าง Flutter Project ก่อนเพื่อให้การ Register สามารถทำกับ Project ที่ต้องการได้ทันที
    6. ใน Android ต้องทำการ config values accessible to Firebase SDKs ใน Root-level (project-level) Gradle file (<project>/build.gradle):
       ```
       buildscript {
         repositories {
           // Make sure that you have the following two repositories
           google()  // Google's Maven repository
           mavenCentral()  // Maven Central repository
         }
         dependencies {
           ...
           // Add the dependency for the Google services Gradle plugin
           classpath 'com.google.gms:google-services:4.3.15'
         }
       }
       allprojects {
         ...
         repositories {
           // Make sure that you have the following two repositories
           google()  // Google's Maven repository
           mavenCentral()  // Maven Central repository
         }
       }
       ```

    และ add both the google-services plugin and any Firebase SDKs that you want to use ใน Module (app-level) Gradle file (<project>/<app-module>/build.gradle):

        ```
          plugins {
            id 'com.android.application'
            // Add the Google services Gradle plugin
            id 'com.google.gms.google-services'
            ...
          }
          dependencies {
            // Import the Firebase BoM
            implementation platform('com.google.firebase:firebase-bom:31.2.3')
            // TODO: Add the dependencies for Firebase products you want to use
            // When using the BoM, don't specify versions in Firebase dependencies
            // https://firebase.google.com/docs/android/setup#available-libraries
          }

        ```

5.  การเชื่อมโยง Firebase Authentication เข้ามาใน Flutter Project
    1. ทำการ Login >> `firebase login`
    2. ติดตั้ง FlutterFire CLI >> `dart pub global activate flutterfire_cli` และ export path
    3. ทำการเลือก Project ใน Firebase ที่ต้องการติดตั้ง >> `flutterfire configure` พร้อมทำการ Config ตามต้องการ ตรวจสอบไฟล์ `firebase_options.dart`
    4. ติดตั้ง Package `flutter pub add firebase_core` และ `flutter pub add firebase_auth`
    5. ใน Main.dart : Add initial widget binding
       ```dart
       WidgetsFlutterBinding.ensureInitialized();
       await Firebase.initializeApp(
         options: DefaultFirebaseOptions.currentPlatform,
       );
       ```
    6. ใน auth_page.dart : ทำการ Stream ข้อมูลเพื่อตรวจสอบ โดยย้าย Login page เข้ามาใน Class หากข้อมูลที่กรอกเข้ามามีอยู่ใน firebase ให้ไปต่อ ในตัวอย่างให้ไป Homepage()
       ```dart
       body: StreamBuilder<User?>(
         stream: FirebaseAuth.instance.authStateChanges(),
         builder: (context, snapshot) {
           // User loged in
           if (snapshot.hasData) {
             return Homepage();
           }
           // User not log in
           else {
             return LoginPage();
           }
         },
       ),
       ```
    7. เปลี่ยนเส้นทางใน main.dart ไปที่ของ Loginpage() > AuthPage() แทน
    8. สร้าง User Account ใน Firebase project โดยเลือกวิธีที่ต้องการ ง่ายที่สุดให้เลือก Email/Password ทำการ Enable > Add User > กรอก email & password ที่ต้องการ
    9. ใน login_page.dart : เพิ่มฟังก์ชัน signUserIn เพื่อใช้สำหรับการส่งค่าที่กรอกจาก TextFormField เข้าไปตรวจสอบ
       ```dart
       void signUserIn(String email, String password) async {
          await FirebaseAuth.instance.signInWithEmailAndPassword(email: email, password: password);
       }
       ```
    10. ใน home_page.dart : ทำการสร้างปุ่มสำหรับการ Logout พร้อมฟังก์ชัน signOut
        ```dart
        void signOut() {
          FirebaseAuth.instance.signOut();
        }
        ```
    11. ใน home_page.dart : สามารถทำการเรียกใช้งานผู้ใช้งานที login ในปัจจุบันได้ด้วย `final user = FirebaseAuth.instance.currentUser!;`
    12. ใน login_page.dart : สามารถทำการแสดงผล loading widget ในระหว่างการโหลดข้อมูลได้ โดยใส่ไว้ใน signUserIn นอกจากนี้ทำการเช็คเงื่อนไขหากมีการกรอกรหัสผิด หรือไม่มีอยู่ในฐานข้อมูล
        ```dart
        void signUserIn(String email, String password) async {
          // show loading widget
          showDialog(
            context: context,
            builder: (context) => const Center(
              child: CircularProgressIndicator(),
            ),
          );
          // try sign in
          try {
            await FirebaseAuth.instance.signInWithEmailAndPassword(email: email, password: password);
            Navigator.pop(context);
          } on FirebaseAuthException catch (e) {
            Navigator.pop(context);
            // Wrong email
            if (e.code == 'user-not-found') {
              // print('No user found for that email');
              showDialog(context: context, builder: (context) => AlertDialog(title: Text('Incorrect email')));
            }
            // Wrong password
            else if (e.code == 'wrong-password') {
              // print('Wrong password');
              showDialog(context: context, builder: (context) => AlertDialog(title: Text('Incorrect password')));
            }
          }
          // pop the loading..
          // Navigator.pop(context);
        }
        ```
6.  การเขื่อมโยง Firebase เข้ามาใน Flutter Project

- เลือก Firebase Project ที่ต้องการ
- สร้าง Firestore Database ที่ Cloud Firestore ในแบบ test mode
- ในหน้า Cloud Firestore คลิก Create database > Start in test mode > Set Cloud Firestore location “asia-east2” > enable
- ทำการเพิ่ม App เข้าไปใน Firebase Project
- ขั้นตอนที่ 1 ของการเพิ่ม Firebase ใน Flutter App ทำตามขั้นตอนการติดตั้ง Firebase CLI ด้วย Command => curl -sL https://firebase.tools | bash
- ทดสอบการ Login ด้วย Command => firebase login
- แสดงรายการของ Firebase Project ด้วย Command => firebase projects:list
- ทำการ Initial Firebase ใน Project ด้วย Command => firebase init ซึ่งจะได้ไฟล์ firebase.json และ .firebaserc
- ขั้นตอนที่ 2 ของการเพิ่ม Firebase ใน Flutter App ใน Terminal ทำการรัน Command => dart pub global activate flutterfire_cli
- จากนั้นทำการ Config ตาม Project ด้วย Command => flutterfire configure --project=“Project Name” หลังจากทำการติดตั้งเสร็จสิ้นจะได้ไฟล์ firebase_option.dart ในโฟลเดอร์ lib
- ติดตั้ง Package Firebase_core ใน pubspec.yaml จากนั้นแก้ไขตามแต่ละ OS
  - ใน iOS Folder สั่ง => pod install
  - ใน Android ทำการแก้ไข minSDKVersion => 21 (android > app > build.gradle) และเพิ่ม multiDexEnabled true
- แก้ไข main() ให้เป็น

```dart
		Future<void> main(List<String> args) async {
  			WidgetsFlutterBinding.ensureInitialized();
  			await Firebase.initializeApp();
  			runApp(MyApp());
		}
```

- ทำการ Initial Firebase ด้วยคำสั่ง => Future<FirebaseApp> firebase = Firebase.initializeApp();
- ตรวจสอบการ Connection ใน FutureBuilder ด้วย snapshot ถ้ามี Error ให้ทำการแสดง Error
- ตรวจสอบความสมบูรณ์ของการเชื่อมต่อด้วย snapshot.connectionState == ConnectionState.done
- ติดตั้ง Package cloud_firestore
- สร้าง Collection สำหรับใช้ในการเก็บข้อมูล ด้วยคำสั่ง CollectionReference \_nameCollection = FirebaseFirestore.instance.collection(’Collection_Name’)
- ในปุ่มสำหรับการอัพโหลดข้อมูลให้ทำการเช็คการทำงานด้วย async และ await
</details>

<details><summary>Notice using Firebase?</summary>
	
- Create Flutter Project
- Create Firebase Project
- Setting Firebase Project for Your apps using Flutter
	- In terminal VSCode, type `firebase login`, `dart pub global activate flutterfire_cli`, `flutterfire configure`
 	- ติดตั้ง Package `flutter pub add firebase_core` และ `flutter pub add firebase_messaging`
- Check file `firebase_options.dart`
- Add new file `firebase_msg.dart`

```dart
import 'dart:async';
import 'dart:io';
import 'package:firebase_messaging/firebase_messaging.dart';

class FirebaseMsg {
  final FirebaseMessaging _msg = FirebaseMessaging.instance;

  Future<String> initFCM() async {
    // 1) ขอ permission
    final settings = await _msg.requestPermission(
      alert: true,
      badge: true,
      sound: true,
    );
    print('Notification permission: ${settings.authorizationStatus}');

    // 2) iOS: ตั้งให้โชว์ noti ตอน foreground (อย่างน้อย banner)
    if (Platform.isIOS) {
      await _msg.setForegroundNotificationPresentationOptions(
        alert: true,
        badge: true,
        sound: true,
      );
    }

    // 3) ดึง token แบบ retry + กันแครช
    final token = await _getFcmTokenWithRetry();
    print('FCM TOKEN => $token');

    // 4) ฟัง token เปลี่ยน (ทำจริงควรส่งขึ้น server)
    _msg.onTokenRefresh.listen((newToken) {
      print('FCM TOKEN REFRESH => $newToken');
    });

    // 5) Foreground message
    FirebaseMessaging.onMessage.listen((RemoteMessage msg) {
      print(
        'onMessage title=${msg.notification?.title} body=${msg.notification?.body}',
      );
      print('onMessage data=${msg.data}');
    });

    // 6) กดแจ้งเตือนแล้วเปิดแอป
    FirebaseMessaging.onMessageOpenedApp.listen((RemoteMessage msg) {
      print('onMessageOpenedApp data=${msg.data}');
    });

    // 7) เปิดจากปิดสนิท (terminated)
    final initial = await _msg.getInitialMessage();
    if (initial != null) {
      print('getInitialMessage data=${initial.data}');
    }
    print(token);
    return token!;
  }

  Future<String?> _getFcmTokenWithRetry() async {
    String? token;

    // iOS: ลองอ่าน APNs token ระหว่างรอ (อาจเป็น null ช่วงแรก)
    for (int i = 0; i < 20; i++) {
      try {
        // บางเครื่อง APNs token มาช้ากว่า 1-10 วิ
        final apns = Platform.isIOS ? await _msg.getAPNSToken() : null;
        if (Platform.isIOS) {
          print('APNs token try#$i => $apns');
        }

        token = await _msg.getToken(); // ✅ ต้อง await
        if (token != null && token.isNotEmpty) return token;
      } catch (e) {
        // ✅ กัน apns-token-not-set ไม่ให้แครช
        print('getToken error try#$i => $e');
      }
      await Future.delayed(const Duration(seconds: 1));
    }

    return token; // อาจยัง null ถ้า iOS config ยังไม่ครบ
  }
}
```
- Edit file `main.dart`
```dart
import 'package:firebase_core/firebase_core.dart';
import 'package:flutter/material.dart';
import 'firebase_options.dart';
import 'firebase_msg.dart';
import 'package:firebase_messaging/firebase_messaging.dart';

@pragma('vm:entry-point')
Future<void> firebaseMessagingBackgroundHandler(RemoteMessage message) async {
  await Firebase.initializeApp(options: DefaultFirebaseOptions.currentPlatform);
  // handle background data here
  print('BG message data=${message.data}');
}

Future<void> main() async {
  WidgetsFlutterBinding.ensureInitialized();

  await Firebase.initializeApp(options: DefaultFirebaseOptions.currentPlatform);

  // ✅ ตั้ง background handler ก่อน runApp
  FirebaseMessaging.onBackgroundMessage(firebaseMessagingBackgroundHandler);

  // ✅ init FCM (ไม่แครชแล้ว)
  String ms = await FirebaseMsg().initFCM();

  runApp(MyApp(ms: ms));
}

class MyApp extends StatelessWidget {
  final String ms;
  const MyApp({super.key, required this.ms});
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
          child: Padding(
            padding: const EdgeInsets.all(16.0),
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [Text('FCM Ready'), Text(ms)],
            ),
          ),
        ),
      ),
    );
  }
}

```
- For iOS, edit `Podfile` for update # platform :ios, '13.0' > '15.6'.
	- It can already run but not show Token ID. You must test app in real phone to test.
	- open project in Xcode
	- Add Push Notifications, in Runner > Target Runner > signing & capabilities > + Capability > Select Push Notifications > กด Push notification Console > Login to [developer.apple.com/account](developer.apple.com/account) > Enable Push Notifications
 	- Add Background Mode, in Runner > Target Runner > signing & capabilities > + Capability > Select Background Modes > กด Remote notifications
	- In firebase, Setting Project > Cloud Messaging > Add APNs Authentication Key from `https://developer.apple.com/account` > Certificates, IDs & Profiles > Keys > Add new Keys > Insert name and select Apple Push Notifications service (APNs) > Configure > Environment > Sandbox & Production > Save > Continue > Register > Select Key ID > Download file.p8 >  Copy Key ID and Team ID (อยู่ในหน้า Membership หรือมุมบน/รายละเอียดทีม)
	- Firebase Console → Project settings (รูปเฟือง) → Cloud Messaging → Upload .p8 in APNs Authentication Key > Insert Key ID and Team ID
	- In Xcode > Runner > Targets Runner > Build Settings > Signing > Code Signing Entitlements > change Debug, Profile, Release to `Runner/RunnerProfile.entitlements`
	- Build and Run again.
- Sent Noti message, in Firebase > Run Messaging > Create your first campaign > select Firebase Notification messages > Create > Insert Nofi title, text > Send test message > add TokenKey() and Sent
</details>

<hr>
</details>

<details><summary>Radio Button</summary>
<hr>

<details><summary>🔘 Radio Button</summary>

```dart
Radio(
    value: 1,
    groupValue: selectedRadio,
    activeColor: Colors.green,
    onChanged: (val) {
      print("Radio $val");
      setSelectedRadio(val);
    },
  ),
```

- The ‘value‘ property is the value of each radio button.
- The ‘groupValue‘ property is the value that decides whether the radio button in the group should be selected or not.
  - The button changes to selected when the ‘value‘ and ‘groupValue‘ becomes equal.
    ```dart
    setSelectedRadio(int val) {
      setState(() {
        selectedRadio = val;
      });
    }
    ```
- The ‘activeColor‘ property decides the active color of the radio button.
- The ‘onChanged‘ returns the current radio button’s value.
</details>

<details><summary>🔘 RadioListTile</summary>

- RadioListTile gives us more control over the normal one. It has additional ‘title‘ and ‘subtitle‘ property and a ‘secondary‘ widget. Here I am setting the ‘secondary‘ widget to an ElevatedButton for now.

```dart
RadioListTile(
  value: 1,
  groupValue: selectedRadioTile,
  title: Text("Radio 1"),
  subtitle: Text("Radio 1 Subtitle"),
  onChanged: (val) {
    print("Radio Tile pressed $val");
    setSelectedRadioTile(val);
  },
  activeColor: Colors.red,
  secondary: ElevatedButton(
    child: Text("Say Hi"),
    onPressed: () {
      print("Say Hello");
    },
  ),
  selected: true,
),
```

</details>

<details><summary>🔘 Radio Group Using Objects</summary>

- Create a new file named ‘user.dart’ and copy these contents.

  ```dart
  class User {
    int userId;
    String firstName;
    String lastName;

    User({this.userId, this.firstName, this.lastName});

    static List<User> getUsers() {
      return <User>[
        User(userId: 1, firstName: "Aaron", lastName: "Jackson"),
        User(userId: 2, firstName: "Ben", lastName: "John"),
        User(userId: 3, firstName: "Carrie", lastName: "Brown"),
        User(userId: 4, firstName: "Deep", lastName: "Sen"),
        User(userId: 5, firstName: "Emily", lastName: "Jane"),
      ];
    }
  }
  ```

- Once that is done. Create a List<user> inside you class and initialize in the initState method.

  ```dart
  List<user> users;

  @override
  void initState() {
    super.initState();
    users = User.getUsers();
  }

  setSelectedUser(User user) {
    setState(() {
      selectedUser = user;
    });
  }

  List<widget> createRadioListUsers() {
    List<widget> widgets = [];
    for (User user in users) {
      widgets.add(
        RadioListTile(
          value: user,
          groupValue: selectedUser,
          title: Text(user.firstName),
          subtitle: Text(user.lastName),
          onChanged: (currentUser) {
            print("Current User ${currentUser.firstName}");
            setSelectedUser(currentUser);
          },
          selected: selectedUser == user,
          activeColor: Colors.green,
        ),
      );
    }
    return widgets;
  }

  // In the build method
  Column(
    children: createRadioListUsers(),
  ),
  ```

  When the user taps each radio button in the list, it will trigger onChanged callback with the currentUser and it will set the global selectedUser object, which will match the corresponding groupValue in the list of widgets and when ‘selectedUser == user‘, that means when each radio button’s user value becomes equal to groupValue, it will become selected. The ‘selected‘ property changes the label color to the ‘activeColor‘, here it is Colors.green.

- Complete code

  ```dart
  import 'package:flutter/material.dart';
  import 'user.dart';

  class RadioWidgetDemo extends StatefulWidget {
    RadioWidgetDemo() : super();
    final String title = "Radio Widget Demo";
    @override
    RadioWidgetDemoState createState() => RadioWidgetDemoState();
  }

  class RadioWidgetDemoState extends State<RadioWidgetDemo> {
    //
    late List<User> users;
    User selectedUser = User();
    late int selectedRadio;
    late int selectedRadioTile;
    @override
    void initState() {
      super.initState();
      selectedRadio = 0;
      selectedRadioTile = 0;
      users = User.getUsers();
    }

    setSelectedRadio(int val) {
      setState(() {
        selectedRadio = val;
      });
    }

    setSelectedRadioTile(int val) {
      setState(() {
        selectedRadioTile = val;
      });
    }

    setSelectedUser(User user) {
      setState(() {
        selectedUser = user;
      });
    }

    List<Widget> createRadioListUsers() {
      List<Widget> widgets = [];
      for (User user in users) {
        widgets.add(
          RadioListTile(
            value: user,
            groupValue: selectedUser,
            title: Text(user.firstName!),
            subtitle: Text(user.lastName!),
            onChanged: (currentUser) {
              print("Current User ${currentUser!.firstName}");
              setSelectedUser(currentUser);
            },
            selected: selectedUser == user,
            activeColor: Colors.green,
          ),
        );
      }
      return widgets;
    }

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: AppBar(
          title: Text(widget.title),
        ),
        body: Column(
          mainAxisAlignment: MainAxisAlignment.start,
          children: <Widget>[
            Container(
              padding: EdgeInsets.all(20.0),
              child: Text("USERS"),
            ),
            // Radio Group Using Objects
            Column(
              children: createRadioListUsers(),
            ),
            const Divider(
              height: 20,
              color: Colors.green,
            ),
            // RadioListTile
            RadioListTile(
              value: 1,
              groupValue: selectedRadioTile,
              title: Text("Radio 1"),
              subtitle: Text("Radio 1 Subtitle"),
              onChanged: (val) {
                print("Radio Tile pressed $val");
                setSelectedRadioTile(val!);
              },
              activeColor: Colors.red,
              secondary: ElevatedButton(
                child: Text("Say Hi"),
                onPressed: () {
                  print("Say Hello");
                },
              ),
              selected: true,
            ),
            RadioListTile(
              value: 2,
              groupValue: selectedRadioTile,
              title: Text("Radio 2"),
              subtitle: Text("Radio 2 Subtitle"),
              onChanged: (val) {
                print("Radio Tile pressed $val");
                setSelectedRadioTile(val!);
              },
              activeColor: Colors.red,
              secondary: ElevatedButton(
                child: Text("Say Hi"),
                onPressed: () {
                  print("Say Hello");
                },
              ),
              selected: false,
            ),
            const Divider(
              height: 20,
              color: Colors.green,
            ),
            // Radio
            ButtonBar(
              alignment: MainAxisAlignment.center,
              children: <Widget>[
                Radio(
                  value: 1,
                  groupValue: selectedRadio,
                  activeColor: Colors.green,
                  onChanged: (val) {
                    print("Radio $val");
                    setSelectedRadio(val!);
                  },
                ),
                Radio(
                  value: 2,
                  groupValue: selectedRadio,
                  activeColor: Colors.blue,
                  onChanged: (val) {
                    print("Radio $val");
                    setSelectedRadio(val!);
                  },
                ),
              ],
            )
          ],
        ),
      );
    }
  }
  ```

- Credit : https://vipinvijayannair.medium.com/radiobuttons-radiolisttile-in-flutter-dee3013a70b1

</details>
<hr>
</details>

<details><summary>Pull to update</summary>
<hr>

1. สร้าง Function สำหรับ Fetchdata โดยเป็นการ SetState ให้กับตัวแปรหรือข้อมูลที่ใช้ในส่วนการอัพเดท
2. ใช้ RefreshIndicator ครอบส่วนที่ต้องการอัพเดท แล้วใช้ event `onRefresh` เรียกฟังก์ชัน fetchData()

```dart
 Future refresh() async {
    setState(() {
      items = ['Item{$now}', 'item5', 'item6'];
      now = DateTime.now();

      // initState();
    });

 }

 @override
 Widget build(BuildContext context) {
  return Scaffold(
    appBar: AppBar(
      title: Text('pull to refresh'),
    ),
    body: RefreshIndicator(
      onRefresh: refresh,
        child: Container(
          child: Column(
            children: [
              Text('$now'),
              Container(
                height: 200,
                child: ListView.builder(
                  itemCount: items.length,
                  itemBuilder: (context, index) {
                    return ListTile(
                      title: Text(items[index]),
                    );
                  },
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }

```

<hr>
</details>

<details><summary>Multiple Language Application</summary>
<hr>

1.  สร้างโปรเจค
2.  เพิ่ม Dependencies ทำการติดตั้ง easy_localization ใน pubspec.yaml
3.  เพิ่มโฟลเดอร์ assets หรือไฟล์คำแปล และ configure ใน pubspec.yaml
4.  เพิ่มไฟล์ภาษาต่างๆ ในรูปแบบ assets/lang/{langCode}-{countryCode}.json เช่น
    ไฟล์ภาษาอังกฤษ assets/lang/en.json

    ```json
    {
      "app": {
        "title": "Multi locale clicker",
        "changeLang": "เปลี่ยนภาษา",
        "description": "You have pushed the button this many times",
        "increment": "Increment",
        "counter": {
          "zero": "{} times",
          "one": "{} time",
          "two": "{} times",
          "other": "{} times"
        }
      }
    }
    ```

    ไฟล์ภาษาไทย assets/lang/th.json

    ```json
    {
      "app": {
        "title": "Multi locale clicker",
        "changeLang": "Change language",
        "description": "คลิกสิคลิกหลายๆที",
        "increment": "เพิ่ม",
        "counter": {
          "zero": "{} ครั้ง",
          "one": "{} ครั้ง",
          "two": "{} ครั้ง",
          "other": "{} ครั้ง"
        }
      }
    }
    ```

    Note: app.changeLang จะใช้กับปุ่มเปลี่ยนภาษา, counter ตั้งใจทำไว้เพื่อรองรับ Plural ในภาษาอังกฤษ

5.  ตั้งค่า easy_localization ลงในแอป
    ใน main.dart เพิ่ม Widget EasyLocalization มาก่อน Widget MyApp โดยเจ้า EasyLocalization จะเป็นตัวหลักในการตั้งค่า Locale ต่างๆ

    ```dart
    import 'package:flutter/material.dart';
    import 'package:easy_localization/easy_localization.dart';

    void main() async {
      WidgetsFlutterBinding.ensureInitialized();
      await EasyLocalization.ensureInitialized();

      runApp(
        EasyLocalization(
          supportedLocales: [Locale('en'), Locale('th')],
          path: 'assets/lang',
          fallbackLocale: Locale('th'),
          child: MyApp(),
        ),
      );
    }

    class MyApp extends StatelessWidget {
    ...
    ```

    เพิ่ม Localization ให้กับ MaterialApp

    ```dart
    ...
    class MyApp extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          localizationsDelegates: context.localizationDelegates,
          supportedLocales: context.supportedLocales,
          locale: context.locale,
          title: 'Flutter Demo',
          theme: ThemeData(
            primarySwatch: Colors.blue,
          ),
          home: MyHomePage(title: 'Flutter Demo Home Page'),
        );
      }
    }
    ...
    ```

    EasyLocalization จะเป็นตัวที่กำหนด context.localizationDelegates context.supportedLocales context.locale ให้ จากนั้น ใช้คำสั่ง tr('...'), '...'.tr() หรือ Text('...').tr() ในการแปลภาษา

    ```dart
    ...
    return MaterialApp(
      ...
      home: Builder(
        builder: (context) {
          return MyHomePage(
            title: tr('app.title'),
          );
        },
      ),
    );
    ...
    ```

    Note: ฟังก์ชั่น Localization ถูกสร้างที่ Widget MaterialApp ถ้าอยากจะเรียกใช้การแปลภาษาที่ MaterialApp ต้องซ้อนผ่าน Widget Builder ก่อน

    ต่อด้วย

    ```dart
    ...
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title!),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text('app.description').tr(),
            Text(
              'app.counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ).plural(_counter),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: tr('Increment'),
        child: const Icon(Icons.add),
      ),
    );
    ...
    ```

6.  เขียนส่วนตั้งค่าเปลี่ยนภาษา

    ```dart
    ...
      return Scaffold(
        appBar: AppBar(
          title: Text(widget.title),
            actions: <Widget>[
              Padding(
                padding: const EdgeInsets.symmetric(horizontal: 10.0),
                child: TextButton(
                child: Text(
                  tr('app.changeLang'),
                  style: TextStyle(color: Colors.white),
                ),
                onPressed: () => setState(() {
              if (context.locale.languageCode == 'en') {
                context.setLocale(Locale('th'));
              } else {
                context.setLocale(Locale('en'));
              }
              }),
            ),
          )
        ],
      );
    ...
    ```

<hr>
</details>

<details><summary>Call Another Application</summary>
<hr>

- Open another app from your app with package: external_app_launcher

```dart
import 'package:flutter/material.dart';
import 'package:external_app_launcher/external_app_launcher.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatefulWidget {
  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  @override
  void initState() {
    super.initState();
  }

  Color containerColor = Colors.red;

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Plugin example app'),
        ),
        body: Center(
          child: Container(
            height: 50,
            width: 150,
            child: RaisedButton(
              color: Colors.blue,
                onPressed: () async {
                  await LaunchApp.openApp(
                    androidPackageName: 'net.pulsesecure.pulsesecure',
                    iosUrlScheme: 'pulsesecure://',
                    appStoreLink: 'itms-apps://itunes.apple.com/us/app/pulse-secure/id945832041',
                    // openStore: false
                  );
                // Enter the package name of the App you want to open and for iOS add the URLscheme to the Info.plist file.
                // The `openStore` argument decides whether the app redirects to PlayStore or AppStore.
                // For testing purpose you can enter com.instagram.android
                },
                child: Container(
                  child: Center(
                    child: Text("Open",
                      textAlign: TextAlign.center,
                    ),
                  ),
                ),
              ),
            ),
          ),
        ),
      );
    }
  }

```

<hr>
</details>

<details><summary>Deploy</summary>
<hr>
	เตรียมก่อน Deploy ทำครั้งเดียว

1. อัปเดตเวอร์ชันแอป ใน pubspec.yaml
2. ตั้งค่า Icon ด้วย Package : flutter_launcher_icons แล้ว generate ให้เรียบร้อย

<hr>
	Deploy บน Android (Google Play)

1. สร้าง Keystore สำหรับเซ็นแอป (ครั้งเดียว) เก็บไฟล์ไว้ในที่ปลอดภัย (ห้ามหาย)

   ```bash
	keytool -genkey -v -keystore upload-keystore.jks -keyalg RSA -keysize 2048 -validity 10000 -alias upload
   ```
   
2. ผูก Keystore ในโปรเจกต์

	- สร้างไฟล์ android/key.properties

		```
	 	storePassword=YOUR_STORE_PASSWORD
	 	keyPassword=YOUR_KEY_PASSWORD
	 	keyAlias=upload
	 	storeFile=../upload-keystore.jks
	  	```
  
	- Build แบบ Release
		```
  		flutter build appbundle --release
		```

3. อัปโหลดขึ้น Google Play Console
   	- เข้า Google Play Console → Create app
   	- Set up รายการสำคัญ:
   		- App details, Privacy Policy URL
   	 	- Content rating
   	  	- Data safety (สำคัญมาก)
   	  	- Target audience
   	- ไปที่ Production (หรือ Internal testing ก่อน) → Create new release
   	- อัปโหลด app-release.aab
   	- ส่งตรวจ (Review) แล้วรออนุมัติ

<hr>
	Deploy บน iOS (App Store)

1. สิ่งที่ต้องมี
   - macOS + Xcode
   - Apple Developer Program
   - เปิดโปรเจกต์ iOS ด้วย:
2. 

</details>

<details><summary>Run in iOS</summary>
<hr>
	Flutter app without my usb cable connected

    flutter run --release

<hr>
</details>

<details><summary>Exercise</summary>
<hr>

<p align="center">
  <img src='images/Flutter_Excersise_Output.png'>
</p>

<details><summary>🔡 Exercise 1 : Get Template</summary>
<hr>

1. Open VS code
2. Open Terminal
3. Clone template project
   ```shell
   git clone -b training_branch https://github.com/BoonyasithKho/project_template_flutter training_excersice
   ```
4. Open directory and install flutter rename package
   ```shell
   flutter pub global activate rename
   ```
5. Rename Application
   ```shell
   flutter pub global run rename setAppName --targets ios,android --value "training_exercise"
   flutter pub get
   ```
6. In terminal type command:
   ```shell
   flutter run
   ```
7. Open project folder and try to change theme color.
8. ทำความเข้าใจ code ในแต่ละส่วน
</details>

<details><summary>🔡 Exercise 2 : Basic</summary>
<hr>

1. Create new screen `first_screen.dart` in folder 'screen'
2. Create class `FirstScreen` as a statefulwidget
3. Create Scaffold widget
   ```dart
   Scaffold();
   ```
   Add AppBar
   ```dart
   appBar: AppBar(
     title: ShowTitle(
       title: 'First Page',
       textStyle: Theme.of(context).textTheme.displayLarge,
     ),
     backgroundColor: Theme.of(context).primaryColor,
   ),
   ```
   Add Body
   ```dart
   body: Center(
     child: Text('data'),
   ),
   ```
4. In main.dart : add `'/firstScreen': (context) => const FirstScreen(),`
5. In my_constant.dart : Add `static String routeFirstScreen = '/firstScreen';`
6. In landing_page.dart : Create button `First Screen`, onpressed `print('Go to First Screen');`
7. Add `Navigator.pushNamed(context, MyConstant.routeFirstScreen);`
8. In FirstScreen > Add Row Widget 2 children :
   - Add Container Color yellow
   - Add Column 4 children (image1, image2, image3, image4)
9. Add text widget `Your name` in Yellow box and set center
10. Add space between item
11. Print 'Your name' in debug console when the yellow box was tapped.
</details>

<details><summary>🔡 Exercise 3 : Show Map</summary>
<hr>

1. Create new page `SecondScreen`
2. Create button `Second Screen` in landing page, onpressed `print('Go to Second Screen');`
3. Update route in main.dart, my_constant.dart, landing_page.dart
4. Start Debug
5. Add package flutter_map (lastest version), latlong2 (lastest version) to pubspec.yaml and save
6. In class SecondScreen add flutter map in scafold widget
   ```dart
   FlutterMap(options: MapOption())
   ```
7. Set MapOption
   center = `'your location'`
   zoom level = `6`
   max zoom level = `20`
   default map layer = `'https://tile.openstreetmap.org/{z}/{x}/{y}.png'`
8. Change map layer to sphere map layer and google map layer

> Sphere Basemap > 'https://basemap.sphere.gistda.or.th/tiles/sphere_streets/EPSG3857/{z}/{x}/{y}.png?key=test2022'

    Sphere Satellite > 'https://basemap.sphere.gistda.or.th/tiles/thailand_images/EPSG3857/{z}/{x}/{y}.jpeg?key=test2022'
    Google Basemap > 'https://mt1.google.com/vt/lyrs=r&x={x}&y={y}&z={z}'
    Google Satellite > 'https://mt1.google.com/vt/lyrs=y&x={x}&y={y}&z={z}'

9. Add FloatingActionButton for zoom in (level 18) and zoom out (level 6) when tap
10. Add Marker Layer to show your location on map
11. Add Button on map for select/switch basemap - Create new list with url of 2 basemaps - Create new list with tms
</details>

<details><summary>🔡 Exercise 4 : Get Data From API</summary>
<hr>

1. Create new page `ThirdScreen`
2. Create button `Third Screen` in landing page, onpressed `print('Go to Third Screen');`
3. Update route in main.dart, my_constant.dart, landing_page.dart
4. Start Debug
5. Add package http (lastest version) to pubspec.yaml and save
6. In class ThirdScreen add AppBar and body with [FutureBuilder widget](https://medium.com/pnpsolution/%E0%B8%A7%E0%B8%B4%E0%B8%98%E0%B8%B5%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%83%E0%B8%8A%E0%B9%89-futurebuilder-%E0%B9%83%E0%B8%99-flutter-aa9c960c9341)
   ```dart
   FutureBuilder(
     future: getData(),
     builder: (BuildContext context, AsyncSnapshot<dynamic> snapshot) {
       if (snapshot.connectionState == ConnectionState.waiting) { // snapshot.data == null
         return Container(
           child: const Center(
             child: Text('Loading...'),
           ),
         );
       } else {
         if (snapshot.connectionState == ConnectionState.done) {
           for (var i = 0; i < snapshot.data.length; i++) {
             Map<String, dynamic> map = jsonDecode(snapshot.data[i].geojson);
             allLocPoint.add(map['coordinates']);
           }
           return ListView.builder(
             itemCount: snapshot.data.length,
             itemBuilder: (context, index) {
               return ListTile(
                 leading: Text(snapshot.data[index].id.toString()),
                 title: Text('สถานี ${snapshot.data[index].stationname} จ.${snapshot.data[index].province}'),
                 subtitle: Text('พิกัด : ${allLocPoint[index].toString()}'),
                 trailing: Text('${snapshot.data[index].rainfallValue} ${snapshot.data[index].rainfallUnit}'),
               );
             },
           );
         }
       }
       return const LinearProgressIndicator();
     },
   ),
   ```
7. Create method for get data from API `getData()`
   ```dart
   Future getData() async {
     var response = await http.get(Uri.parse(MyConstant.domain));
     var jsonData = jsonDecode(response.body);
     List<APIData> apiData = [];
     for (var u in jsonData) {
       APIData _getData = APIData(u["id"].toInt(), u["geom"], u["descriptio"], DateTime.parse(u["time"]), u["copyright"], u["province"], u["stationnam"], u["rainfall_v"].toInt(),
           u["rainfall_u"], u["temperatur"].toInt(), u["temperat_1"], u["geojson"]);
       apiData.add(_getData);
     }
     // print(apiData.length);
     return apiData;
   }
   ```
8. Get Json data from your API and add to List<APIData> (note: You must to create model folder which include `apidata_model.dart`)
9. In `apidata_model.dart` create class APIData which has all column name from your API and make constructor (note: constructor เป็น Method ที่มีชื่อเดียวกับ Class โดยจะใช้กำหนดค่าเริ่มต้นให้กับ Class ที่เป็น Instance โดย Constructor จะถูกเรียกใช้งานอัตโนมัติ และจะต้องทำการ ใส่ค่า Parameters ตามจำนวน Argument ของ Constructor Class นั้น ๆ)

   ```dart
    class APIData {
       final int id;
       final String geom;
       final String description;
       final DateTime time;
       final String copyright;
       final String province;
       final String stationname;
       final int rainfallValue;
       final String rainfallUnit;
       final int temperatureValue;
       final String temperatureUnit;
       final String geojson;

       APIData(this.id, this.geom, this.description, this.time, this.copyright, this.province, this.stationname, this.rainfallValue, this.rainfallUnit, this.temperatureValue,
           this.temperatureUnit, this.geojson);
     }
   ```

10. Create FloatingActionButton for print location of all points in console and popup dialog of number record.
`dart
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          print(allLocPoint);
          MyDialog().normalDialog(context, 'จำนวนข้อมูล', '${apiData.length} Records');
        },
        child: const Icon(Icons.outbond),
      ),
      `
</details>

<details><summary>🔡 Exercise 5 : Web map and API Data</summary>
<hr>

1. Create new page `FourthScreen`
2. Create button `Fourth Screen` in landing page, onpressed `print('Go to Fourth Screen');`
3. Update route in main.dart, my_constant.dart, landing_page.dart
4. Start Debug
5. In class FourthScreen show basemap like Third Screen with button
6. Change icon in bottom right button to Icons.refresh with onpressed `mapController.move(location, 6.0);`
   ```dart
   floatingActionButton: FloatingActionButton.small(
     onPressed: () {
       setState(() {
         mapController.move(location, 6.0);
       });
     },
     child: Icon(
       Icons.refresh,
       color: Theme.of(context).iconTheme.color,
     ),
   ),
   ```
7. Get API Service for create list of marker like Forth Screen

   ```dart
   Future getData() async {
     var response = await http.get(Uri.parse(MyConstant.domain));
     var jsonData = jsonDecode(response.body);

     for (var u in jsonData) {
       // defined u["..."] follow your api field
       APIData getData = APIData(u["id"].toInt(), u["geom"], u["descriptio"], DateTime.parse(u["time"]), u["copyright"], u["province"], u["stationnam"], u["rainfall_v"].toInt(), u["rainfall_u"], u["temperatur"].toInt(), u["temperat_1"], u["geojson"]);
       apiData.add(getData);
     }

     for (var i = 0; i < apiData.length; i++) {
       Map<String, dynamic> map = jsonDecode(apiData[i].geojson);
       allLocPoint.add(map['coordinates']);
     }

     Timer(const Duration(seconds: 1), () {
       getmarkers();
     });
   }

   List<Marker> getmarkers() {
     for (var i = 0; i < apiData.length; i++) {
       List allLocPoints = [];
       Map<String, dynamic> map = jsonDecode(apiData[i].geojson);
       allLocPoints = map['coordinates'];

       setState(
         () {
           var pointMarker = LatLng(allLocPoints[1].toDouble(), allLocPoints[0].toDouble());
           markers.add(
             Marker(
               point: pointMarker,
               builder: (context) => const Icon(Icons.location_pin, color: Colors.green),
             ),
           );
         },
       );
     }
     return markers;
   }
   ```

8. Create Popup when tap on marker using `show_markerpopup.dart` in widgets folder for creat tooltip/popup of marker

   ```dart
   import 'package:flutter/material.dart';
   import 'package:flutter/src/widgets/framework.dart';
   import 'package:flutter/src/widgets/placeholder.dart';

   import '../utils/my_theme.dart';

   class ShowMarkerPopup extends StatefulWidget {
     final Widget child;
     final String? tooltip;
     final Function onTap;

     const ShowMarkerPopup({super.key, required this.child, this.tooltip, required this.onTap});

     @override
     State<ShowMarkerPopup> createState() => _ShowMarkerPopupState();
   }

   class _ShowMarkerPopupState extends State<ShowMarkerPopup> {
     final key = GlobalKey();
     @override
     Widget build(BuildContext context) {
       return InkWell(
         onTap: () {
           dynamic tooltip = key.currentState;
           tooltip.ensureTooltipVisible();
           widget.onTap();
         },
         enableFeedback: true,
         child: Container(
           child: Tooltip(
             key: key,
             message: widget.tooltip,
             textStyle: Theme.of(context).textTheme.bodyLarge,
             padding: const EdgeInsets.all(8.0),
             decoration: BoxDecoration(
               color: Theme.of(context).primaryColor,
               borderRadius: BorderRadius.circular(8.0),
             ),
             child: widget.child,
           ),
         ),
       );
     }
   }
   ```

9. Change builder in marker.add() with
   ```dart
   builder: (context) {
     return ShowMarkerPopup(
       tooltip:
         'Station name: ${apiData[i].stationname}\nTemperature : ${apiData[i].temperatureValue} ${apiData[i].temperatureUnit}\nRain Volumn : ${apiData[i].rainfallValue}  ${apiData[i].rainfallUnit}',
       onTap: () {},
       child: const Icon(
         Icons.location_on_rounded,
         size: 20,
         color: Colors.blue,
         shadows: [
           BoxShadow(
             color: Colors.black,
             blurRadius: 10.0,
           ),
         ],
       ),
     );
   },
   ```
10. Tap on marker
11. Add Web Map Service to show
`dart
      TileLayer(
        wmsOptions: WMSTileLayerOptions(
          baseUrl:
            'https://gistdaportal.gistda.or.th/data/rest/services/GFlood/GFlood_Inno_WMS_FloodArea/MapServer/export?dpi=96&transparent=true&format=png32&bboxSR=102100&imageSR=102100&f=image&layers=0',
          ),
          minZoom: 6,
          opacity: 0.5,
          backgroundColor: Colors.transparent,
      ),
      `
</details>

<details><summary>🔡 Exercise 6 : Webview</summary>
<hr>

1. Create new page `FifthScreen`
2. Create button `Fifth Screen` in landing page, onpressed `print('Go to Fifth Screen');`
3. Update route in main.dart, my_constant.dart, landing_page.dart
4. Start Debug
5. Add package webview_flutter (lastest version) to pubspec.yaml and save
6. In class FifthScreen add WebViewWidget in scafold widget
   ```dart
   Scaffold(
       body: SafeArea(
         child: Stack(
           children: [
             WebViewWidget(
               controller: controller,
             ),
           ],
         ),
       ),
   );
   ```
7. Create initial state for controller and set Url from website to show in app
   ```dart
     @override
     void initState() {
       controller = WebViewController();
       super.initState();
       controller.setJavaScriptMode(JavaScriptMode.unrestricted);
       controller.loadRequest(
         Uri.parse('your url'),
       );
     }
   ```
8. Add parameter controller
   ```dart
   late final WebViewController controller;
   ```
9. Test your webview widget
</details>

</details>
