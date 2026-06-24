# DIO

Dio is a powerful HTTP client that supports interceptors, global configuration, and easy file upload/download.  

 It is often preferred for complex API integrations.

## Basic Dio GET Request

```dart
import 'package:dio/dio.dart';

final dio = Dio();
try {
  final response = await dio.get('https://jsonplaceholder.typicode.com/posts/1');
  print(response.data);
} catch (e) {
  print(e);
}
```
