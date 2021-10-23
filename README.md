MapReduce Use Case – Titanic Data Analysis
DATASET DESCRIPTION
Column 1 : PassengerId

Column 2 : Survived  (survived=0 & died=1)

Column 3 : Pclass

Column 4 : Name

Column 5 : Sex

Column 6 : Age

Column 7 : SibSp

Column 8 : Parch

Column 9 : Ticket

Column 10 : Fare

Column 11 : Cabin

Column 12 : Embarked

*********Problem Statement 1:**********

In this problem statement, we will find the average age of males and females who died in the Titanic tragedy.


***********Problem Statement 2:*********
In this problem statement, we will find the number of people died or survived in each class with their genders and ages.


********For problem statement 1.*******

1. Open terminal

2. hadoop fs -mkdir /titanic

3. hadoop fs -put /home/mangal/Desktop/TitanicData.txt /titanic

4. Open bashrc file by gedit ~/.bashrc and type
	  ///// don't add this path if it is already exist
	export HADOOP_CLASSPATH=$JAVA_HOME/lib/tools.jar

5. Then source ~/.bashrc

6. cd Desktop

7. Now compile titanic1.java file suppose that file is on Desktop

	hadoop com.sun.tools.javac.Main titanic1.java

8. To combine all class files 
	
	jar cf wc.jar titanic1*.class

9. To execute
	
	hadoop jar wc.jar titanic1 /titanic/TitanicData.txt /average_age

10. hadoop fs -ls /			//// to check output folder is there or not

11. hadoop fs -cat /average_age/part-r-00000

************For problem statement 2****************

1. Open terminal

2. hadoop fs -mkdir /titanic

3. hadoop fs -put /home/mangal/Desktop/TitanicData.txt /titanic

4. Open bashrc file by gedit ~/.bashrc and type
	  ///// don't add this path if it is already exist
	export HADOOP_CLASSPATH=$JAVA_HOME/lib/tools.jar

5. Then source ~/.bashrc

6. cd Desktop

7. Now compile titanic2.java file suppose that file is on Desktop

	hadoop com.sun.tools.javac.Main titanic2.java

8. To combine all class files 
	
	jar cf wc.jar titanic2*.class

9. To execute
	
	hadoop jar wc.jar titanic2 /titanic/TitanicData.txt /female_died

10. hadoop fs -ls /			//// to check output folder is there or not

11. hadoop fs -cat /female_died/part-r-00000
