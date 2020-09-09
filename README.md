

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.geometry.Insets;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.layout.GridPane;
import javafx.stage.Stage;


public class lala extends Application
{
    
    private int count = 0;
    private Label myLabel = new Label("0");

    @Override
    public void start(Stage stage) throws Exception
    {
        
        Button myButton = new Button("Count");

        
        GridPane pane = new GridPane();
        pane.setPadding(new Insets(10, 10, 10, 10));
        pane.setMinSize(300, 300);
        pane.setVgap(10);
        pane.setHgap(10);

      
        myButton.setOnAction(this::buttonClick);

        
        pane.add(myLabel, 1, 0);
        pane.add(myButton, 0, 0);

       
        Scene scene = new Scene(pane, 300,100);
        stage.setTitle("JavaFX Example");
        stage.setScene(scene);

        
        stage.show();
    }

    /**
     * This will be executed when the button is clicked
     * It increments the count by 1
     */
    private void buttonClick(ActionEvent event)
    {
        
        count = count + 1;
        myLabel.setText(Integer.toString(count));
    }
}
