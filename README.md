# 389.-Usando-CSS-com-FXML
Adicionado caracteristicas a tela login
ARQUIVO FXML
_________________________________________
<?xml version="1.0" encoding="UTF-8"?>

<?import javafx.scene.layout.*?>
<?import javafx.scene.control.*?>

<GridPane xmlns:fx="http://javafx.com/fxml/1"
	fx:controller="fxml.LoginControlador"
	styleClass="login">
	<Label text="Seja Bem Vindo"
		styleClass="login-titulo"
		GridPane.columnIndex="0" GridPane.rowIndex="0"></Label>	
	<Label text="E-mail: "
		styleClass="login-form-label"
	    GridPane.columnIndex="0" GridPane.rowIndex="1"></Label>
	<TextField fx:id="campoEmail"
		GridPane.columnIndex="1" GridPane.rowIndex="1">
	</TextField>
	<Label text="Senha: "
		styleClass="login-form-label"
		GridPane.columnIndex="0" GridPane.rowIndex="2"></Label>
	<PasswordField fx:id="campoSenha"
		GridPane.columnIndex="1" GridPane.rowIndex="2">
	</PasswordField>
	<Button text = "Entrar"
		GridPane.columnIndex="0" GridPane.rowIndex="3"
		onAction="#entrar">
	</Button>
</GridPane>
________________________________________
APP
_______________________________________
public class AppFXML extends Application {
	
	@Override
	public void start(Stage primaryStage) throws Exception {
		String arquivoCSS = getClass().getResource("/fxml/Login.css").toExternalForm();
		URL arquivoFXML = getClass().getResource("/fxml/Login.fxml");
		GridPane raiz = FXMLLoader.load(arquivoFXML);
		
		Scene cena = new Scene(raiz, 350, 400);
		cena.getStylesheets().add(arquivoCSS);
		
		primaryStage.setResizable(false);
		primaryStage.setTitle("Tela de Loguin");
		primaryStage.setScene(cena);
		primaryStage.show();
	}
	public static void main(String [] args) {
		launch(args);
	}
  ![image](https://user-images.githubusercontent.com/95525963/153731988-8454f69b-f1af-4217-b6cb-e513a56e296e.png)
