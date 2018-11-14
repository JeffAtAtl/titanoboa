
## Synopsis
Titanoboa is fully distributed, highly scalable and fault tolerant workflow orchestration platform.
It employs hybrid iPaaS concepts and runs on the JVM.
You can run it on-premises or in a cloud.

![alt Logo](https://s3.eu-central-1.amazonaws.com/www.titanoboa.io/tb-logo-dark-nosubtitle.svg)

See also [titanoboa.io](https://titanoboa.io) and our [wiki](https://github.com/mikub/titanoboa/wiki) 

<img src="http://www.titanoboa.io/sample-graph.gif" width="500"/>

## Installation 
Download the latest release from https://www.titanoboa.io/titanoboa.jar. It is a single jar file.

    curl --remote-name https://www.titanoboa.io/titanoboa.jar

__Note__: _If you are intending on running titanoboa server on java JDK instead of JRE, download a distribution for JDK instead:_

    curl --remote-name https://www.titanoboa.io/titanoboa4jdk.jar

then execute the jar:
    
     java -jar titanoboa.jar

In your console you should see bunch of log messages and ultimately you will see
     
     INFO [main] - Started @3238ms

which means the server started successfully. By default the server and will start on port 3000.

Congratulations! You have just started your titanoboa server!

### Running server with GUI

Titanoboa GUI is great place for developing and designing new workflows as well as for managing their execution and monitoring the status of your server(s).
It is also a great starting point for evaluating and exploring the titanoboa platform.

__The GUI is free for non-commercial use only__, so if you just want to explore titanoboa it is the best place to start:

Download the latest release from https://www.titanoboa.io/distributions/gui-non-commercial-use-only/titanoboa.jar. It is a single jar file, the GUI is already in it.

    curl --remote-name https://www.titanoboa.io/distributions/gui-non-commercial-use-only/titanoboa.jar

__Note__: _If you are intending on running titanoboa server on java JDK instead of JRE, download a distribution for JDK instead:_

    curl --remote-name https://www.titanoboa.io/distributions/gui-non-commercial-use-only/titanoboa4jdk.jar

then execute the jar:
    
     java -jar titanoboa.jar

In your console you should see bunch of log messages and ultimately you will see
     
     INFO [main] - Started @3478ms

which means the server started successfully. By default the server and the GUI will start on port 3000 so you can open http://localhost:3000 in your browser to access it.

Now you can go ahead and try to create a [sample workflow](https://github.com/mikub/titanoboa/wiki/Getting-Started-with-GUI).

### Prerequisites
Java 8 JRE or JDK and higher. Almost all of the functionality works on Java 7 and higher, however Java Lambda support has been tested only on Java 8.

### Building from the repository
In case you don't want to download distributed release from our web page but to build it from the repository:
Titanoboa uses leiningen for dependency management, so if you don't have it download it from https://leiningen.org/ and follow its installation instructions.

Clone this repository

    git clone https://github.com/mikub/titanoboa
    
generate uberjar:

    lein uberjar
    
this will generate a big jar file (aka uberjar) in the _target_ directory.

If you want to use GUI you can clone the titanoboa-gui repository as well:

    git clone https://github.com/mikub/titanoboa-gui

then merge GUI's _public_ folder into the uberjar:

    zip -r -g titanoboa.jar public

then execute the jar:
    
     java -jar titanoboa.jar

### Server Configuration
Server configuration and external dependencies file can be specified by system properties `boa.server.config.path` and `boa.server.dependencies.path`:

     java -Dboa.server.config.path=boa_server_config_local.clj -Dboa.server.dependencies.path=ext-dependencies.clj -jar titanoboa.jar
     
See [Server configuration wiki](https://github.com/mikub/titanoboa/wiki/Server-Configuration) for more details.

## License
Copyright © Miro Kubicek

Titanoboa is dual-licensed under either AGPL license or a Commercial license.
