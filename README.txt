FIRST:
NOTE: Eclipse LUNA Standard with Java EE was used
NOTE: Install Apache Maven (https://maven.apache.org/download.cgi)

Import the extended version of pitest as a maven project into Eclipse.

Right click the pom.xml file in the "pitest" folder and  "Run as Maven Build.."

Enter into Goal field: "clean install -DskipTests"

To specify which active mutators we are going to be use:
*Must be pasted below plugin into the project pom.xml of the project which is going to be mutated*

<build>
  <plugins>
	<plugin>
	<groupId>org.pitest</groupId>
	<artifactId>pitest-maven</artifactId>
	<version>1.2.4</version>
	<configuration>
		<mutators>
			<mutator>Absolute Mutator</mutator>
			<mutator>Arithmentic and Bitwise Replacement 1</mutator>
			<mutator>Arithmentic and Bitwise Replacement 2</mutator>
			<mutator>Arithmentic and Bitwise Replacement 3</mutator>
			<mutator>Arithmentic and Bitwise Replacement 4</mutator>					    		
			<mutator>AOD_Mutator2</mutator>
			<mutator>AOD_Mutator1</mutator>
			<mutator>RelationalReplacement1</mutator>
			<mutator>RelationalReplacement2</mutator>
			<mutator>RelationalReplacement3</mutator>
			<mutator>UOI_Mutator1</mutator>
			<mutator>UOI_Mutator1</mutator>
			<mutator>UOI_Mutator1</mutator>
			<mutator>CRCR1</mutator>
			<mutator>CRCR2</mutator>
			<mutator>CRCR3</mutator>
			<mutator>CRCR4</mutator>
			<mutator>CRCR5</mutator>
		</mutators>	
    	</configuration>
	</plugin>
  </plugins>
</build>

To Run the mutation tests:
Open Command Prompt
Relocate to the project directory where the pom.xml of the porject(on which we are going to run augmented PIT Tool)(cd /*test_project*)
Run command (mvn org.pitest:pitest-maven:mutationCoverage)

Mutation Reports will be located in target folder under pit-reports
