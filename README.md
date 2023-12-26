# Using Freezed in Flutter

This project demonstrates how to use the Freezed package for more robust and less boilerplate code in your Flutter applications.

## Overview

Freezed is a code generation package that helps in creating immutable and copyable classes with less verbose syntax. It's especially useful in state management, data models, and when working with JSON data.

## Getting Started

Before diving into Freezed, ensure you have a basic understanding of Flutter development. If this is your first Flutter project, consider going through these resources:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For comprehensive Flutter documentation, visit [Flutter online documentation](https://docs.flutter.dev/), which provides tutorials, samples, and guidance on mobile development.

### Setting Up Freezed in Your Project

To utilize Freezed, you will need to set up your Flutter project accordingly. Here are the steps:

1. **Add Dependencies**: Update your `pubspec.yaml` with the following:

   ```yaml
   dependencies:
     flutter:
       sdk: flutter
     freezed_annotation: ^[latest_version]

   dev_dependencies:
     build_runner: ^[latest_version]
     freezed: ^[latest_version]

Replace [latest_version] with the current version numbers of the respective packages.

1. Run pub get: Fetch the dependencies:
```sh
flutter pub get
```

2. Create a Freezed Model: Define your data model with the @freezed annotation. For example, create a file named user.dart:
```dart
import 'package:freezed_annotation/freezed_annotation.dart';

part 'user.freezed.dart';

@freezed
class User with _$User {
  const factory User({
    required String id,
    required String name,
    @Default(0) int age,
  }) = _User;
}

```

3. Generate Code: Run the build runner command to generate the necessary files:
```sh
flutter pub run build_runner build --delete-conflicting-outputs
```

### Using Your Freezed Model
Once you have your Freezed model, you can utilize it within your Flutter application to benefit from its features like immutability and built-in methods.
```dart
var user = User(id: '123', name: 'John Doe');
var updatedUser = user.copyWith(name: 'Jane Doe');
```

### Next Steps

Explore advanced features of Freezed, including union/sealed classes and JSON serialization.
Integrate Freezed models with state management solutions like Provider or Riverpod.
Write unit tests to ensure your models and business logic are working correctly.
Additional Resources
- [Freezed package on pub.dev](https://pub.dev/packages/freezed)
- [Effective Dart Documentation](https://dart.dev/effective-dart/documentation#:~:text=)

For help and discussions about best practices, get in touch with the Flutter community:

- [Flutter Community](https://flutter.dev/community#:~:text=URL%3A%20https%3A%2F%2Fflutter)
- [StackOverflow](https://stackoverflow.com/search?q=%5Bflutter%5D+freezed&s=b179f33d-1aa2-4cfa-ad89-26d86b5bb033)


### Happy coding with Flutter and Freezed!

