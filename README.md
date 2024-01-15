<h1 align="center">qCompiler: Simplifying Code Compilation</h1>

<p align="center"><b>qCompiler</b> is a versatile Node.js library designed for building online or offline code compiler applications. It enables seamless compilation for various languages on the server, providing outputs swiftly and efficiently.</p>

# Why qCompiler?
**qCompiler** offers a user-friendly solution for developers who want to integrate code compilation into their applications without the hassle of configuring compilers on the server. Whether you are building an educational platform, have coding challenges, or need a reliable code compilation service, **qCompiler** streamlines the process.

# Key Features
- **Language Support:** As an evolving project, qCompiler currently supports essential languages, including C, C++, Java, and Python. As the library expands, additional languages will be incorporated.

Supported Languages 
===================
qCompiler is currently in the initial development stage. As the library grows, so does the list here.

| Language | Support |
|-----------|:---------:|
|C |&#x2714;|
|C++ | &#x2714; |
|Java | &#x2714; |
|Python | &#x2714; |

# Workflow

1. **Receive Code and Input Data:** Get the program and input data from the client as requested.
   
2. **Compile the Program:** Utilize the qCompiler module to compile the program.

3. **Retrieve Output and Errors:** Obtain the output and errors in JSON and string formats.

4. **Respond to the Client:** Send the output back to the client.

# Setting Up Compilers

Before utilizing **qCompiler**, ensure that the necessary compilers for the target programming languages are set up on the server. Here's a brief guide to assist you:

## Installation and Testing the Environment

To compile programs in any programming language, you must have the relevant compiler installed on the server. Follow these steps to set up the compiler environment:

### **Installing and Testing C/C++ on Windows:**
   Install GCC compiler, which can compile programs from the command line. After installation, set environment variables to access GCC command lines from any directory.

   - Download [MinGw](http://www.mingw.org/) and install on your server machine.

   - For a quick test, create a simple C/C++ file in any directory.

   - Open a command prompt in that directory and run:
       ```bash
         path/to/minGW/g++ filename.c -o output.exe
       ```

   - If this command runs smoothly and an `output.exe` file appears, your GCC compiler setup is good to go.

### **Installing and Testing Python on Windows:**
   Ensuring Python is correctly installed and configured on your Windows machine is a straightforward process. Follow these simple steps to set up Python for use with **qCompiler**:

   - Download from [official Python website](https://www.python.org/downloads/) and run the installer.
   
   - Add Python environment variable to PATH (optional).
   
   - Open a Command Prompt and run the following command:
      ```bash
        python --version
      ```
      You should see the installed Python version. This verifies that Python is successfully installed.
   
   - To ensure Python is working as expected, let's run a simple script:
   
   - Open a text editor and create a file named `test.py`. Add the following code to the file:
      ```python
        print("Hello, Python!")
      ```

   - Open a Command Prompt and run the following command:
      ```bash
        python test.py
      ```
      You should see the output "Hello, Python!".

### **Installing and Testing Java on Windows:**
Ensuring Java is correctly installed and configured on your Windows machine is a simple process. Follow these steps to set up Java for use with **qCompiler**:

- Download Java Development Kit (JDK) from [Oracle JDK Download page](https://www.oracle.com/java/technologies/javase-downloads.html) and install it.

- Set up the `JAVA_HOME` environment variable with variable Name: `JAVA_HOME` and variable Value: `Path to your JDK installation`.

- Add "Path" variable under "System Variables" `%JAVA_HOME%\bin`.

- To verify the Java installation, run the following commands:
     ```bash
     java -version
     javac -version
     ```
  You should see information about the installed Java version and the Java compiler.



# Documentation

## Installation

```bash
  npm i qcompiler
```

## Usage

### **C/C++**
```javascript
const { compile } = require('qcompiler');
const systemCongig = {
 OS: "windows",
 cmd: "g++"
}
const language = "CPP";

const data = await compile(code, language, input, systemConfig);

console.log(data)
//  data.status = true/false
//  data.output = Output value
//  data.error  = Error message (if status == false)
```

### **Java**
```javascript
const { compile } = require('qcompiler');
const systemCongig = {
 OS: "windows",
 cmdCompile: "javac",
 cmdExecute: "java"
}
const language = "JAVA";

const data = await compile(code, language, input, systemConfig);

console.log(data)
//  data.status = true/false
//  data.output = Output value
//  data.error  = Error message (if status == false)
```

### **Python**
```javascript
const { compile } = require('qcompiler');
const systemCongig = {
 OS: "windows",
 cmd: "python"
}
const language = "PYTHON";

const data = await compile(code, language, input, systemConfig);

console.log(data)
//  data.status = true/false
//  data.output = Output value
//  data.error  = Error message (if status == false)
```

### Language Parameter
To compile code in different languages a `language` parameter is required to pass. The value for this parameter for different language is as follows:
```javascript
// For C
const language = "C";

// For C++
const language = "CPP";

// For C
const language = "C";

// For Java
const language = "JAVA";

// For Python
const language = "PYTHON";
```

# **Note**

*For the most up-to-date information and usage guidelines, please take a look at the official documentation.*
*Explore the power of code compilation with qCompiler – the comprehensive solution for seamless integration and efficient processing.*

# License

All the contents in this repository are released under the <a href="https://github.com/masud70/qCompiler/License.md">MIT License</a>.