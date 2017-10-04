- Open XCode
- File -> New -> Project -> Cross-platform -> External Build System
- Enter Product Name
- Choose the directory where you want your XCode Project to be created
Adding Src file
- File -> Add Files to "[your product/project name]"
- Go to the NS-3 src code, and select the files/directories - usually src/ and scratch/ - to include into the XCode project

Before building, you need to configure your project. Use your terminal and CD to where the ns-3 directory is placed, then type :
./waf -d debug configure

Set up XCode to build your project
- In the XCode project settings -> tab "Info" -> External Build Tool Configuration -> Build Tool
-- Change it to : ./waf
- In Directory chose the directory where the ns-3 src code is placed
- After this step, you should be able to build your project successfully 

Now to the debugging part

- Product -> Scheme -> Edit Scheme -> Run -> Info :
-- Executable : Other ( then chose your simulation main program- from build/scratch/ usually - )
- In Arguments, you can specify the arguments to be passed to your main simulation program
- Then close and run

You can now use the C++ debugger integrated in XCode

If you have any questions, please do not hesitate
