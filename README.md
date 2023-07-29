
## OCP (Open-Closed Principle)

### Example 1: Basic Graphical Editor

#### No compliance

```java
public enum ShapeTypeEnum {
  SQUARE,
  CIRCLE
}
```

```java
public class Point {}
```

```java
public abstract class Shape {
  ShapeTypeEnum shapeType;
}
```

```java
public class Square extends Shape {
  private Point origin;

  private float width;

  private float length;
}
```

```java
public class Circle extends Shape {
  private float radius;

  private Point center;
}
```

```java
public class GraphicalEditor {
  public static void drawShape(Shape shape) {
    switch (shape.shapeType) {
      case SQUARE -> drawSquare((Square) shape);
      case CIRCLE -> drawCircle((Circle) shape);
    }
  }

  private static void drawSquare(Square square) { System.out.println("Drawing square...."); }

  private static void drawCircle(Circle circle) { System.out.println("Drawing circle...."); }
}
```
