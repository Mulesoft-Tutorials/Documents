
# Exception Handling

When an event is being processed through Mule flow that throws an error

- Normal flow execution stops
- The event is passed to the first processor in an error handler

![](https://github.com/Mulesoft-Tutorials/Documents/blob/master/images/Errors-1.PNG)


## Default Error Handler

If there is no error handler defined, then Mule default error handler is used

- handles all messaging error thrown in Mule application
- stops execution and logs information about the error
- cannot be configured

When an error in thrown, error object is created ( error.description and error.type)

## Creating Error Handler

Error handler can be added to
- An application
- Flow
- Event processors

Error handler can have one or more error handler scopes like

  - On Error Continue
  - On Error Propogate
