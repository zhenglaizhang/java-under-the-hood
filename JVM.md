## Overview

* 'J' in JVM is misleading!
* 


## Class file structure

* Magic Number: 0xCAFEBABE (file cmd)
    
    > file World.class
    HelloWorld.class: compiled Java class data, version 52.0
    

## class file disassembler

    javac HelloWorld.java
    javap HelloWorld
    javap -c HelloWorld     # disassemble method 
    javap -v HelloWorld     # print stack size, locals and args


javac automatically add one no-arg default ctor.


## stack based virtual machine

* not the same as phyciscal machines which has registers
The action of the JVM interpreter can be simply thought of a switch inside a while loop - processing each opcode independently of the last using the stack positions to hold intermediate values.

ituation for real production-grade Java interpreters is a little more complexo

To achieve this, the operating system starts the virtual machine process and almost immediately, the first in a chain of class loaders is initialised. This initial loader is known as the Bootstrap classloader, and contains classes in the core Java runtime. In current versions these are loaded from rt.jar, although this is changing in Java 9