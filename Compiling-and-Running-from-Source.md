To be able to compile and run OpenNARS the following is required:
<br/><br/>
**1.** Java jdk 1.8 or higher
<br/><br/>
**2.** git  
<br/>
**3.** Maven can be obtained from https://maven.apache.org/download.cgi
<br/><br/>
**4.** Java git and Maven must be written to environment variables such that they are accessible from terminal
<br/><br/>
**Note:** In order to use OpenNARS launcher, OpenNARS needs to be installed in three stages: 
<br/><br/>
**a.** terminal version of OpenNARS where Narsese statements can be entered from the terminal only
<br/><br/>
**b.** OpenNARS GUI where Narsese statements can be entered in a special pane of a GUI where derivations, output and other useful info can be seen
<br/><br/>
**c.** OpenNARS Lab - test cases demonstrate NARS functionality and abilities
<br/><br/>
**## Instruction to compile and run OpenNARS from source code using Maven**
<br/><br/>
**1.** Create a directory and navigate to it
<br/><br/>
**2.** Clone git repository by typing git clone https://github.com/opennars/opennars.git
<br/><br/>
**3.** If using Windows only, Skip if using Unix or MMAC. In order for maven to find valid JDK JAVA_HOME variable must point to the correct location just set it to your directory of JDK. Ecample: set JAVA_HOME="C:\Progra~1\Java\jdk1.8.0_121"