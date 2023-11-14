# Class Loaders in Java
## 1. Introduction to Class Loaders
- Java classes aren’t loaded into memory all at once, but rather when they’re required by an application. This is where class loaders come into the picture. They’re responsible for loading classes into memory.

## 2. Types of Built-in Class Loaders
how we can load different classes using various class loaders:
```
public void printClassLoaders() throws ClassNotFoundException {

    System.out.println("Classloader of this class:"
        + PrintClassLoader.class.getClassLoader());

    System.out.println("Classloader of DriverManager:"
        + DriverManager.class.getClassLoader());

    System.out.println("Classloader of ArrayList:"
        + ArrayList.class.getClassLoader());
}
```
output:
```
Classloader of this class:jdk.internal.loader.ClassLoaders$AppClassLoader@73d16e93
Classloader of DriverManager:jdk.internal.loader.ClassLoaders$PlatformClassLoader@1fb700ee
Classloader of ArrayList:null
```
There are three different class loaders here: 
1. application, 
2. extension,
3. bootstrap (displayed as null).

The application class loader loads the class where the example method is contained. An application or system class loader loads our own files in the classpath.

Next, the extension class loader loads the DriverManager class. Extension class loaders load classes that are an extension of the standard core Java classes.

Finally, the bootstrap class loader loads the ArrayList class. A bootstrap or primordial class loader is the parent of all the others.

However, we can see that for the ArrayList, it displays null in the output. This is because the bootstrap class loader is written in native code, not Java, so it doesn’t show up as a Java class. As a result, the behavior of the bootstrap class loader will differ across JVMs.

### 2.1. Bootstrap Class Loader
Java classes are loaded by an instance of java.lang.ClassLoader. However, class loaders are classes themselves. So the question is, who loads the java.lang.ClassLoader itself?

This is where the bootstrap or primordial class loader comes into play.

It’s mainly responsible for loading JDK internal classes, typically rt.jar and other core libraries located in the $JAVA_HOME/jre/lib directory. Additionally, the Bootstrap class loader serves as the parent of all the other ClassLoader instances.

This bootstrap class loader is part of the core JVM and is written in native code, as pointed out in the above example. Different platforms might have different implementations of this particular class loader.

### 2.2. Extension Class Loader
The extension class loader is a child of the bootstrap class loader, and takes care of loading the extensions of the standard core Java classes so that they’re available to all applications running on the platform.

The extension class loader loads from the JDK extensions directory, usually the $JAVA_HOME/lib/ext directory, or any other directory mentioned in the java.ext.dirs system property.



### 2.3. System Class Loader
The system or application class loader, on the other hand, takes care of loading all the application level classes into the JVM. It loads files found in the classpath environment variable, -classpath, or -cp command line option. It’s also a child of the extensions class loader.

## 3. How Do Class Loaders Work?
Class loaders are part of the Java Runtime Environment. When the JVM requests a class, the class loader tries to locate the class and load the class definition into the runtime using the fully qualified class name.

The java.lang.ClassLoader.loadClass() method is responsible for loading the class definition into runtime. It tries to load the class based on a fully qualified name.

If the class isn’t already loaded, it delegates the request to the parent class loader. This process happens recursively.

Eventually, if the parent class loader doesn’t find the class, then the child class will call the java.net.URLClassLoader.findClass() method to look for classes in the file system itself. 

If the last child class loader isn’t able to load the class either, it throws java.lang.NoClassDefFoundError or java.lang.ClassNotFoundException.
Let’s look at an example of the output when ClassNotFoundException is thrown:
```
java.lang.ClassNotFoundException: com.baeldung.classloader.SampleClassLoader    
    at java.net.URLClassLoader.findClass(URLClassLoader.java:381)    
    at java.lang.ClassLoader.loadClass(ClassLoader.java:424)    
    at java.lang.ClassLoader.loadClass(ClassLoader.java:357)    
    at java.lang.Class.forName0(Native Method)    
    at java.lang.Class.forName(Class.java:348)

```
If we go through the sequence of events right from calling java.lang.Class.forName(), we can see that it first tries to load the class through the parent class loader, and then java.net.URLClassLoader.findClass() to look for the class itself.

When it still doesn’t find the class, it throws a ClassNotFoundException.

Now let’s examine three important features of class loaders.
### 3.1. Delegation Model
Class loaders follow the delegation model, where on request to find a class or resource, a ClassLoader instance will delegate the search of the class or resource to the parent class loader.

Let’s say we have a request to load an application class into the JVM. The system class loader first delegates the loading of that class to its parent extension class loader, which in turn delegates it to the bootstrap class loader.

Only if the bootstrap and then the extension class loader are unsuccessful in loading the class, the system class loader tries to load the class itself.
### 3.2. Unique Classes
As a consequence of the delegation model, it’s easy to ensure unique classes, as we always try to delegate upwards.


freestar
If the parent class loader isn’t able to find the class, only then will the current instance attempt to do so itself.
### 3.3. Visibility
In addition, children class loaders are visible to classes loaded by their parent class loaders.

For instance, classes loaded by the system class loader have visibility into classes loaded by the extension and bootstrap class loaders, but not vice-versa.

To illustrate this, if Class A is loaded by the application class loader, and class B is loaded by the extensions class loader, then both A and B classes are visible as far as other classes loaded by the application class loader are concerned.

Class B, however, is the only class visible to other classes loaded by the extension class loader.


## 4. Custom ClassLoader
The built-in class loader is sufficient for most cases where the files are already in the file system.

However, in scenarios where we need to load classes out of the local hard drive or a network, we may need to make use of custom class loaders.

In this section, we’ll cover some other use cases for custom class loaders and demonstrate how to create one.


### 4.1. Custom Class Loaders Use-Cases
Custom class loaders are helpful for more than just loading the class during runtime. A few use cases might include:

1. Helping to modify the existing bytecode, e.g. weaving agents
2. Creating classes dynamically suited to the user’s needs, e.g. in JDBC, switching between different driver implementations is done through dynamic class loading.
3. Implementing a class versioning mechanism while loading different bytecodes for classes with the same names and packages. This can be done either through a URL class loader (load jars via URLs) or custom class loaders.
Below are more concrete examples where custom class loaders might come in handy.

Browsers, for instance, use a custom class loader to load executable content from a website. A browser can load applets from different web pages using separate class loaders. The applet viewer, which is used to run applets, contains a ClassLoader that accesses a website on a remote server instead of looking in the local file system.

It then loads the raw bytecode files via HTTP, and turns them into classes inside the JVM. Even if these applets have the same name, they’re considered different components if loaded by different class loaders.

Now that we understand why custom class loaders are relevant, let’s implement a subclass of ClassLoader to extend and summarise the functionality of how the JVM loads classes.
### 4.2. Creating Our Custom Class Loader

## 5. Understanding java.lang.ClassLoader

### 5.1. The loadClass() Method

### 5.2. The defineClass() Method


### 5.3. The findClass() Method


### 5.4. The getParent() Method


### 5.5. The getResource() Method


## 6. Context Classloaders

## 7. Conclusion

