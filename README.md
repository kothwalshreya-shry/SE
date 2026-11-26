**SRS · UML · GIT/GITHUB**

Quick revision for tomorrow's practical examination

# **1. SRS – Software Requirement Specification**

**SRS:** A document describing what a software system should do and how it should perform.

### **Abstract – Remember this format**

"The [System Name] is a software application designed to [purpose]. It helps [users] to [activities]. The system provides features such as [features]. It aims to improve efficiency, accuracy, security and user convenience."

### **Functional Requirements (WHAT the system does)**

1. User registration and login.
2. Manage user profiles.
3. Search and view information.
4. Add, update and delete records.
5. Book or place requests.
6. Process payments.
7. Track status.
8. Send notifications.
9. Generate reports.
10. Admin management.

Adapt each point to the actual scenario. Don't include irrelevant features.

### **Non-Functional Requirements (HOW WELL it works)**

| No. | Requirement       | Meaning                    |
| --- | ----------------- | -------------------------- |
| 1   | Performance       | Fast response              |
| 2   | Security          | Data protection            |
| 3   | Reliability       | No frequent failures       |
| 4   | Availability      | Accessible when needed     |
| 5   | Usability         | User-friendly              |
| 6   | Scalability       | Handles more users         |
| 7   | Maintainability   | Easy to update             |
| 8   | Compatibility     | Works on different devices |
| 9   | Accuracy          | Correct results            |
| 10  | Backup & Recovery | Recover lost data          |

# **2. UML – All four diagrams**

## **A. Use Case Diagram**

Structural / Behavioural interaction view

**Purpose:** Shows interaction between users and the system.

| Element         | Symbol                              |
| --------------- | ----------------------------------- |
| Actor           | Stick figure                        |
| Use Case        | Oval                                |
| System Boundary | Rectangle                           |
| Association     | Solid line                          |
| Include         | Dashed arrow labelled `<<include>>` |
| Extend          | Dashed arrow labelled `<<extend>>`  |

**Remember:**

- Actors OUTSIDE the rectangle.
- Use cases INSIDE the rectangle.
- Lines connect actors and use cases.

**StarUML:** Model → Add Diagram → Use Case Diagram → Actor → Use Case → Association.

## **B. Class Diagram**

Structural diagram

**Purpose:** Shows classes, attributes, methods and relationships.

Every class has 3 compartments:

```
----------------------
       Patient
----------------------
- patientId: int
- name: String
- age: int
----------------------
+ bookAppointment()
+ viewRecords()
----------------------
```

| Symbol          | Meaning     |
| --------------- | ----------- |
| `+`             | Public      |
| `-`             | Private     |
| `#`             | Protected   |
| Solid line      | Association |
| Hollow triangle | Inheritance |
| Hollow diamond  | Aggregation |
| Filled diamond  | Composition |

**StarUML:** Model → Add Diagram → Class Diagram → Class → Add Attributes → Add Operations → Association.

## **C. Sequence Diagram**

Behavioural diagram

**Purpose:** Shows interactions between objects in chronological order.

| Element        | Meaning                 |
| -------------- | ----------------------- |
| Actor/Object   | Participant             |
| Lifeline       | Dashed vertical line    |
| Message        | Horizontal arrow        |
| Activation     | Thin vertical rectangle |
| Return Message | Dashed arrow            |

**Remember: TIME FLOWS TOP TO BOTTOM.**

Example – Food Ordering:

Participants:

1. Customer
2. Food Ordering System
3. Payment Gateway
4. Restaurant

Message sequence:

```
Customer -> System: login()
System -> Customer: loginSuccess()
Customer -> System: viewMenu()
System -> Customer: displayMenu()
Customer -> System: placeOrder()
System -> Payment: processPayment()
Payment -> System: paymentSuccess()
System -> Restaurant: sendOrder()
Restaurant -> System: confirmOrder()
System -> Customer: orderConfirmation()
```

**StarUML:** Model → Add Diagram → Sequence Diagram → Lifeline → Message.

## **D. Component Diagram**

Structural diagram

**Purpose:** Shows software components/modules and their dependencies.

Example – Online Gaming:

Components:

1. User Interface
2. Authentication
3. Game Engine
4. Player Management
5. Leaderboard
6. Database

Relationships:

```
User Interface -> Authentication
User Interface -> Game Engine
Game Engine -> Player Management
Game Engine -> Leaderboard
Authentication -> Database
Player Management -> Database
Leaderboard -> Database
```

**StarUML:** Model → Add Diagram → Component Diagram → Component → Dependency.

### **UML comparison – Very important viva**

| Diagram   | Represents                | Category    |
| --------- | ------------------------- | ----------- |
| Use Case  | User interactions         | Behavioural |
| Class     | Classes and relationships | Structural  |
| Sequence  | Message order             | Behavioural |
| Component | Software modules          | Structural  |

# **3. StarUML – Common practical steps**

1. Open StarUML.
2. File → New.
3. Right-click Model in Model Explorer.
4. Select Add Diagram.
5. Choose the required diagram.
6. Select elements from Toolbox.
7. Place elements on canvas.
8. Rename elements.
9. Connect using appropriate relationships.
10. Arrange neatly.
11. Ctrl + S to save.

Useful: Use Export Diagram when asked to save or submit the diagram as an image.

# **4. GIT & GITHUB – Complete command cheat sheet**

## **A. Installation and configuration**

| Command                                  | Purpose            |
| ---------------------------------------- | ------------------ |
| `git --version`                          | Check Git version  |
| `git config --global user.name "Name"`   | Set username       |
| `git config --global user.email "email"` | Set email          |
| `git config --list`                      | View configuration |

## **B. Repository commands**

| Command                   | Purpose                    |
| ------------------------- | -------------------------- |
| `git init`                | Initialize repository      |
| `git clone URL`           | Clone repository           |
| `git status`              | Check file status          |
| `git add filename`        | Stage a file               |
| `git add .`               | Stage all changes          |
| `git commit -m "message"` | Commit changes             |
| `git show`                | Show latest commit details |

## **C. Branching commands**

| Command                   | Purpose              |
| ------------------------- | -------------------- |
| `git branch`              | List branches        |
| `git branch feature`      | Create branch        |
| `git checkout feature`    | Switch branch        |
| `git checkout -b feature` | Create and switch    |
| `git switch main`         | Switch to main       |
| `git branch -d feature`   | Delete merged branch |

## **D. Merge and Rebase**

| Command              | Purpose                           |
| -------------------- | --------------------------------- |
| `git merge feature`  | Merge feature into current branch |
| `git rebase main`    | Rebase current branch onto main   |
| `git merge --abort`  | Abort merge in progress           |
| `git rebase --abort` | Abort rebase in progress          |

## **E. Stash commands**

| Command           | Purpose                        |
| ----------------- | ------------------------------ |
| `git stash`       | Temporarily save changes       |
| `git stash list`  | List stashes                   |
| `git stash apply` | Restore without removing stash |
| `git stash pop`   | Restore and remove stash entry |
| `git stash drop`  | Delete stash entry             |

## **F. Diff and Log**

| Command                           | Purpose                   |
| --------------------------------- | ------------------------- |
| `git diff`                        | Show unstaged differences |
| `git diff --staged`               | Show staged differences   |
| `git log`                         | Show commit history       |
| `git log --oneline`               | Compact commit history    |
| `git log --graph --oneline --all` | Graphical commit history  |

## **G. Reset and Revert**

| Command                    | Purpose                                  |
| -------------------------- | ---------------------------------------- |
| `git reset --soft HEAD~1`  | Undo commit, keep staged changes         |
| `git reset --mixed HEAD~1` | Undo commit, keep unstaged changes       |
| `git reset --hard HEAD~1`  | Undo commit and discard changes          |
| `git revert COMMIT_ID`     | Create a commit reversing another commit |



Careful

&#x20;Hard reset can permanently discard work.



## **H. Remote commands – GitHub**

| Command                     | Purpose                     |
| --------------------------- | --------------------------- |
| `git remote -v`             | View remote URLs            |
| `git remote add origin URL` | Connect GitHub repository   |
| `git fetch origin`          | Download remote updates     |
| `git pull origin main`      | Fetch and integrate updates |
| `git push origin main`      | Push commits to GitHub      |
| `git push -u origin main`   | Push and set upstream       |
| `git push`                  | Push to configured upstream |

### **Git workflow – Memorise this!**

**git init**

Create repository

**git add .**

Stage files

**git commit -m "message"**

Save changes

**git push**

Upload to GitHub

# **5. Git vs GitHub – Viva questions**

| Question                  | Answer                                             |
| ------------------------- | -------------------------------------------------- |
| What is Git?              | Distributed version control system.                |
| What is GitHub?           | Online Git repository hosting platform.            |
| What is a repository?     | Project files and their version history.           |
| What is a commit?         | A saved snapshot of changes.                       |
| What is staging?          | Preparing changes before committing.               |
| What is HEAD?             | Reference to the current commit.                   |
| What is origin?           | Default remote repository name.                    |
| What is a merge conflict? | When Git cannot automatically combine changes.     |
| What is `.git`?           | Hidden directory containing Git metadata.          |
| What is a fork?           | A personal copy of another GitHub repository.      |
| What is a pull request?   | A proposal to merge changes into another branch.   |
| What is `.gitignore`?     | File specifying untracked files Git should ignore. |

# **6. Last-minute differences – Examiner favourites**

| Compare              | Difference                                  |
| -------------------- | ------------------------------------------- |
| FR vs NFR            | What system does vs how well it works       |
| Use Case vs Class    | User interaction vs system structure        |
| Class vs Component   | Classes vs software modules                 |
| Sequence vs Activity | Interaction order vs workflow               |
| Git vs GitHub        | Version control vs online hosting           |
| Init vs Clone        | Create local repo vs copy remote repo       |
| Fetch vs Pull        | Download updates vs download and integrate  |
| Merge vs Rebase      | Combine histories vs reapply commits        |
| Reset vs Revert      | Move branch reference vs create undo commit |
| Stash vs Commit      | Temporary save vs permanent history record  |


///////////////////////////////////////////////////////////////////////////////////////////////

# **Nagios — Tiny Exam Cheatsheet 💗**

**Aim:** Monitor hosts and services using Nagios Core.

**Commands**

```
sudo systemctl start nagios4
sudo systemctl start apache2
sudo systemctl status nagios4
sudo systemctl restart nagios4
nagios4 -v /etc/nagios4/nagios.cfg
```

**Dashboard:** `http://localhost/nagios4`

**Configuration files**

- `/etc/nagios4/nagios.cfg` — Main configuration
- `/etc/nagios4/conf.d/` — Additional configurations
- `/usr/lib/nagios/plugins/` — Plugins

**Four states**

- OK — Working
- WARNING — Minor problem
- CRITICAL — Serious problem
- UNKNOWN — Cannot determine status

**Important terms**

- Host — Device being monitored
- Service — Application/resource monitored
- Plugin — Performs monitoring checks
- NRPE — Executes checks on remote Linux machines
- Apache — Web server

////////////////////////////////////////////////////////////////////////////////////////

OHHH, yes bbg! You want an **actual practical example matching your SE question papers**, not just definitions. Let's use the project/repository examples from your uploaded SE practical answer material.

# **Maven Java — example practical**

Let's take a Java application called **Metro Management System**.

Your question material includes this repository:

[MetroRepo — GitHub repository](https://github.com/anujyog1/MetroRepo.git?utm_source=chatgpt.com)

The idea is to build a Java project using Maven and generate a JAR file.

## **1. Aim**

To build and manage a Java application using Maven.

## **2. Project structure**

```
MetroProject/
│
├── pom.xml
└── src/
    └── main/
        └── java/
            └── App.java
```

## **3. Java program — App.java**

```
public class App {
    public static void main(String[] args) {
        System.out.println("Metro Management System");
        System.out.println("Maven Build Successful!");
    }
}
```

## **4. pom.xml**

This is the Maven configuration file.

```
<project xmlns="http://maven.apache.org/POM/4.0.0"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
 https://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.metro</groupId>
    <artifactId>MetroProject</artifactId>
    <version>1.0</version>

    <properties>
        <maven.compiler.source>17</maven.compiler.source>
        <maven.compiler.target>17</maven.compiler.target>
    </properties>

</project>
```

## **5. Commands to execute in the exam**

First clone the repository if the question provides one:

```
git clone https://github.com/anujyog1/MetroRepo.git
cd MetroRepo
```

Check the project:

```
dir
```

Find and inspect `pom.xml`. Then execute:

```
mvn clean
mvn compile
mvn test
mvn package
```

**What each command does**

| Command       | Output/action           |
| ------------- | ----------------------- |
| `mvn clean`   | Deletes old build files |
| `mvn compile` | Compiles Java code      |
| `mvn test`    | Runs tests              |
| `mvn package` | Generates JAR/WAR       |

**Expected result: BUILD SUCCESS**

Generated artifact will be inside the `target/` folder.

**Important:** The Metro repository must actually contain a Maven `pom.xml` before you use these commands. If it is a web project, it may generate a WAR instead of a JAR. Check the supplied repository rather than assuming.

//////////////////////////////////////////////////////////////////////////////////

# **Maven Web — Tiny Cheatsheet 💗**

**Aim:** Build and deploy a Maven Web Application using Tomcat.

**Example:** Online Event Management System

**Repository:**

```
git clone https://github.com/haleema91/LAB-INTERNAL-II-OEMS.git
cd LAB-INTERNAL-II-OEMS
```

**Build commands:**

```
mvn clean package
ls target/
```

**Deploy WAR:**

```
sudo cp target/*.war /var/lib/tomcat*/webapps/
sudo systemctl restart tomcat
sudo systemctl status tomcat
```

**Browser:** `http://localhost:8080/OnlineEventManagement/`

**Remember:**

- `pom.xml` — Maven configuration.
- WAR — Web Application Archive.
- Tomcat — Application server.
- `target/` — Generated WAR file.
- `mvn clean package` — Builds the application.


/////////////////////////////////////////////////////////////////////////////////////////

Of courseee bbg 😭❤️ Here's the **complete Jenkins Java Freestyle workflow**, from creating the job to checking the final output. This is the exam-style sequence based on your SE Lab practical answer book.

# **Jenkins – Java Project (Freestyle)**

**Aim:** To automate the building and testing of a Java project using Jenkins.

**What happens?**

**GitHub Repository**

**Jenkins Job**

**Build → Test → Package**

**BUILD SUCCESS + Archived Artifact**

## **Step 1: Create a Jenkins job**

1. Open Jenkins in your browser.
2. Click **New Item**.
3. Enter `JavaProject`.
4. Select **Freestyle project**.
5. Click **OK**.

## **Step 2: Configure source code management**

1. Open the job's **Configure** page.
2. Go to **Source Code Management**.
3. Select **Git**.
4. Enter the repository URL given in the question.
5. Under Branches to build, enter `*/main` or `*/master` after checking the repository's default branch.

Example URL from your answer book:

```
https://github.com/sarasrija/SportSystem.git
```

Use the exact repository specified in your exam question, not necessarily this example.

## **Step 3: Configure build trigger**

1. Go to **Build Triggers**.
2. Select **Poll SCM**.
3. Enter:

```
H/5 * * * *
```

This checks for source-code changes approximately every five minutes.

## **Step 4: Configure build steps**

1. Go to **Build Steps**.
2. Choose **Invoke top-level Maven targets**, if the Maven Integration plugin and Maven tool are configured.
3. Enter these goals:

```
clean compile test package
```

Alternatively, use **Execute shell** on Linux or **Execute Windows batch command** on Windows:

```
mvn clean package
```

Use the option supported by the lab's Jenkins setup.

## **Step 5: Archive artifacts**

1. Go to **Post-build Actions**.
2. Select **Archive the artifacts**.
3. Enter the appropriate pattern:

For a web project:

```
target/*.war
```

For a Java JAR project:

```
target/*.jar
```

## **Step 6: Save and build**

1. Click **Save**.
2. Click **Build Now**.
3. Open the build number under **Build History**.
4. Click **Console Output**.
5. Check whether the build completed successfully.

## **Step 7: Expected result**

Successful build

You should see:

```
BUILD SUCCESS
Finished: SUCCESS
```

The generated `.jar` or `.war` file should be available under the Jenkins build's **Archived Artifacts**.

## **Important things to check before starting**

- JDK must be configured under **Manage Jenkins → Tools**.
- Maven must be configured if you're using Maven build goals.
- Use `sh` for Linux agents and `bat` for Windows agents.
- The repository URL and branch must be correct.&#x20;

  Brand_Guidelines_SE.docx



## **Tiny exam cheatsheet**

| Step | What to do                      |
| ---- | ------------------------------- |
| 1    | New Item → Freestyle project    |
| 2    | SCM → Git → Repository URL      |
| 3    | Branch → `*/main` or `*/master` |
| 4    | Build Trigger → Poll SCM        |
| 5    | Build → `mvn clean package`     |
| 6    | Archive → `target/*.jar`        |
| 7    | Save → Build Now                |
| 8    | Console Output → BUILD SUCCESS  |


////////////////////////////////////////////////////////////////////////////////////

NEXTTT 😭❤️ **Jenkins – Web Project (Maven Web)**

This is similar to Jenkins Java, but now we're building a **web application that generates a WAR file**.

## **Aim**

To automate the build and deployment process of a web project using Jenkins.

### **Step 1: Create a job**

1. Open Jenkins Dashboard.
2. Click **New Item**.
3. Enter `OnlineEventManagement`.
4. Select **Freestyle project**.
5. Click **OK**.

### **Step 2: Configure Git**

Go to **Configure → Source Code Management → Git**.

Repository URL (example from your lab material):

```
https://github.com/haleema91/LAB-INTERNAL-II-OEMS.git
```

Branch: `*/main` (verify the repository's default branch first).

### **Step 3: Build trigger**

Go to **Build Triggers → Poll SCM**.

```
H/5 * * * *
```

### **Step 4: Build the web project**

Go to **Build Steps → Execute Shell** (Linux):

```
mvn clean package
```

### **Step 5: Archive the WAR file**

Go to **Post-build Actions → Archive the artifacts**.

```
target/*.war
```

### **Step 6: Build and verify**

- Click **Save**.
- Click **Build Now**.
- Open **Console Output**.
- Check for `BUILD SUCCESS`.
- Check **Archived Artifacts** for the WAR file.

### **Step 7: Deploy using Tomcat (if required)**

```
sudo cp target/*.war /var/lib/tomcat*/webapps/
sudo systemctl restart tomcat
sudo systemctl status tomcat
```

Open the application using the Tomcat URL and the actual WAR context path.

Expected result

```
BUILD SUCCESS
Finished: SUCCESS
```

////////////////////////////////////////////////////////////////////////////////////////////////

NEXTTT BBGG 😭💗 Now **Jenkins – Scripted Pipeline**.

This is different from Freestyle because instead of configuring every build step through buttons, we write the entire workflow using a **Groovy script**.

## **Aim**

To automate checkout, cleaning, compilation, testing and packaging using a Jenkins Scripted Pipeline.

### **Step 1: Create a Pipeline job**

1. Open Jenkins Dashboard.
2. Click **New Item**.
3. Enter `SportSystemPipeline`.
4. Select **Pipeline** (not Freestyle project).
5. Click **OK**.

### **Step 2: Configure the pipeline**

1. Scroll down to the **Pipeline** section.
2. Select **Pipeline script** under Definition.
3. Paste this script:

```

node {
    stage('Checkout') {
        git branch: 'main',
            url: 'https://github.com/sarasrija/SportSystem.git'
    }

    stage('Clean') {
        echo "Build number: ${env.BUILD_NUMBER}"
        sh 'mvn clean'
    }

    stage('Compile') {
        sh 'mvn compile'
    }

    stage('Test') {
        sh 'mvn test'
    }

    stage('Package') {
        sh 'mvn package'
    }

    stage('Archive') {
        archiveArtifacts artifacts: 'target/*.war',
                         fingerprint: true
    }
}

```

**Remember:** Use the repository and branch specified in your exam question. This is the SportSystem example from your answer book.

### **Step 3: Save and execute**

1. Click **Save**.
2. Click **Build Now**.
3. Open the build number.
4. Click **Console Output**.
5. Verify that all stages execute successfully.

### **Step 4: Expected output**

**Pipeline stages**

Success

Checkout

Passed

Clean

Passed

Compile

Passed

Test

Passed

Package

Passed

Archive

Passed

**Finished: SUCCESS**

### **Important viva**

| Question                    | Answer                                           |
| --------------------------- | ------------------------------------------------ |
| What is Pipeline?           | A sequence of automated build stages.            |
| What is Groovy?             | The scripting language used by Jenkins Pipeline. |
| What is `node`?             | Allocates an executor/workspace.                 |
| What is `stage`?            | Represents a step/group in the pipeline.         |
| What is `sh`?               | Executes Linux shell commands.                   |
| What is `archiveArtifacts`? | Stores generated build files.                    |
| What is `BUILD_NUMBER`?     | Jenkins' current build number.                   |

///////////////////////////////////////////////////////////////////////////////////////

NEXTTT BBGG 😭❤️ Now we're moving to **Kubernetes – Deploy and Scale NGINX using Minikube**.

## **Aim**

To deploy an NGINX application using Kubernetes and scale the number of replicas.

**First, understand these terms:**

- **Kubernetes:** Container orchestration tool.
- **Minikube:** Runs a local Kubernetes cluster.
- **Pod:** Smallest deployable unit in Kubernetes.
- **Deployment:** Manages Pods and replicas.
- **Service:** Exposes the application to access it.

## **Complete practical workflow**

### **Step 1: Start Minikube**

Open the terminal:

```
minikube start --driver=docker
```

This starts the local Kubernetes cluster using Docker.

### **Step 2: Create NGINX deployment**

```
kubectl create deployment nginx --image=nginx --replicas=2
```

This creates an NGINX deployment with 2 replicas.

### **Step 3: Check deployment and Pods**

```
kubectl get deployments
kubectl get pods -o wide
```

You should see two NGINX Pods running.

### **Step 4: Expose the deployment**

```
kubectl expose deployment nginx --type=NodePort --port=80
```

This exposes NGINX through a NodePort service.

### **Step 5: Check service**

```
kubectl get services
```

### **Step 6: Open NGINX in browser**

```
minikube service nginx --url
```

Copy the URL displayed and open it in your browser.

You should see the NGINX welcome page!

### **Step 7: Scale the deployment**

```
kubectl scale deployment nginx --replicas=4
```

Now NGINX runs with four replicas.

Verify:

```
kubectl get deployments
kubectl get pods
kubectl get services
```

Expected result

Deployment successfully scaled from 2 replicas to 4 replicas.
