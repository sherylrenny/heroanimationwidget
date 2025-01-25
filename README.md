# heroanimationwidget
# how to inculcate hero animation in your code.
import 'package:flutter/material.dart';
import 'package:flutter/material.dart';
void main() {// The main function is the entry point of the Flutter app.
  runApp(const MyApp()); // Runs the app starting with the MyApp widget.
}
class MyApp extends StatelessWidget { //MyApp is the root widget of the app.
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      debugShowCheckedModeBanner: false, // Removes the debug banner from the app.
      home: HeroFirstScreen(), // Sets the first screen of the app.
    );
  }
}
class HeroFirstScreen extends StatelessWidget { // The first screen where the user starts.
  const HeroFirstScreen({super.key});
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Hero Demo - Screen 1')), // Title of the app bar.
      body: Center(
        child: GestureDetector(// Detects taps on the widget.
          onTap: () { // When tapped, navigate to the second screen.
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => HeroSecondScreen()),
            );
          },
          child: Hero(
            tag: 'hero-tag', //Unique identifier to link Hero widgets between screens.
            child: Container(
              width: 100, 
              height: 100, 
              decoration: BoxDecoration(
                color: Colors.blue, 
                borderRadius: BorderRadius.circular(10), 
              ),
              child: const Icon(
                Icons.airplanemode_active_outlined,
                size: 30.0, 
              ),
            ),
          ),
        ),
      ),
    );
  }
}

class HeroSecondScreen extends StatelessWidget {//The second screen that the user navigates to.
  const HeroSecondScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Hero Demo - Screen 2')), // Title of the app bar.
      body: Center(
        child: Hero(
          tag: 'hero-tag', 
          child: Container(
            width: 200, // (larger than the first screen).
            height: 200, //(larger than the first screen).
            decoration: BoxDecoration(
              color: Colors.red, 
              borderRadius: BorderRadius.circular(20), // More rounded corners than the first screen.
            ),
            child: const Icon(
              Icons.flight_takeoff,
              size: 40,
            ),
          ),
        ),
      ),
    );
  }
}
