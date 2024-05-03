#OOP Mid-2 3 Programs 

## Write a program that displays the color of a circle as red when the mouse button is pressed and as white when the mouse button is released.
```Java Q-10 Unit 7&8
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;
import javafx.stage.Stage;

public class CircleColorChangeApp extends Application {
    @Override
    public void start(Stage primaryStage) {
        double width = 400;
        double height = 400;

        Circle circle = new Circle(width / 2, height / 2, Math.min(width, height) / 10, Color.WHITE);
        circle.setStroke(Color.BLACK);

        StackPane pane = new StackPane(circle);
        pane.setOnMousePressed(e -> circle.setFill(Color.RED));
        pane.setOnMouseReleased(e -> circle.setFill(Color.WHITE));

        primaryStage.setScene(new Scene(pane, width, height));
        primaryStage.setTitle("Circle Color Change");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

## Write a program that displays a tic-tac-toe board. A cell may be X, O, or empty. What to display at each cell is randomly decided. The X and O are images in the files X.gif and O.gif.

```Java Q-11 Unit 7&8
import javafx.application.Application;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.layout.GridPane;
import javafx.stage.Stage;

public class TicTacToe extends Application {
    @Override
    public void start(Stage primaryStage) {
        GridPane pane = new GridPane();
        pane.setAlignment(Pos.CENTER);

        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                int random = (int) (Math.random() * 3);
                String cellText = (random == 0) ? "X" : (random == 1) ? "O" : "";
                Label cellLabel = new Label(cellText);
                cellLabel.setStyle("-fx-font-size: 24px; -fx-border-color: black;");
                pane.add(cellLabel, j, i);
            }
        }

        Scene scene = new Scene(pane, 150, 150);
        primaryStage.setTitle("Tic Tac Toe");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

## Creating a Calculator using JavaFX

```Java Q-12 Unit 7&8
import javafx.application.Application;
import javafx.geometry.Pos;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.control.TextField;
import javafx.scene.layout.GridPane;
import javafx.stage.Stage;

public class SimpleCalculator extends Application {
    private TextField displayField;

    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("Simple Calculator");

        // Create the display field
        displayField = new TextField();
        displayField.setAlignment(Pos.CENTER_RIGHT);
        displayField.setEditable(false);

        // Create buttons for digits and operators
        Button[] digitButtons = new Button[10];
        for (int i = 0; i < 10; i++) {
            digitButtons[i] = new Button(Integer.toString(i));
            digitButtons[i].setOnAction(e -> appendToDisplay(Integer.toString(i)));
        }

        Button addButton = createOperatorButton("+");
        Button subtractButton = createOperatorButton("-");
        Button multiplyButton = createOperatorButton("*");
        Button divideButton = createOperatorButton("/");

        Button clearButton = new Button("C");
        clearButton.setOnAction(e -> clearDisplay());

        Button equalsButton = new Button("=");
        equalsButton.setOnAction(e -> evaluateExpression());

        // Create the grid layout
        GridPane grid = new GridPane();
        grid.setAlignment(Pos.CENTER);
        grid.setHgap(10);
        grid.setVgap(10);

        // Add buttons to the grid
        grid.add(displayField, 0, 0, 4, 1);
        grid.addRow(1, digitButtons[7], digitButtons[8], digitButtons[9], addButton);
        grid.addRow(2, digitButtons[4], digitButtons[5], digitButtons[6], subtractButton);
        grid.addRow(3, digitButtons[1], digitButtons[2], digitButtons[3], multiplyButton);
        grid.addRow(4, clearButton, digitButtons[0], equalsButton, divideButton);

        Scene scene = new Scene(grid, 300, 250);
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    private Button createOperatorButton(String operator) {
        Button button = new Button(operator);
        button.setOnAction(e -> appendToDisplay(operator));
        return button;
    }

    private void appendToDisplay(String text) {
        displayField.appendText(text);
    }

    private void clearDisplay() {
        displayField.clear();
    }

    private void evaluateExpression() {
        try {
            String expression = displayField.getText();
            double result = evaluate(expression);
            displayField.setText(Double.toString(result));
        } catch (Exception e) {
            displayField.setText("Error");
        }
    }

    private double evaluate(String expression) {
        // Implement your own expression evaluation logic here
        // For simplicity, this example just returns the input as-is
        return Double.parseDouble(expression);
    }
}
```
## End of Programs
*You Can Check Out Other Files For More QB Solution*


![alt text](https://i.imgur.com/8Qw2VtL.png)
    
**Created By Vatsal Shah**
    
`csevatsalshah@gmail.com`
