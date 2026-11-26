BABYYYY THIS IS YOUR LAST-MINUTE REVISION SHEET. 😭❤️

I've combined **SRS + all 4 UML diagrams + StarUML + Git/GitHub commands** into one exam cheat sheet. Save this and revise it before sleeping.

# **SE LAB EXTERNAL – MASTER CHEAT SHEET**

# **Q1 + Q2 + Q3**

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

### **SRS scenarios from your papers**

- Food Ordering System
- Hospital Management System
- Campus Event Management System
- Online Gaming System
- Library Automation System
- Book Bank System

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

Example – Campus Event Management:

- Actors: Student, Faculty, Admin.
- Use cases: Login, View Events, Register, Create Event, Manage Events, Generate Reports.

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

**Example – Hospital Management:**

Classes:

- Patient
- Doctor
- Appointment
- MedicalRecord
- Bill

Relationships:

- Patient — Appointment
- Doctor — Appointment
- Patient — MedicalRecord
- Appointment — Bill

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

