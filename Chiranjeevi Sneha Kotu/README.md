# MapReduce Solution - Sneha
Our dataset is subset of data on migraine treatments collected by Tammy Kostecki-Dillon. 
In our project we try to find out about the age groups of people of both genders who suffer from migrane and the symptoms and medication they use.
## How to download and use the code
In order to see the code the following steps need to be followed

### Prerequisites
The prerequisite is to have a VMWare running in laptop. In orderto run the solution first install a VMWare with Python running in it.

Link to download VMWare
```
Download and install from https://my.vmware.com/web/vmware/free#desktop_end_user_computing/vmware_player/6_0
or
Download and install VirtualBox from https://www.virtualbox.org/wiki/Downloads
Create the Virtual Machine:
```

###Installion of VMWare
Download the VMWare from above link and then install by these steps
Create a new Virtual machine:
Create a new virtual machine by pressing the ‘New’ button:
Choose a name, use ‘Type’: ‘Linux’:
Press Next
Select memory size for the VM. (2048 MB)
Press Next
Select ‘Use an existing virtual hard drive file’’, click the button to browse to the directory you unzipped the provided VM image and press ‘Create’.
Select the machine and click ‘Play virtual machine’
Start the VM!

### How to run the solution
After installing VMWare put the mapper,reducer and .csv dataset into a folder and follow the commands given below inorder to put these files into HDFS and run the solution to get the output
```
In code, to see local mapper.py & reducer.py, type:
$ ls
$ ls ../data
$ cd ../data
```
Put a copy of KosteckiDillon.csv into HDFS myinput directory.

```
$ hadoop fs -ls
$ hadoop fs -put KosteckiDillon.csv
$ hadoop fs -ls
$ hadoop fs -tail KosteckiDillon.csv
$ hadoop fs -mv KosteckiDillon.csv newname.txt
$ hadoop fs -rm newname.txt
$ hadoop fs -mkdir myinput
$ hadoop fs -put KosteckiDillon.csv myinput
```
Verify myinput/KosteckiDillon.csv is in HDFS.
 
```
$ hadoop fs -ls myinput 
```

Run MR 

```
hs s_mapper.py s_reducer.py myinput joboutput
```

Review the output in HDFS
```
$ hadoop fs -ls
$ hadoop fs -ls joboutput
```
To get results out of hadoop, use get:

``` 
$ hadoop fs -get joboutput/part-00000 results.txt
```

Check for a local copy with ls:
```
$ ls 
s_mapper.py s_reducer.py results.txt
```





