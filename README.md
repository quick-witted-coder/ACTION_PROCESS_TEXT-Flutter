# ACTION_PROCESS_TEXT Flutter

A flutter plugin for ACTION_PROCESS_TEXT implementation in android.

## What is it used for?

It can be used when you want your users to use a shortcut for opening your app when selecting text anywhere in the android environment.


![](https://i.postimg.cc/Jn53nQFV/action-process-texttest.gif) ![](https://i.postimg.cc/hvqSCL4j/slanganorytest.gif)

## Constraints

###   1. It works only for android.
###   2. It can only be used inside a Stateful widget.
###   3. Use setState() after updating the value from the action.

## Include in your project

```yaml
dependencies:
  action_process_text: <latest version>
```

Run pub get and get packages.

Add this to `AndroidManifest.xml` in the `android\app\src\main\` folder.
```xml
  <activity android:name="com.example.action_process_text.ActionProcessTextPlugin"
            android:label="Action_Text" android:theme="@style/LaunchTheme">
            <intent-filter>
                <action android:name="android.intent.action.PROCESS_TEXT" />
                <data android:mimeType="text/plain"/>
                <category android:name="android.intent.category.DEFAULT" />
            </intent-filter>
   </activity>
```
Change the `android:label` to the action text that you want.

Then import the package to use it.

```dart
import 'package:action_process_text/action_process_text.dart';
```
## Usage

Use the constructor of the widget to initialize the action_process_text.
`ActionProcessText.getInputText` is used to get the selected text from the android action.

```dart
class MainPage extends StatefulWidget {
  @override
  _MainPageState createState() => _MainPageState();
}

class _MainPageState extends State<MainPage> {
  _MainPageState() {
    initActionProcessText();
  }

  Future<void> initActionProcessText() async {
    inputText = await ActionProcessText.getInputText;
    setState(() {});
  }

  String inputText = '';

  @override
  Widget build(BuildContext context) {
    return Scaffold();
  }
  }
```

## Bugs/Requests

If you encounter any problems feel free to open an issue.
Pull request are also welcome.
