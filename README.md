Simple demo [Spwing](https://github.com/bobhablutzel/spwing) application that 
demonstrates the use of the bidirectional binding, controller constructor parameters,
and multiple button handler methods.

This demonstration builds on the [SpwingLabelButtonDemo](https://github.com/bobhablutzel/SpwingLabelButtonDemo)
demonstration program, which introduces the concept of Spwing models, controllers, views and the 
SVWF view description language.

This application add bidirectional model <-> view binding. In this example,
the model field ```textField``` is bound to the view JTextField element ```textField```.
The binding occurs in this SVWF statement:

```
bind {
    textField.text => "textField" ["evtTextFieldChanged"];
}
```

By adding this binding, the contexts of the JTextField are initially set to the 
value from the model, and the model value is modified as the user types in the JTextField.
Two buttons are given in the demonstration; one will post a dialog with the current
value from the model, and the other will change the model value programmatically (which
will be reflected in the view).

This demonstration uses a different mechanism for communicating the model to the controller.
Since multiple controller methods need access to the model, it is added as a field of the 
controller. The [Lombok](https://projectlombok.org/) ```RequiredArgsConstructor``` constructor is used to add a constructor
that takes the model instance, which will automatically be provided by the Spwing framework
when the controller is created.

The demonstration also shows multiple button click handlers in the controller, which are linked
to the appropriate buttons via naming convention.

