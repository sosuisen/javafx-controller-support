# JavaFX Controller Support

This VSCode extension provides support for FXML controllers in JavaFX projects.

- Detection and correction of `fx:id` errors.
- Displays diagnostics for invalid `fx:controller`.
- Offers a Code Lens option to add an `initialize` method if it is missing from the controller class.

# Features

## (1) Detection and Correction of fx:id Errors

Displays diagnostics when an `fx:id` in the FXML does not have a corresponding `@FXML` field in the controller class.

### 🛠️ Automatically Adds Necessary @FXML Fields

Adds the required `@FXML` fields for `fx:id` individually through Quick Fix.

<img src="images/no_field_hint.png" width="300">

### 🔍 Code Lens Option for Missing @FXML Fields

Provides a Code Lens option, "Add all missing @FXML fields," to automatically add all missing `@FXML` fields for `fx:id`.

<img src="images/no_field_lens.png" width="200">

### 📺 Diagnostics for Incorrect `@FXML` Fields

Displays diagnostics when an `@FXML` field specified in the controller class does not have a corresponding `fx:id` in the FXML.

<img src="images/no_fxid_hint.png" width="300">

## (2) Diagnostics for Invalid `fx:controller`

💡 `fx:controller` must be specified in the FXML file.

<img src="images/fxcontroller_01.png" width="400">

💡 Controller class not found.

<img src="images/fxcontroller_02.png" width="500">


## (3) Code Lens Option to Add initialize Method

Press "Add public void initialize() method" to add the `initialize` method.

<img src="images/initialize_lens.png" width="200">

Result:

<img src="images/initialize_result.png" width="500">


# Miscellaneous

## Limitations

This plugin does not support references to event handlers using `@FXML`, and there are no plans to support them.

Please reference the element using `fx:id` and set the event handler in the controller class.

<img src="images/setonaction.png" width="250">

## Requirements

- Java and FXML files must be located within the `src` directory. For example, place Java files in `src/main/java/com/example/FooController.java` and FXML files in `src/main/resources/com/example/foo.fxml`.
- `fx:controller` must be specified in the FXML file. `FXMLLoader.setController()` is not supported.
- This extension will not function correctly unless there is a class in the project that extends `javafx.application.Application`.

## Extension Settings

This extension does not contribute any settings.

## Issues

https://github.com/sosuisen/javafx-controller-support/issues

## Release Notes

### 1.2.0

- Builder Class Generator has been separated into the [JavaFX Builder Class Generator](https://marketplace.visualstudio.com/items?itemName=sosuisha.javafx-builder-class-generator) extension.

### 1.1.0

- Added Builder Class Generator.

### 1.0.0

- Initial release.
