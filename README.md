# calilangmuletest

As the name suggests, this Mule app is a simple demonstration of the [mule cali-lang connector](https://github.com/rsv-code/cali-lang-mule-connector).

## Getting Started

1. First clone this repo.
2. In Anypoint Studio import the cloned project.
3. In Postman you can import the postman collection found in src/test/resources.
4. Launch the application.
5. Test the invoke request from Postman.

## What's going on in the Application

This is a really simple app. In the calilangmuletestFlow flow in the calilangmuletest.xml file there's a single Cali lang transform connector. Have a look at the properties and you'll see the 'Script file name' is set to ca/main.ca. Go ahead and open that file and you'll find all the cali-lang code which is being executed in the transform.

Also note that I've set the log glass to 'io.github.rsv-code.calilangtest'. You can find the definition of this in src/main/resources/log4j2.xml. This 'Log class' field is optional but it allows you to specify a log class to use.

The other two properties in the Cali lang transform are 'Message obj' and 'Vars obj'. These are set by default and there's nothing to modify here. They need to be present because this is how these Mule items are passed into the cali-lang interpreter for use in the script.

## src/main/resources/ca/main.ca

This is where the meat and potatos are. Cali-Lang files are required to end with a .ca extension. In this example a class of 'test' is implemented and it has a magic function called 'main' which takes no arguments. The main function is special and it tells the cali-lang interpreter where to begin execution.

For details about the options available with the cali-lang mule connector check out the docs in [cali-lang-mule-connector](https://github.com/rsv-code/cali-lang-mule-connector). For more information about cali-lang in general see the wiki docs in [cali.lang.base](https://github.com/cali-lang/cali.lang.base).

## License

This demo application is available under the terms of the GNU GPL v3. Please see the acompanying LICENSE file for details.
