Azure AD B2C Embedded Webview
============================

Azure AD B2C Embedded Webview is a very simple sample that demonstrates how to use the embedded web view to sign in users with Azure AD B2C.
Currently, using Azure AD B2C redirects to browser. This package embeds the webview using flutter's appview and redirects the user as per onRedirect callback.

## Features

Embedded web view for Azure AD B2C
Redirects to the route specified in redirectRoute after successful sign in
Successfully secures the token in the app using flutter secure storage
Navigates to screen in app after successful sign in

## Getting started
To use the package in your Flutter app, add the following code to your main.dart file:
```yaml
dependencies:
  aad_b2c_webview: ^0.0.1
```

## Usage

Example added in aad_b2c_webview/aad_b2c folder

```dart
@override
Widget build(BuildContext context) {
  return MaterialApp(
    title: 'Flutter Demo',
    theme: ThemeData(
      primaryColor: const Color(0xFF2F56D2),
      textTheme: const TextTheme(
        headlineLarge: TextStyle(
          color: Colors.black,
          fontSize: 32,
          fontWeight: FontWeight.w700,
          fontFamily: 'UberMove',
        ),
        bodyText1: TextStyle(
          color: Color(0xFF8A8A8A),
          fontSize: 17,
          fontWeight: FontWeight.w400,
          fontFamily: 'UberMoveText',
        ),
        headline2: TextStyle(
          fontSize: 18,
          color: Colors.black,
          fontWeight: FontWeight.w700,
          fontFamily: 'UberMove',
        ),
      ),
    ),
    debugShowCheckedModeBanner: false,
    initialRoute: '/',
    routes: {
      // When navigating to the "/" route, build the Create Account widget.

      '/': (context) => const ADB2CEmbedWebView(
        url: '<user_flow_endpoint>',
        redirectUrl: '<redirect_uri_of_user_flow>',
        redirectRoute: '<route_to_redirect_to_after_sign_in>',
        onRedirect: onRedirect,
      ),
    },
  );
}
```
