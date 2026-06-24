# HTTP

You must add `http: ^1.1.0` to your `pubspec.yaml` and import it using import `'package:http/http.dart' as http;`. 

## GET Request Example:

```bash
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> fetchData() async {
  final response = await http.get(Uri.parse('https://jsonplaceholder.typicode.com/posts/1'));
  if (response.statusCode == 200) {
    final data = json.decode(response.body);
    print(data);
  } else {
    throw Exception('Failed to load data');
  }
}
```

## POST Request Example:

```bash
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> postData() async {
  final response = await http.post(
    Uri.parse('https://jsonplaceholder.typicode.com/posts'),
    headers: {'Content-Type': 'application/json'},
    body: json.encode({'title': 'foo', 'body': 'bar', 'userId': 1}),
  );
  if (response.statusCode == 201) {
    print('Post created successfully');
  } else {
    throw Exception('Failed to create post');
  }
}
```
