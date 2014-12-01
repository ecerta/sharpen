Building JAR on Local from code located on GitHub:-
1. Install Java 7 & maven
2. Pull the code following URL Or download zip and after that unzip it.  
  https://github.com/avasp/sharpen/tree/SelfContainedJarFile-30SEP14
3. Go to parent directory where pom.xml is present through command prompt.
4. Now run following command in command prompt:
>mvn clean install
5. On successful buld, sharpencore-0.0.1-SNAPSHOT-jar-with-dependencies.jar will be created in folder 
../sharpen.core/target 
6. sharpencore-0.0.1-SNAPSHOT-jar-with-dependencies.jar can be used to convert java source files to c#.

Uses of JAR(sharpencore-0.0.1-SNAPSHOT-jar-with-dependencies.jar) for conversion:
    
Minimum command to for conversion 

>java -jar sharpencore-0.0.1-SNAPSHOT-jar-with-dependencies.jar  sourcepath -cp dependent_jar 

Above
sourcepath: Absolute path for java source. For example: D:\JavaProject\src
dependent_jar: name of dependent jar with complete path. For example:D:\javalib\log4j.jar 
all dependent jar should be provided through -cp options. 

All valid command line can be input through a file. For example all command is in file "sharpen-all-options":
>java -jar sharpencore-0.0.1-SNAPSHOT-jar-with-dependecies.jar D:\JavaProject\src  @D:\ProjectConfig\sharpen-all-options 

Help can be displayed with following command: 
>java -jar sharpencore-0.0.1-SNAPSHOT-jar-with-dependecies.jar -help

Following are valid command lines:-
 
-pascalCase: Convert Java identifiers to Pascal case. For example:-pascalCase

-pascalCase+: Convert Java indentifiers and package names (namespaces) to Pascal case. For example: -pascalCase+

-cp: Set absolute path for dependent jar or adds a new entry to classpath. For example: -cp D:\javalib\log4j.jar 

-srcFolder: Adds a new source folder for sharpening. For Example: -srcFolder D:\javaprj\src 		 

-paramCountFileNames: Append Generic parameter count to file names. For example: -paramCountFileNames

-nativeTypeSystem: Map java classes to .NET classes with a similar functionality. For example: java.lang.Class - System.Type

-indentWithSpaces: Use spaces for indentation. For example: -indentWithSpaces

-indentSize: Set indent size. For example: -indentSize 5

-maxColumns: Set Max columns size. For example: -maxColumns 280 

-nativeInterfaces: Adds an "I" in front of the interface name. For example: -nativeInterfaces

-separateInterfaceConstants: Separates interface constants to their own classes. For example: -separateInterfaceConstants

-organizeUsings: Adds "using" for the types used. For example:-organizeUsings

-fullyQualify: Converts to a fully-qualified name. For example: -fullyQualify File

-namespaceMapping: Maps a java package name to a .NET namespace. For example: -namespaceMapping java.security Sharpen

-methodMapping: Maps a java method name to a .NET method (can be method in another class). 
For example: -methodMapping java.math.BigInteger.toByteArray GetBytes

-typeMapping: Maps a java class to .NET type. 
For Example:-typeMapping java.util.Enumeration System.Collections.Generic.IEnumeration

-propertyMapping: Maps a java method to .NET property. 
For Example: -propertyMapping java.net.Socket.isConnected Connected

-runtimeTypeName: Name of the runtime class. The runtime class provides implementation for methods that don't have a direct mapping or 
that are simpler to map at the language level than at the sharpen level. For instance: String.substring, String.valueOf, Exception.printStackTrace,
etc.

-header: Header comment to be added to all converted files. 
For example:-header D:\config\copyright_comment.txt

-xmldoc: Specifies an xml- overlay file, which overrides javadoc documentation for specific classes. 
For example: -xmldoc D:\Config\ApiOverlay.xml

-eventMapping: Converts the methods to an event.

-eventAddMapping: Marks the method as an event subscription method. Invocations to the method in the form <target>.method(<argument>) will be replaced by the c# event subscription idiom: <target> += <argument>

-conditionalCompilation: Conditional compilation based on package name/source top (packages) are applied to the full compilation unit (everything will be enclosed by the conditional compilation).
For example: -conditionalCompilation com.avasp.disply NOTUSEDCODE 

-configurationClass: Overwrites default configuration Class with input class name. The default is 'sharpen.core.DefaultConfiguration'.
For example: -configurationClass sharpen.core.MyConfiguration

-junitConversion: JUnit conversion  mode on

-sharpenNamespace: Maps a java package name to a .NET namespace.
For example:-namespaceMapping java.util.concurrent.locks Sharpen

-help: Display Help    
