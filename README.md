# example

Run in terminal : flutter pub run easy_localization:generate -f keys -o locale_keys.g.dart

## example/resources/langs/en-EN.json

```json
{
  "hi": "Hi !",
  "welcome": "Welcome {}"
}
```

Will be generated strings class like this, then you can use it without .tr(), if arguments needed will be generated args function

```dart
import 'package:easy_localization/easy_localization.dart';

// DO NOT EDIT. This is code generated via package:easy_localization/generate.dart

abstract class Strings {
  static final hi = 'hi'.tr();

  static String welcome(String arg0) {
    return 'welcome'.tr(args: [arg0]);
  }
}
```

### [example/lib/main.dart](https://github.com/aissat/easy_localization/blob/master/example/lib/main.dart)

```dart
class MyHomePage extends StatefulWidget {
  MyHomePage({Key? key, required this.title}) : super(key: key);

  final String title;

  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Container(
        child: Column(
          mainAxisSize: MainAxisSize.min,
          mainAxisAlignment: MainAxisAlignment.center,
          crossAxisAlignment: CrossAxisAlignment.center,
          children: [
            Text(Strings.hi),
            Text(Strings.welcome("Flutter")),
          ],
        ),
        alignment: Alignment.center,
      ),
    );
  }
}

```
