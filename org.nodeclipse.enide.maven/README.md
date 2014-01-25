

# Enide Maven

This is alternative and completion to m2e (Maven Eclipse Integration).

Launch build or execute Java class.
Project does not need to be Maven project. Just `pom.xml` would be enough.
(The project may be General, old classic Java, broken Maven or Gradle project.)

No miracles, this plugins just launches `mvn` with options, as you can do from command line.
Full path to maven `mvn.bat` or `mvn` is used, so you can try different versions.
Specify options to `mvn` that will be Workspace-wide.
Executed string is shown is Console, so you can check and learn. 

## org.nodeclipse.enide.maven

pom.xml Run As `mvn package` Maven build
*.java Run As `mvn compile exec:java -Dexec.mainClass=package.Class`

Minisite <http://www.nodeclipse.org/enide/maven/>
GitHub <https://github.com/Nodeclipse/nodeclipse-1/tree/master/org.nodeclipse.enide.maven>

### Developing 

`git clone`, import this project and `org.nodeclipse.coomon` (2) in Eclipse with PDE (e.g. Eclipse SDK/Classic)
 as "Existing Projects into Workspace".

maven build is optional for full build with other plugins.

### TODO

1)

What is gradle analog for maven compile and run
`mvn compile exec:java -Dexec.mainClass=example.Example`

2)

`-Dexec.mainClass=maven.MainClass` becomes `maven.MainClass`

	package maven;
	
	public class MainClass {
		public static void main(String[] args) {
			System.out.println("app is running!");
		}
	}

from Eclipse using 

		Process p = DebugPlugin.exec(cmds, workingPath, envp);
		RuntimeProcess process = (RuntimeProcess)DebugPlugin.newProcess(launch, p, MavenConstants.PROCESS_MESSAGE);

for process

D:\Code\springsource\3.0\apache-maven-3.0.3\bin\mvn.bat compile exec:java -Dexec.mainClass=maven.MainClass 

[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building org.example.maven 0.0.1-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 0.672s
[INFO] Finished at: Fri Jan 24 23:59:50 CST 2014
[INFO] Final Memory: 4M/15M
[INFO] ------------------------------------------------------------------------
[ERROR] Unknown lifecycle phase "maven.MainClass". You must specify a valid lifecycle phase or a goal in the format <plugin-prefix>:<goal> or <plugin-group-id>:<plugin-artifact-id>[:<plugin-version>]:<goal>. Available lifecycle phases are: validate, initialize, generate-sources, process-sources, generate-resources, process-resources, compile, process-classes, generate-test-sources, process-test-sources, generate-test-resources, process-test-resources, test-compile, process-test-classes, test, prepare-package, package, pre-integration-test, integration-test, post-integration-test, verify, install, deploy, pre-site, site, post-site, site-deploy, pre-clean, clean, post-clean. -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/LifecyclePhaseNotFoundException

but from cmd shell using `mvn` or full filename is OK

D:\Progs\Enide-Monster-08-kepler-win32\runtime-EclipseApplication\org.example.maven>mvn compile exec:java -Dexec.mainClass=maven.MainClass
[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Building org.example.maven 0.0.1-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO]
[INFO] --- maven-resources-plugin:2.4.3:resources (default-resources) @ org.example.maven ---
[WARNING] Using platform encoding (Cp1251 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 0 resource
[INFO]
[INFO] --- maven-compiler-plugin:2.3.2:compile (default-compile) @ org.example.maven ---
[INFO] Nothing to compile - all classes are up to date
[INFO]
[INFO] >>> exec-maven-plugin:1.2.1:java (default-cli) @ org.example.maven >>>
[INFO]
[INFO] <<< exec-maven-plugin:1.2.1:java (default-cli) @ org.example.maven <<<
[INFO]
[INFO] --- exec-maven-plugin:1.2.1:java (default-cli) @ org.example.maven ---
app is running!
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 1.342s
[INFO] Finished at: Fri Jan 24 23:56:41 CST 2014
[INFO] Final Memory: 5M/15M
[INFO] ------------------------------------------------------------------------
D:\Progs\Enide-Monster-08-kepler-win32\runtime-EclipseApplication\org.example.maven>D:\Code\springsource\3.0\apache-maven-3.0.3\bin\mvn.bat compile exec:java -Dexec.mainClass=maven
.MainClass
[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Building org.example.maven 0.0.1-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO]
[INFO] --- maven-resources-plugin:2.4.3:resources (default-resources) @ org.example.maven ---
[WARNING] Using platform encoding (Cp1251 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] Copying 0 resource
[INFO]
[INFO] --- maven-compiler-plugin:2.3.2:compile (default-compile) @ org.example.maven ---
[INFO] Nothing to compile - all classes are up to date
[INFO]
[INFO] >>> exec-maven-plugin:1.2.1:java (default-cli) @ org.example.maven >>>
[INFO]
[INFO] <<< exec-maven-plugin:1.2.1:java (default-cli) @ org.example.maven <<<
[INFO]
[INFO] --- exec-maven-plugin:1.2.1:java (default-cli) @ org.example.maven ---
app is running!
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 1.435s
[INFO] Finished at: Fri Jan 24 23:57:46 CST 2014
[INFO] Final Memory: 5M/15M
[INFO] ------------------------------------------------------------------------