========================================================
        SOFTWARE ENGINEERING LAB — EXAM CHEAT SHEET
========================================================

========================================================
1. GIT + GITHUB
========================================================

CLONE PROJECT
--------------
git clone <GITHUB-URL>                 # Download repository
cd <PROJECT-FOLDER>                    # Enter project
git status                             # Check Git status
git remote -v                          # Check remote URL


CREATE / SWITCH BRANCH
----------------------
git branch                             # List local branches
git branch -a                          # List all branches
git branch --show-current              # Show current branch
git switch -c <branch-name>            # Create + switch to new branch
git switch <branch-name>               # Switch to existing branch


EDIT + CHECK CHANGES
--------------------
git status                             # See modified/untracked files
git diff                               # See exact changes
git add .                              # Stage all changes
git add <filename>                     # Stage one file
git commit -m "message"                # Create commit
git log --oneline                      # View commit history


UNSTAGE FILE
------------
git restore --staged <filename>        # Unstage but KEEP file


UNDO COMMIT
-----------
git log --oneline                      # Find commit ID
git revert <commit-id>                 # Undo commit, preserve history


STASH
-----
git stash                              # Temporarily save uncommitted work
git stash list                         # View saved stashes
git stash pop                          # Restore latest stash

git stash
git switch <urgent-branch>             # Switch to existing branch
# Do urgent work
git switch <feature-branch>
git stash pop


REBASE
------
git fetch origin                       # Get latest remote information
git rebase origin/main                 # Put feature commits on latest main
git add .
git rebase --continue                  # Continue after resolving conflict
git rebase --abort                     # Cancel rebase


MERGE
-----
git switch main                        # Switch to main
git merge <feature-branch>             # Merge feature into main


RECOVER LOST COMMIT
-------------------
git reflog                             # Find disappeared/lost commit


COMPARE BRANCHES
----------------
git diff <branch1> <branch2> -- <file> # Compare file between branches


AMEND LAST COMMIT
-----------------
git commit --amend --no-edit           # Modify previous commit


RESET
-----
git reset --soft HEAD~1                # Undo last commit, keep changes staged


STOP TRACKING FILE
------------------
git rm --cached <filename>             # Untrack file, KEEP locally
echo <filename> >> .gitignore          # Add file to ignore
git add .gitignore
git commit -m "Update gitignore"


GRAPH / HISTORY
---------------
git log --oneline --graph --decorate --all
                                      # Show branch graph + commits


PUSH TO GITHUB
--------------
git remote add origin <GITHUB-URL>     # Connect local repo to GitHub
git branch -M main                     # Rename branch to main
git push -u origin main                # Push + set upstream

git push origin main                   # Push later changes


========================================================
2. MAVEN
========================================================

IMPORTANT:
Run Maven commands INSIDE THE PROJECT FOLDER
WHERE pom.xml IS PRESENT.


CHECK MAVEN / JAVA
------------------
mvn -v                                 # Show Maven + Java version


MAIN BUILD COMMANDS
-------------------
mvn clean                              # Delete old target/build output
mvn compile                            # Compile source code
mvn test                               # Run tests
mvn package                            # Create JAR/WAR in target
mvn clean install                      # Full clean build + install


DEBUG BUILD
-----------
mvn clean package -X                  # Detailed/debug Maven output


DEPENDENCY TROUBLESHOOTING
--------------------------
mvn dependency:tree                    # Show dependencies + versions
mvn dependency:analyze                 # Analyze dependency usage


RUN ONE TEST
------------
mvn -Dtest=TestClassName test          # Run only one test

Example:
mvn -Dtest=MaintenanceBillingTest test


SKIP TESTS
----------
mvn package -DskipTests                # Package without running tests


========================================================
3. pom.xml — IMPORTANT PARTS
========================================================

BASIC STRUCTURE
---------------

<project>

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>       <!-- Project/group -->
    <artifactId>MyApp</artifactId>       <!-- Application name -->
    <version>1.0-SNAPSHOT</version>      <!-- Version -->

    <packaging>war</packaging>            <!-- jar or war -->

    <dependencies>                        <!-- External libraries -->

        <dependency>
            <groupId>...</groupId>
            <artifactId>...</artifactId>
            <version>...</version>
            <scope>...</scope>
        </dependency>

    </dependencies>

    <build>

        <finalName>MyApp</finalName>      <!-- Output filename -->

        <plugins>                          <!-- Active plugins -->
            ...
        </plugins>

    </build>

</project>


COMMON POM FIXES
----------------

BROKEN:
<scope>provided

FIX:
<scope>provided</scope>


MYSQL DEPENDENCY:
<dependency>
    <groupId>com.mysql</groupId>
    <artifactId>mysql-connector-j</artifactId>
    <version>8.0.33</version>
</dependency>


JUNIT:
<dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.13.2</version>
    <scope>test</scope>
</dependency>


WAR NAME:
<finalName>ApartmentMaintenanceSystem</finalName>

Result:
target/ApartmentMaintenanceSystem.war


TOMCAT PLUGIN:
<plugin>
    <groupId>org.apache.tomcat.maven</groupId>
    <artifactId>tomcat7-maven-plugin</artifactId>
    <version>2.2</version>

    <configuration>
        <path>/</path>
        <port>8080</port>
    </configuration>
</plugin>


PLUGIN MANAGEMENT:
<pluginManagement>
    ...
</pluginManagement>

# Manages/defaults plugin configuration

<plugins>
    ...
</plugins>

# Activates plugin for the build


SNAPSHOT:
1.0-SNAPSHOT = development version
Release version = fixed/stable version


DEPENDENCY CONFLICT:
mvn dependency:tree                 # Find which versions are coming in


JDK / JAVA VERSION:
mvn -v                               # Check Maven + Java version


========================================================
4. DOCKER
========================================================

IMPORTANT:
Usually work from PROJECT ROOT.
The built JAR/WAR should be available in target/.


DOCKERFILE
----------

Create a file named:

Dockerfile

Put:

FROM openjdk:17-jdk-slim
WORKDIR /app
COPY target/<application>.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","app.jar"]

FROM = Base Java image
WORKDIR = Working directory inside container
COPY = Copy application into container
EXPOSE = Application port
ENTRYPOINT = Command used to start application


BUILD IMAGE
-----------
docker build -t <image-name> .
                                      # Build Docker image


RUN CONTAINER
-------------
docker run -d --name <container-name> -p 8080:8080 <image-name>

-d = Run in background
--name = Container name
-p = Port mapping

8080:8080
   ↑   ↑
 host container


CHECK CONTAINERS
----------------
docker ps                              # Running containers
docker ps -a                           # All containers


ENTER CONTAINER
---------------
docker exec -it <container-name> /bin/sh
                                      # Open shell inside container


STOP / START
------------
docker stop <container-name>           # Stop container
docker start <container-name>          # Start container


DOCKERHUB
---------
docker login                           # Login to DockerHub

docker commit <container-id> <username>/<image>:v1
                                      # Create/tag image from container

docker push <username>/<image>:v1      # Push image to DockerHub

docker logout                          # Logout


========================================================
5. MASTER EXAM FLOWS
========================================================


GIT BASIC FLOW
--------------
git clone <URL>
cd <PROJECT>
git status
git switch -c feature-name

# Edit files

git diff
git add .
git commit -m "message"
git push origin feature-name


GIT URGENT WORK FLOW
--------------------
git stash
git switch <urgent-branch>

# Fix urgent issue

git switch <feature-branch>
git stash pop


GIT REBASE FLOW
---------------
git fetch origin
git rebase origin/main

# Resolve conflicts

git add .
git rebase --continue

# OR cancel:
git rebase --abort


GIT MERGE FLOW
--------------
git switch main
git merge <feature-branch>
git push origin main


MAVEN FLOW
----------
cd <PROJECT-WITH-pom.xml>

mvn -v
mvn clean
mvn compile
mvn test
mvn package
mvn clean install


MAVEN TROUBLESHOOTING
---------------------
Dependency problem:
mvn dependency:tree

Dependency analysis:
mvn dependency:analyze

Debug:
mvn clean package -X

One test:
mvn -Dtest=TestName test

Skip tests:
mvn package -DskipTests

POM problem:
Open pom.xml → find incorrect part → fix → build again


DOCKER FLOW
-----------
cd <PROJECT>

# Make sure target/<app>.jar exists

# Create Dockerfile

docker build -t <image-name> .

docker run -d --name <container-name> -p 8080:8080 <image-name>

docker ps

# Test:
http://localhost:8080

docker stop <container-name>
docker start <container-name>

docker login
docker push <username>/<image>:v1
docker logout


========================================================
6. IF YOUR BRAIN GOES BLANK TOMORROW 😭
========================================================

Git:
clone → status → branch → edit → diff → add → commit
→ stash → fetch → merge/rebase → revert → reflog → push

Maven:
mvn -v → clean → compile → test → package → install

Dependency issue:
pom.xml / dependency:tree

Debug:
-X

One test:
-Dtest=Name test

Skip tests:
-DskipTests

Docker:
Dockerfile → build → run → ps → stop/start → login → push


========================================================
IMPORTANT
========================================================

DO NOT blindly paste the same POM/Dockerfile into every question.

Read what the examiner asks.

Change ONLY the relevant dependency / version / scope /
plugin / packaging / finalName / configuration.

Exact filenames, artifact names, ports and dependencies can
change depending on the project/set.
========================================================
