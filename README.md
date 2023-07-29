# custom_shaped_bottom_nav_bar

<img width="300" alt="image" src="https://github.com/YamamotoDesu/custom_shaped_bottom_nav_bar/assets/47273077/95b3c636-be9a-4452-9243-df004f00376b">

```dart
class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key});

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  @override
  Widget build(BuildContext context) {
    final Size size = MediaQuery.sizeOf(context);

    return Scaffold(
      backgroundColor: Colors.white10,
      body: Stack(
        children: [
          Positioned(
            bottom: 0,
            left: 0,
            child: SizedBox(
              width: size.width,
              height: 80,
              child: Stack(
                children: [
                  CustomPaint(
                    size: Size(size.width, 80),
                    painter: BNBCustomPainter(),
                  ),
                  Center(
                    heightFactor: 0.6,
                    child: FloatingActionButton(
                      shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.circular(30.0),
                      ),
                      backgroundColor: Colors.orange,
                      elevation: 0.1,
                      onPressed: () {},
                      child:
                          const Icon(Icons.shopping_cart, color: Colors.white),
                    ),
                  ),
                  Container(
                    width: size.width,
                    height: 80,
                    child: Row(
                      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                      children: [
                        IconButton(
                          onPressed: () {},
                          icon: const Icon(Icons.home),
                        ),
                        IconButton(
                          onPressed: () {},
                          icon: const Icon(Icons.restaurant_menu),
                        ),
                        SizedBox(width: size.width * 0.20),
                        IconButton(
                          onPressed: () {},
                          icon: const Icon(Icons.bookmark),
                        ),
                        IconButton(
                          onPressed: () {},
                          icon: const Icon(Icons.notifications),
                        ),
                      ],
                    ),
                  ),
                ],
              ),
            ),
          )
        ],
      ),
    );
  }
}

class BNBCustomPainter extends CustomPainter {
  @override
  void paint(Canvas canvas, Size size) {
    Paint paint = Paint()
      ..color = Colors.white
      ..style = PaintingStyle.fill;
    Path path = Path()..moveTo(0, 20);
    path.quadraticBezierTo(size.width * 0.20, 0, size.width * 0.35, 0);
    path.quadraticBezierTo(size.width * 0.40, 0, size.width * 0.40, 20);
    path.arcToPoint(Offset(size.width * 0.60, 20),
        radius: const Radius.circular(10.0), clockwise: false);
    path.quadraticBezierTo(size.width * 0.60, 0, size.width * 0.65, 0);
    path.quadraticBezierTo(size.width * 0.80, 0, size.width, 20);
    path.lineTo(size.width, size.height);
    path.lineTo(0, size.height);
    path.close();
    canvas.drawShadow(path, Colors.black, 5, true);
    canvas.drawPath(path, paint);
  }

  @override
  bool shouldRepaint(covariant CustomPainter oldDelegate) {
    return false;
  }
}
```

<img width="376" alt="iPhone_12_Pro" src="https://github.com/YamamotoDesu/custom_shaped_bottom_nav_bar/assets/47273077/118acdd4-c10c-4577-be8f-bbace1d40070">

<img width="376" alt="iPhone_12_Pro" src="https://github.com/YamamotoDesu/custom_shaped_bottom_nav_bar/assets/47273077/38124ab4-e391-4db9-b24a-594a3d94ed8f">

<img width="376" alt="iPhone_12_Pro" src="https://github.com/YamamotoDesu/custom_shaped_bottom_nav_bar/assets/47273077/194aed66-6a23-490d-9997-f4ba66e19a2f">

<img width="376" alt="iPhone_12_Pro" src="https://github.com/YamamotoDesu/custom_shaped_bottom_nav_bar/assets/47273077/fc529ae7-8a27-48d1-81f7-a57121cc03f1">
