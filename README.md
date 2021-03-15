# flutter_common_ui
A boiler plate of flutter dart common custom made UI such as onboarding screen, registration form,  login screen and etc.

## Show some ❤️ and star the repo to support the project

## Usage 
To use this package :
add the dependency to your pubspec.yaml file.

dependencies:
    flutter:
      sdk: flutter
    intro_screen_onboarding: ^0.0.1
    
 
## How to use
## onboarding screen
 ```class TestScreen extends StatelessWidget {

  final List<Introduction> list = [
    Introduction(
      title: 'eCommerce',
      subTitle: 'Subtitle',
      imageUrl: 'your/image/directory/',

    ),
    Introduction(
      title: 'Delivery',
      subTitle: 'Your order will be immediately collected and',
      imageUrl: 'your/image/directory/',
    )
  ];

  @override
  Widget build(BuildContext context) {
    return IntroScreenOnboarding(introductionList: list, onTapSkipButton: () {
      Navigator.push(
        context,
        MaterialPageRoute(
          builder: (context) => HomePage(),
        ), //MaterialPageRoute
      );
    },);
  }
}```

## login screen
```dart
import 'package:flutter/material.dart';  
import 'package:login_/login_.dart';  
  
void main() {  
  runApp(MyApp());  
}  
  
class MyApp extends StatefulWidget {  
  //You have to create a list with the type of login's that you are going to import into your application  
  
  @override  
  _MyAppState createState() => _MyAppState();  
}  
  
class _MyAppState extends State<MyApp> {  
  @override  
  Widget build(BuildContext context) {  
  
  
    return MaterialApp(  
        title: 'Flutter Demo',  
        theme: ThemeData(  
          primarySwatch: Colors.blue,  
          visualDensity: VisualDensity.adaptivePlatformDensity,  
        ),  
        home: Scaffold(  
            body: buildLogin()));  
  }  
  
  Login buildLogin() {  
  
    List<LoginTypeLoginModel> listLogin = [  
      LoginTypeLoginModel(  
          callFunction: (BuildContext _buildContext) {  
            // develop what they want the facebook to do when the user clicks  
  },  
          logo: TypeLogo.facebook),  
      LoginTypeLoginModel(  
          callFunction: (BuildContext _buildContext) {  
            // develop what they want the Google to do when the user clicks  
  },  
          logo: TypeLogo.google),  
      LoginTypeLoginModel(  
          callFunction: (BuildContext _buildContext) {  
            print("APPLE");  
            // develop what they want the Apple to do when the user clicks  
  },  
          logo: TypeLogo.apple),  
      LoginTypeLoginModel(  
          callFunction: (BuildContext _buildContext) {  
            Navigator.of(_buildContext).push(MaterialPageRoute(  
              builder: (_buildContext) => widgetLoginUserAndPassword(),  
            ));  
          },  
          logo: TypeLogo.userPassword),  
    ];  
  
    return Login(  
            pathLogo: 'assets/logo.png',  
            isExploreApp: true,  
            functionExploreApp: () {  
              // develop what they want the ExploreApp to do when the user clicks  
  },  
            isFooter: true,  
            widgetFooter: this.widgetFooter(),  
            typeLoginModel: listLogin,  
            isSignUp: true,  
            widgetSignUp: this.widgetLoginSignUp(),  
      );  
  }  
  
  Widget widgetLoginUserAndPassword() {  
    return LoginUserAndPassword(  
              callLogin: (BuildContext _context, Function isRequest,  
                  String user, String password) {  
                isRequest(true);  
  
                Future.delayed(Duration(seconds: 2), () {  
                  print('-------------- function call----------------');  
                  print(user);  
                  print(password);  
                  print('-------------- end call----------------');  
  
                  isRequest(false);  
                });  
              },  
              logo: './assets/logo_head.png',  
              isFooter: true,  
              widgetFooter: this.widgetFooter(),  
              isResetPassword: true,  
              widgetResetPassword: this.widgetResetPassword(),  
              isSignUp: true,  
              signUp: this.widgetLoginSignUp(),  
            );  
  }  
  
  Widget widgetResetPassword() {  
    return LoginResetPassword(  
      logo: 'assets/logo_head.png',  
      funResetPassword: (BuildContext _context, Function isRequest, String email) {  
        isRequest(true);  
  
        Future.delayed(Duration(seconds: 2), () {  
          isRequest(false);  
  
        });  
      },  
  
      isFooter: true,  
      widgetFooter: this.widgetFooter(),  
    );  
  }  
  
  Widget widgetFooter() {  
    return LoginFooter(  
      logo: 'assets/logo_footer.png',  
      text: 'Power by',  
      funFooterLogin: () {  
        // develop what they want the footer to do when the user clicks  
  },  
    );  
  }  
  
  Widget widgetLoginSignUp() {  
    return LoginSignUp(  
      isFooter: true,  
        widgetFooter: this.widgetFooter(),  
        logo: 'assets/logo_head.png',  
        funSignUp: (BuildContext _context, Function isRequest,  
            SignUpModel signUpModel) {  
          isRequest(true);  
     
        });  
  }  
}
```

# Created & Maintained By
Keith Randell Gapusan
krsgapusan@gmail.com

# License
flutter_common_ui is licensed under MIT license.
