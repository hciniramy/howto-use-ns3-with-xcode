This is a small guide on how to integrate your NS-3 projects with XCode and make it **build**, **run** and **_debug_** them. 
The main purpose of this is to be able to use the debugging features of XCode with your NS-3 project. 
Because we all know that debugging is a pain in the a** ! Especially with the non-helping error messages of NS-3 ./waf build tool.

---

#### Create an XCode Project
- Open XCode
- File -> New -> Project -> Cross-platform -> External Build System
- Enter Product Name
- Choose the directory where you want your XCode Project to be created

#### Add the/your source files
- File -> Add Files to "[your product/project name]"
- Go to the NS-3 src code and select the files/directories _- usually src/ and scratch/ -_ to include in the XCode project

---

Now, before building, you need to configure your ns-3 project ( this can be done once ).
Use your terminal and **CD** to where the ns-3 directory is placed, then type :

*$ ./waf -d debug configure*

---

#### Set up XCode to build your project
- In the XCode project settings view -> tab **"Info"** -> External Build Tool Configuration :
  - In  **Build Tool** write : ./waf
  - In **Directory** : chose the directory where the ns-3 src code is placed

_After these steps, you should be able to build your project successfully_

---

#### Set up XCode to run and debug your project
- Product -> Scheme -> Edit Scheme -> Run  :
  - In **Info**-Tab -> Executable : Other ( then chose your simulation main program _- usually from build/scratch/ usually -_ )
  - In **Arguments**-Tab : you can specify the arguments to be passed to your main simulation program (e.g : when you run your simulation using waf : ./waf --run="mysimulation **-arg1=val1 -arg2=val2**")
  - Now close and run

You should be able now to use the C++ debugger integrated in XCode

If you have any questions or problems, please do not hesitate to open issues for them
