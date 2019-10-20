**Current page is designed to allow users to quickly set up and start using OpenNARS system**

There are multiple ways to start OpenNARS: download executable ready-to-use .jar binary or compile from source

## I. Executable version
Java 8 is the minimum requirement for the purpose of running OpenNARS, Java 8 or later versions can be downloaded from [here](https://www.java.com/en/)

For executable version, simply download .zip file from [here](https://www.opennars.org) to an accessible location on your machine, then extract the file, navigate to OpenNARS/bin and run **opennars-lab-3.x.y-SNAPSHOT.jar**

## II. Source-code version

**To be able to compile and run from source code the following is required:**
<br/><br/>
**1.** Java jdk 1.8 or higher
<br/><br/>
**2.** git  
<br/>
**3.** Maven can be obtained from https://maven.apache.org/download.cgi
<br/><br/>
**4.** Java, git and Maven must be written to environment variables such that they are accessible from terminal
<br/><br/>
**Note:** In order to use OpenNARS launcher, OpenNARS needs to be installed in three stages: 
<br/>
**a.** **Terminal version** of OpenNARS where Narsese statements can be entered from the terminal only
<br/>
**b.** **OpenNARS GUI** where Narsese statements are entered within GUI, and derivations, output and other useful info can also be seen
<br/>
**c.** **OpenNARS Lab** - test cases that demonstrate NARS functionality and abilities
<br/>

### Instruction to compile and run OpenNARS from source code using Maven

**1.** Create a directory and navigate to it, let call this directory a _root_
<br/><br/>
**2.** Clone git repository by issuing command git clone https://github.com/opennars/opennars.git
<br/><br/>
**3.** For Windows users only, **skip this step if using Unix or MAC**. In order for maven to find valid JDK _**JAVA_HOME**_ variable must point to the correct location, just set it to your directory of JDK.<br/> Example: **set JAVA_HOME="C:\Progra~1\Java\jdk1.8.0_121"**
<br/><br/>
**4.** Navigate to _opennars_ directory where _pom.xml_ can be found and type _**mvn install**_, the building process will start. **Note:** It should take about 5-7 minutes to complete since it will be running some tests. It is possible to skip tests by issuing command: _**mvn install -DskipTests=True**_
<br/><br/>
**5.** Stage 1 is done! To run OpenNARS from terminal just navigate to _opennars/target/_ directory and issue command _**java -jar opennars-3.0.0-SNAPSHOT.jar**_ It should start, register with the shell and you should be able to enter Narsese statements to communicate with the system.
<br/><br/>
**6.** To set up OpenNARS with gui, navigate to _root_ directory
<br/><br/>
**7.** Clone OpenNars-GUI by issuing command _**git clone https://github.com/opennars/opennars-GUI.git**_
<br/><br/>
**8.** Once completed navigate to opennars-GUI directory and issue command _**mvn install**_, building process will start, it should take few minutes to complete, again tests can be skipped
<br/><br/>
**9.** Step 2 is done! To run OpenNARS with GUI support just navigate to _opennars-GUI/target/_ directory and issue command _**java -jar opennars-3.0.0-SNAPSHOT.jar**_ 
<br/><br/>
**11.** To set up OpenNARS with launcher and test examples, navigate to _root_ directory
<br/><br/>
**12.** Clone OpenNars-LAB by issuing command _**git clone https://github.com/opennars/opennars-LAB.git**_
<br/><br/>
**13.** Once completed navigate to opennars-LAB directory and issue command  _**mvn install**_, building process will start, it should take few minutes to complete.
<br/><br/>
**14.** Step 3 is done! To run OpenNARS Launcher just navigate to _opennars-LAB/target/_ directory and issue command _**java -jar opennars-3.0.0-SNAPSHOT.jar**_ 
<br/><br/>
_Once all the steps are completed root directory should contain three folders:_
<br/>
opennars
<br/>
opennars-GUI
<br/>
opennars-LAB
<br/><br/>

## III. Launcher

### Welcome frame
Once the jar file is running, you will be greeted by the OpenNARS launcher. This lists a variety of applications that allow for interaction with a NARS agent. In addition, the launcher provides links to the wiki, website, and communication channels.<br/><br/> 
![image](https://user-images.githubusercontent.com/24262360/52943113-63620a00-333a-11e9-9adb-fbc175f8ed34.png)
<br/>For now, the most important of these is the ‘Main GUI’ option.

### OpenNARS GUI
Clicking the Main GUI button will open an instance of the OpenNARS GUI which offers many capabilities. The main one is providing a means to enter Narsese sentences into the system, so that they can be parsed and added to the memory of the agent, as well as be processed in real time. In addition, the GUI provides the immediate responses of the system, as well as shows the current activities in it.<br/><br/>
![image](https://user-images.githubusercontent.com/24262360/52943282-ceabdc00-333a-11e9-8f9a-e4c6835ce953.png)

### Control Panel
The left-hand side contains the control elements for the system. The four fields (volume, pause, threads, and decision threshold) represent configuration parameters that influence the workings of the inference engine, and the frequency of output seen by the user.

The play button allows the user to pause, and restart the system. When paused, the system will not perform inference cycles, and the output of the system will stop. The button next to this allows a user to ‘step through’ a single inference cycle.

### Output Panel
The largest of the three panels is the output area for the system. This is the area where the current workings of the system will be displayed. These will show up as Narsese statements that represent user inputs and derived tasks.

### Input Panel
The pane below this is the input field for the GUI. Here a user can input lines of Narsese statements to be provided to the system. To test this out, try inputting the following simple sentences:<br/>
<Sam --> Man>.<br/>
<Man --> Animal>.<br/>
<Sam --> Animal>?<br/>
The input field can accommodate multiple lines of input text. Once any text is entered into the field, an input button will appear. After selecting this, the system will attempt to parse the text, and if properly formatted Narsese is found, the sentence will be entered into the actual NARS agents memory. You can also use "Ctrl-Enter" to enter the text.

Once the text is inputted (try the above statements out!) you should see the output panel echo back the statements. Once the ‘play’ button is hit, the system will start performing inference cycles. The derived statements that result from this will appear in the output panel.