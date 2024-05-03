# OOP Mid-2 Unit 7 & 8
`Created by Vatsal Shah`
`Disclaimer - AI is Used While Making This and Add Figure in Answer Accordingly if Required`

### Q-1) Draw Architecture of JavaFX API. Explain in brief.

refer to ppt for this question best answer

JavaFX architecture comprises several layers that work together to provide a rich user interface experience. Here's a brief explanation:

1. **Hardware Acceleration Layer**: Utilizes hardware resources for rendering graphics efficiently, ensuring smooth performance.

2. **Prism Graphics Pipeline**: Prism is the rendering engine responsible for rendering 2D and 3D graphics, handling rendering, image compositing, and applying effects.

3. **Scene Graph**: Represents the visual elements of the application in a hierarchical tree structure. It contains nodes representing shapes, text, images, etc., and their transformations.

4. **FXML and Scene Builder**: FXML is an XML-based markup language for designing UI layouts. Scene Builder is a visual layout tool for creating FXML files by dragging and dropping UI components.

5. **Java API**: Provides classes and interfaces for creating and managing UI components, handling events, applying effects, etc.

6. **Media and Web Services**: Includes APIs for media playback, streaming, and web integration.

7. **CSS Styling**: Supports CSS for styling UI components, allowing developers to define the appearance of elements.

This architecture ensures flexibility, performance, and ease of development in JavaFX applications.

![alt text](https://i.imgur.com/IutLXRO.png)

### Q-2) Enlist various layout panes and explain any two in detail OR Explain different layout panes used in JavaFX.

#### Layout Panes in JavaFX:

| Layout Pane   | Description                                                                                                   |
|---------------|---------------------------------------------------------------------------------------------------------------|
| BorderPane    | Divides the layout into top, bottom, left, right, and center regions. Useful for typical application layouts. |
| VBox          | Stacks its child nodes in a single vertical column. Ideal for vertical arrangements like menus or forms.     |
| HBox          | Arranges child nodes in a single horizontal row. Suitable for horizontal layouts such as toolbars.          |
| GridPane      | Organizes child nodes in a grid of rows and columns, offering precise control over layout.                    |
| StackPane     | Stacks child nodes on top of each other, allowing only one child to be visible at a time.                      |
| AnchorPane    | Anchors child nodes to the edges of the container or specific offsets, useful for resizable layouts.          |

#### Explanation of BorderPane:

BorderPane is commonly used for typical application layouts. It divides the layout into five regions: top, bottom, left, right, and center. Components placed within a BorderPane are positioned at one of these regions, making it suitable for arranging menus, toolbars, status bars, and main content areas.

#### Explanation of GridPane:

GridPane is ideal for creating complex layouts with rows and columns. Components are placed in cells specified by row and column indices, allowing precise control over their positioning. GridPane supports spanning rows and columns, making it suitable for designing forms, tables, and structured layouts.

### Q-3) Explain Color class along with its methods.

The `Color` class in JavaFX represents colors using the RGB (Red, Green, Blue) model. Here are some methods of the `Color` class:

| Method                 | Description                                                                           |
|------------------------|---------------------------------------------------------------------------------------|
| `Color(double r, double g, double b, double opacity)` | Constructs a color with the specified RGB values and opacity.                           |
| `Color.rgb(int r, int g, int b)`                       | Creates a color from integer RGB values (0-255).                                          |
| `Color.web(String hex)`                                | Creates a color from a hexadecimal string (e.g., "#ff0000" for red).                     |
| `brighter()`                                           | Returns a brighter shade of the color.                                                    |
| `darker()`                                             | Returns a darker shade of the color.                                                      |
| `getRed()`, `getGreen()`, `getBlue()`                  | Returns the red, green, or blue component of the color as a value between 0.0 and 1.0.     |
| `getOpacity()`                                         | Returns the opacity of the color as a value between 0.0 (fully transparent) and 1.0 (opaque). |

The `Color` class provides a versatile way to represent and manipulate colors in JavaFX applications.

### Q-4) Enlist various layout panes in JavaFX and explain any two in detail.

#### Layout Panes in JavaFX:

| Layout Pane   | Description                                                                                                   |
|---------------|---------------------------------------------------------------------------------------------------------------|
| BorderPane    | Divides the layout into top, bottom, left, right, and center regions. Useful for typical application layouts. |
| VBox          | Stacks its child nodes in a single vertical column. Ideal for vertical arrangements like menus or forms.     |
| HBox          | Arranges child nodes in a single horizontal row. Suitable for horizontal layouts such as toolbars.          |
| GridPane      | Organizes child nodes in a grid of rows and columns, offering precise control over layout.                    |
| StackPane     | Stacks child nodes on top of each other, allowing only one child to be visible at a time.                      |
| AnchorPane    | Anchors child nodes to the edges of the container or specific offsets, useful for resizable layouts.          |

#### Explanation of BorderPane:

BorderPane is commonly used for typical application layouts. It divides the layout into five regions: top, bottom, left, right, and center. Components placed within a BorderPane are positioned at one of these regions, making it suitable for arranging menus, toolbars, status bars, and main content areas.

#### Explanation of GridPane:

GridPane is ideal for creating complex layouts with rows and columns. Components are placed in cells specified by row and column indices, allowing precise control over their positioning. GridPane supports spanning rows and columns, making it suitable for designing forms, tables, and structured layouts.


### Q-5) Explain following classes in JavaFX.

a) **Color class**: The `Color` class in JavaFX represents colors using the RGB (Red, Green, Blue) model. It provides methods to create and manipulate colors. You can specify colors using RGB values or hexadecimal strings. This class is commonly used for defining colors for UI elements, shapes, text, and more.

b) **Font class**: The `Font` class represents fonts in JavaFX applications. It allows you to specify the font family, size, weight, and style of text displayed in UI components. Fonts can be set for labels, buttons, text fields, and other text-based nodes to control their appearance.

c) **Image and ImageView classes**: The `Image` class represents an image in JavaFX, which can be loaded from various sources such as files, URLs, or input streams. The `ImageView` class is used to display images within a JavaFX application. You can scale, rotate, and apply other transformations to images using ImageView.

d) **Color class with methods**: The `Color` class provides methods to manipulate colors, such as `brighter()` to get a brighter shade of the color, `darker()` to get a darker shade, and methods to get the red, green, blue, and opacity components of the color. These methods are useful for adjusting the appearance of UI elements dynamically.

### Q-6) Explain mouse and key event handler in JavaFX.

In JavaFX, event handling for mouse and keyboard events is done using event handlers. Here's an overview of mouse and key event handlers:

**Mouse Event Handler**:
- Mouse events include actions like clicking, dragging, moving, entering, and exiting.
- You can handle mouse events using event handler interfaces such as `OnMouseClicked`, `OnMousePressed`, `OnMouseDragged`, etc.
- To attach a mouse event handler to a node, you can use the `setOnMouseClicked`, `setOnMousePressed`, `setOnMouseDragged`, etc. methods.

**Key Event Handler**:
- Key events are triggered when a keyboard key is pressed, released, or typed.
- Key events are handled using event handler interfaces like `OnKeyPressed`, `OnKeyReleased`, and `OnKeyTyped`.
- To handle key events, you can attach event handlers using methods like `setOnKeyPressed`, `setOnKeyReleased`, and `setOnKeyTyped`.

Example of attaching mouse event handler to a button:
```java
Button button = new Button("Click Me");
button.setOnMouseClicked(event -> {
    System.out.println("Button clicked!");
});
```

Example of attaching key event handler to a text field:
```java
TextField textField = new TextField();
textField.setOnKeyPressed(event -> {
    System.out.println("Key pressed: " + event.getCode());
});
```

### Q-7) Explain following controls

a) **TextArea**: TextArea is a multi-line text input control that allows users to enter and edit multiple lines of text. It supports features like scrolling, selection, and text wrapping. TextArea is commonly used for text editing, input forms, and displaying large amounts of text.

b) **Scrollbar**: Scrollbar is a UI control that allows users to scroll through the content of a scrollable area, such as a scroll pane or text area. It provides a visual indicator of the current position within the content and allows users to navigate to different parts of the content by dragging the scrollbar thumb or clicking the track.

c) **Checkbox**: Checkbox is a UI control that allows users to toggle between two states: checked and unchecked. It's commonly used for representing boolean options or enabling/disabling features in an application. Users can click on the checkbox to toggle its state.

d) **ComboBox**: ComboBox is a combination of a text field and a drop-down list. It allows users to select an item from a list of options or enter a custom value. ComboBox is commonly used for selecting items from a predefined list or providing autocomplete functionality.

e) **RadioButton**: RadioButton is a UI control that allows users to select one option from a group of mutually exclusive options. Radio buttons are typically used in groups where only one option can be selected at a time. Users can click on a radio button to select it, deselecting any other radio button in the same group.

f) **TextField**: TextField is a single-line text input control that allows users to enter and edit text. It's commonly used for input forms, search boxes, and other scenarios where users need to enter short amounts of text. TextField supports features like text selection, cursor navigation, and text validation.

g) **Label**: Label is a UI control used to display text or an image. It's commonly used for providing descriptions, titles, or captions for other UI components. Labels can display static text or be bound to dynamic data sources for updating their content dynamically.

### Q-8) How do you declare a generic type in a class? Explain.

In Java, you can declare a generic type in a class using angle brackets (`<>`). Generic types allow you to create classes and methods that operate on different data types while providing compile-time type safety. Here's how you declare a generic type in a class:

```java
public class MyClass<T> {
    // Class members and methods
}
```

In the above example, `T` is a type parameter that represents a placeholder for the actual type that will be specified when an instance of `MyClass` is created. You can use this type parameter within the class to define variables, methods, or return types.

For example, you can create an instance of `MyClass` specifying `Integer` as the type parameter:

```java
MyClass<Integer> integerObj = new MyClass<>();
```

Now, `T` is replaced with `Integer` throughout the class definition wherever it appears. This allows you to work with `Integer` objects within `MyClass`.

You can also use multiple type parameters in a generic class:

```java
public class Pair<K, V> {
    private K key;
    private V value;
    
    // Constructor and methods
}
```

In this case, `Pair` is a generic class with two type parameters `K` and `V`, representing the key and value types respectively.

### Q-9) Explain Event Handling Phases of JavaFX in detail.

In JavaFX, event handling occurs in multiple phases, allowing various nodes in the scene graph to process events. The event handling phases are as follows:

1. **Capturing Phase**: In this phase, the event is captured by the root node of the scene graph and propagated down to the target node. During capturing, event handlers registered on parent nodes have the opportunity to intercept and handle the event before it reaches the target node.

2. **Target Phase**: Once the event reaches the target node, it triggers event handlers registered directly on that node. This phase allows the target node to handle the event.

3. **Bubbling Phase**: After the target phase, the event bubbles up through the parent hierarchy, allowing event handlers registered on ancestor nodes to process the event. During bubbling, event handlers on parent nodes can react to the event after it has been handled by the target node.

JavaFX provides event handler interfaces for capturing, handling, and bubbling events. These interfaces include `EventHandler`, `EventTarget`, `EventDispatcher`, etc. You can register event handlers using methods like `setOn<EventName>`, where `<EventName>` represents the type of event (e.g., `setOnMouseClicked`, `setOnKeyPressed`, etc.).

Understanding event handling phases is essential for developing responsive and interactive JavaFX applications, as it allows you to control how events are processed and propagated through the scene graph.

### Q-10) Write a program that displays the color of a circle as red when the mouse button is pressed and as white when the mouse button is released.

```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;
import javafx.stage.Stage;

public class CircleColorChange extends Application {

    @Override
    public void start(Stage primaryStage) {
        Circle circle = new Circle(100, Color.WHITE);
        circle.setStroke(Color.BLACK);

        circle.setOnMousePressed(event -> circle.setFill(Color.RED));
        circle.setOnMouseReleased(event -> circle.setFill(Color.WHITE));

        StackPane root = new StackPane(circle);
        Scene scene = new Scene(root, 200, 200);

        primaryStage.setScene(scene);
        primaryStage.setTitle("Circle Color Change");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

In this program, a circle is displayed with an initial color of white. When the mouse button is pressed on the circle, its color changes to red. When the mouse button is released, the color changes back to white.

### Q-11) Write a program that displays a tic-tac-toe board. A cell may be X, O, or empty. What to display at each cell is randomly decided. The X and O are images in the files X.gif and O.gif.

```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.GridPane;
import javafx.stage.Stage;

import java.util.Random;

public class TicTacToeBoard extends Application {

    @Override
    public void start(Stage primaryStage) {
        GridPane gridPane = new GridPane();
        Random random = new Random();

        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                ImageView imageView = new ImageView();
                int randomValue = random.nextInt(3);
                String imagePath = switch (randomValue) {
                    case 0 -> "X.gif";
                    case 1 -> "O.gif";
                    default -> null;
                };
                if (imagePath != null) {
                    Image image = new Image(getClass().getResourceAsStream(imagePath));
                    imageView.setImage(image);
                }
                gridPane.add(imageView, j, i);
            }
        }

        Scene scene = new Scene(gridPane, 300, 300);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Tic Tac Toe Board");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

In this program, a tic-tac-toe board is displayed using a `GridPane`. Each cell of the grid contains either an X or O image randomly chosen. The images are loaded from files `X.gif` and `O.gif`.

### Q-12) Creating a Calculator using JavaFX

```java
// JavaFX code for Calculator goes here
```

### Q-13) Explain main predefined animations in JavaFX. Explain any of them with a suitable example.

JavaFX provides various predefined animations for creating dynamic and visually appealing effects in applications. Some of the main predefined animations include:

1. **Fade Transition**: Gradually changes the opacity of a node over a specified duration, creating a fading effect.

2. **Translate Transition**: Animates the translation (movement) of a node from one position to another.

3. **Scale Transition**: Animates the scaling (resizing) of a node, making it grow or shrink over time.

4. **Rotate Transition**: Animates the rotation of a node around a specified pivot point.

5. **Sequential Transition**: Groups multiple animations to run sequentially, one after the other.

6. **Parallel Transition**: Groups multiple animations to run simultaneously.

Example using Fade Transition:

```java
import javafx.animation.FadeTransition;
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;
import javafx.util.Duration;

public class FadeTransitionExample extends Application {

    @Override
    public void start(Stage primaryStage) {
        Button button = new Button("Fade Me");
        FadeTransition fadeTransition = new FadeTransition(Duration.seconds(2), button);
        fadeTransition.setFromValue(1.0);
        fadeTransition.setToValue(0.1);
        fadeTransition.setAutoReverse(true);
        fadeTransition.setCycleCount(FadeTransition.INDEFINITE);
        fadeTransition.play();

        StackPane root

 = new StackPane(button);
        Scene scene = new Scene(root, 300, 200);

        primaryStage.setScene(scene);
        primaryStage.setTitle("Fade Transition Example");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

In this example, a `FadeTransition` is applied to a button, causing it to fade in and out continuously. The duration of each fade cycle is 2 seconds, and the animation repeats indefinitely.

## End of Unit-7 & 8 QB
*You Can Check Out Other Files For More QB Solution*


![alt text](https://i.imgur.com/8Qw2VtL.png)
    
**Created By Vatsal Shah**
    
`csevatsalshah@gmail.com`
