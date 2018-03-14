# software-eng-quiz
import javafx.application.*;
import javafx.scene.*;
import javafx.stage.*;
import javafx.scene.layout.*;
import javafx.scene.control.*;
import javafx.event.*;
import javafx.geometry.*;

public class CheckBox extends Application {

  Label response;
  Label prompt;

  RadioButton rbq1;
  RadioButton rbq2;


  ToggleGroup tg;

  public static void main(String[] args) {
    launch(args);
  }

  // Override the start method
  public void start(Stage myStage)  {

    //Use a flowpane for the root node
    FlowPane rootNode = new FlowPane(Orientation.VERTICAL, 0, 10);
    rootNode.setAlignment(Pos.CENTER_LEFT);
    rootNode.setPadding(new Insets(0, 0, 0, 10));

    //Set a scene
    Scene myScene = newScene(rootNode, 220, 140);
    myStage.setScene(myScene);

    //Create prompting label
    prompt = new Label("Select answer");
    response = new Label("");

    //Create the radio buttons
    rbKeyboard = new RadioButton("q1");
    rbMouse = new RadioButton("q2")

    tg = new ToggleGroup;

    //Add each button to toggle group
    rbq1.setToggleGroup(tg);
    rbq2.setToggleGroup(tg);

    //Handle action events for the radio buttons
    rbq1.setOnAction(new EventHandler<ActionEvent>() {
      public void handle(ActionEvent ae) {
        response.setText("Answer selected is q1")
      }
    });

    rbq2.setOnAction(new EventHandler<ActionEvent>() {
      public void handle(ActionEvent ae) {
        response.setText("Answer selected is q2")
      }
    });

     rbq1.fire();

     //Add label and buttons to the scene
     rootNode.getChildren().addAll(prompt, rbq1, rbq2, response);

     myStage.show();
  }

}
// this is not yet complete. I have created a couple of radio buttons here. The layout needs to be tweaked. 
