# InnoByte-Services
Internship
#Main Application Class

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.VBox;
import javafx.stage.Stage;

public class OnlineQuizApp extends Application {
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("Online Quiz Application");

        Button loginButton = new Button("Login");
        Button registerButton = new Button("Register");

        loginButton.setOnAction(e -> LoginUI.display());
        registerButton.setOnAction(e -> RegisterUI.display());

        VBox layout = new VBox(10);
        layout.getChildren().addAll(loginButton, registerButton);

        Scene scene = new Scene(layout, 400, 200);
        primaryStage.setScene(scene);
        primaryStage.show();
    }
}



#Database Configuration


import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class DatabaseConfig {
    private static final String URL = "jdbc:mysql://localhost:3306/quiz_app";
    private static final String USER = "root";
    private static final String PASSWORD = "password";

    public static Connection getConnection() throws SQLException {
        return DriverManager.getConnection(URL, USER, PASSWORD);
    }
}


