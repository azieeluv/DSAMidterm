Diaz, Zianne P.
Setting Up Visual Studio Code and Git for Your DSA Midterms

This guide provides step-by-step instructions on how to set up Git and GitHub for your project, including basic operations like adding files, committing changes, and pushing to a remote repository. Following these steps will ensure your development environment is ready for your Data Structures and Algorithms (DSA) midterm project.

1. Install Visual Studio Code (VS Code)

Download VS Code: Visit the official VS Code website and download the installer for your operating system (Windows or macOS). On Windows, run the installer (.exe) and follow the prompts (generally clicking "Next" through defaults). On macOS, download the .dmg and drag the VS Code app to your Applications folder.

Complete Installation: Launch VS Code to confirm it installed correctly. You should be able to find "Visual Studio Code" in your Start menu (Windows) or Applications (Mac).

2. Install Git

Download Git: Go to the official Git website and download the latest Git installer for your OS
docs.github.com
. For Windows, choose the 64-bit installer (if prompted during installation, you can enable the "Git Bash Here" option for convenience). For Mac or Linux, download the appropriate package or use a package manager (e.g. Homebrew on Mac)
docs.github.com
.

Run the Installer: Install Git with the default settings. This will also install Git Bash on Windows, a terminal that lets you use Unix-style Git commands.

Remember: Git (the version control tool) is different from GitHub (the hosting service). Git is the local software that tracks changes in your code, while GitHub is a cloud platform to store and share those changes
docs.github.com
. In fact, “Git is responsible for everything GitHub-related that happens locally on your computer”
docs.github.com
.

Verify Git Installation: After installing, restart your computer (if the installer prompts you to). Then, create or open any folder in File Explorer and right-click on it. You should see a "Git Bash Here" option in the context menu, which means Git was installed successfully. You can also open a regular Command Prompt (CMD) or terminal and run git --version to check that Git responds.

3. Create a Project Folder

Make a New Folder: Choose a location on your computer (e.g. Documents) and create a new folder for your midterm project. Name the folder using the format SurnameFirstName_DSA_Midterms. For example, if your name is Tristan Belardo, you might name it BelardoTristan_DSA_Midterms. This will keep your project files organized in one place.

Verify VS Code Installation: Search for "Visual Studio Code" on your computer and open it, or use the VS Code icon if available. If VS Code opens, it's installed correctly.

Verify Git Context Menu: Right-click your new project folder. If "Git Bash Here" appears in the context menu, then Git is correctly installed and integrated. If you do not see this option, you may need to reinstall Git (making sure to enable context menu integration during setup).

4. Open the Folder in VS Code

Now that you have VS Code installed and a project folder created, open that folder in VS Code:

Using Command Prompt (Windows): Open the project folder in Windows File Explorer. Click in the address bar at the top, type cmd, and press Enter. This will open a Command Prompt at that folder's location. In the Command Prompt, type code . and hit Enter. This command launches VS Code, opening the current folder (the . represents the current directory).

Tip: If the code . command is not recognized, it means the VS Code CLI isn’t on your PATH. In that case, you can open VS Code manually and use File > Open Folder... to select your project folder.

Using Terminal (Mac/Linux): Open a terminal, use the cd command to navigate to your project directory, then run code . to open VS Code at that location. (If this doesn’t work on Mac, you might need to install the "Shell Command: Install 'code' command in PATH" from VS Code's Command Palette).

Once VS Code opens, you should see your project folder name in the Explorer sidebar. This means VS Code is now working in the context of that folder (which will later become a Git repository).

5. Configure VS Code Settings for Git

VS Code comes with integrated source control support for Git, but let's do a bit of setup for convenience:

Open the Terminal in VS Code: In VS Code, go to View > Terminal (or press <kbd>Ctrl</kbd>+<kbd></kbd> on Windows/Linux, or <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd></kbd> on Mac). This will open an integrated terminal at the bottom of VS Code.

Select the Shell (Windows users): By default, VS Code might open PowerShell or another shell. To avoid confusion with Git commands, click the drop-down menu in the terminal window (usually says "1: powershell" or similar) and switch it to Command Prompt (CMD). You can also use Git Bash here if you prefer Unix-style commands, but the following instructions assume a standard Command Prompt on Windows.

Enable Auto Save: To prevent losing any work, enable auto-saving of files. Go to File > Auto Save and make sure it's checked. With Auto Save on, VS Code will automatically save your files whenever you pause typing, so you don't have to manually save before committing changes.

6. Install a Git Commit Message Extension (Optional)

For a smoother Git experience in VS Code, you can install the "Conventional Commits" extension:

Install Conventional Commits Extension: In VS Code, click on the Extensions icon (on the left sidebar) and search for "Conventional Commits". Install the extension named Conventional Commits. This tool helps you format your commit messages according to a standard convention (e.g. it will prompt you to choose a commit type like feat or fix, then enter a message).

Sign In to GitHub in VS Code: If you see an option to sign in to GitHub (for example, under Accounts in the VS Code status bar or the Source Control view), go ahead and sign in with your GitHub credentials. This will make it easier to interact with GitHub from VS Code and may be required for some features (like cloning from GitHub or publishing to GitHub directly). Note: The core source control functionality will work regardless, but signing in is helpful for integration.

VS Code will now be ready to work with Git. It detects Git is installed on your system and enables source control features automatically
code.visualstudio.com
. (If Git wasn’t installed, VS Code’s source control view would prompt you to install Git first.)

7. Create Your First File in the Project

Let's add a sample file to our project:

New File: In VS Code, click the New File button (or right-click in the Explorer pane) and create a file named hello_world.html. This will be a simple HTML file.

Add Content: Open hello_world.html and type a basic HTML snippet, for example:

<h1>Hello, World!</h1>
<p>This is a test page for my DSA Midterm project.</p>


Since auto-save is on, you can just pause for a moment and VS Code will save the file for you.

Confirm File Creation: You should see hello_world.html listed in the Explorer with its content on the right. We haven't put this file under version control yet — we'll do that soon.

8. Create a New Repository on GitHub

Next, set up a repository on GitHub to eventually host your project:

Log in to GitHub: Go to GitHub.com in your web browser and log in to your account (create an account first if you don't have one).

Create New Repo: Click the "New" repository button (usually a green button or a + dropdown > New repository).

Repository Settings: Fill in the repository details:

Name: DSA_Midterm (for example; you can name it as instructed by your course, but we'll use DSA_Midterm here).

Description: (optional) e.g. "Midterm project repository for DSA class".

Visibility: Choose Public (so your instructor or team can see it, unless you prefer private).

Do not check "Add a README" or any other options to add files. We want the repo to start empty since we already have files locally.

Create: Click Create repository. GitHub will set up a new (empty) repository and will show you some instructions. Keep this page open — you'll need the repository's URL for the next step. It should look something like https://github.com/YourUsername/DSA_Midterm.git. Copy that URL to your clipboard.

9. Initialize Git in Your Project Folder

Now that you have a GitHub repository online, initialize Git locally in your project folder and prepare to connect it:

Initialize a Git Repo: In VS Code's integrated terminal (make sure you are still in your project folder directory), run:

git init


This turns your project folder into a new local Git repository. (You'll notice a new hidden folder .git is created and the Source Control icon in VS Code becomes active with an indicator.)

Configure Git (if not already done): Set your user name and email for Git (this is used in your commit metadata):

git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"


Use the name and email associated with your GitHub account. You only need to do this once per machine; Git will remember it for all repositories. (If you already configured this in the past, you can skip this step.)

Why these configs? Setting your name and email is important because Git includes this information with each commit. It allows others to see who made the changes, and it should match your GitHub identity for consistency
code.visualstudio.com
.

10. Stage and Commit Your Files (Initial Commit)

With Git initialized, you can now save a snapshot of your project files:

Create a README: It's good practice to include a README file in your repo. In VS Code, create a new file called README.md (all caps). In this Markdown file, you can write a brief description of your project. For now, you might just put a title and a one-liner (you can edit it later).

Stage the file(s): In the terminal, tell Git which files to include in the next commit. For example:

git add README.md


This command stages the README file. If you also want to include the HTML file in this commit, you could stage it too (e.g. git add hello_world.html). You can stage multiple files or use git add . to stage all new files at once.

Commit the files: Now create a commit (a snapshot of the staged files in the repository) with a message:

git commit -m "Initial commit"


This packages the staged files into the repository history with the message "Initial commit". You have now made your first commit in the project’s Git history. (At this point, the commit is only local; we haven’t uploaded it to GitHub yet.)

11. Connect to GitHub and Push the Commit

Next, link your local repo with the GitHub repo you created, and upload (push) your commit to GitHub:

Set the Branch Name: By default, Git might have named your initial branch "master". GitHub now uses "main" as the default branch name. To avoid confusion, rename your branch to main:

git branch -M main


This ensures your local branch is named main (matching what GitHub expects for a new repo).

Add the Remote Origin: You need to tell Git the URL of the remote repository (on GitHub) and name it "origin":

git remote add origin <repo-url.git>


Replace <repo-url.git> with the URL you copied from GitHub (ending in .git). This command links the name "origin" to your GitHub repository. (You can check it's set by running git remote -v.)

Push to GitHub: Now push your main branch to the GitHub origin and set it as the upstream:

git push -u origin main


The first push may prompt for your GitHub username/password or a token (if you haven’t logged in via VS Code). Once authenticated, this uploads your commit to the GitHub repository. The -u flag sets the upstream tracking, so future git push commands (without arguments) will know where to send your commits.

Verify on GitHub: Visit your GitHub repository page (refresh if needed). You should now see your files (e.g., README.md, and possibly hello_world.html if you added it) listed. Congratulations – your project is now on GitHub!

(Using a remote repository on GitHub provides a backup of your work and lets you share or collaborate on code easily
docs.github.com
.)

12. Using VS Code Source Control for Future Changes

After the initial setup, you can manage changes directly in VS Code's Source Control view, which is often simpler than typing commands:

Make Changes to Your Project: For example, create a new file page1.html in your project and add some content, and edit the existing hello_world.html (maybe fix a typo or add a new line). These changes will appear in VS Code's Source Control panel (the Git icon on the left will show a number indicating pending changes).

Stage Changes in VS Code: Click on the Source Control icon. You will see a list of changed files under "CHANGES". Hover over each file and click the + (Stage Changes) button, or click Stage All to stage everything. Staged files will move to a "STAGED CHANGES" section.

Commit with Conventional Commits: Instead of using the terminal, let's use the Conventional Commits extension:

Click the Conventional Commits button (it might appear as a small checkmark icon in the Source Control view or you can press <kbd>Ctrl+Shift+P</kbd> and type "Conventional Commits").

A prompt will ask for a commit type. Choose an appropriate type from the list (for example, feat for adding a new feature or fix for fixing something). In our example, since we added a new page and maybe fixed text in hello_world, you might choose fix.

It may ask for a scope (you can skip or enter a module name if relevant), then for a description. For example: "Fixed Hello World header and added Page 1". This becomes your commit message.

When you accept, the extension will format the message and commit the staged changes. Depending on settings, it might auto-push as well, but if not, you can manually push. If you're signed in and have the upstream set, VS Code should show a Sync Changes or Push button (often with an up-arrow icon) in the status bar or next to the branch name in the bottom-left. Click that to push your commit to GitHub.

Confirm the Commit: After syncing, check the GitHub repo online again. You should see the new commit in the history, and the new file (page1.html) and updated content reflected there.

Example: You created page1.html and modified hello_world.html. Using Conventional Commits, you choose fix as the type and write a message "Fixed Hello World and added Page 1". The commit message would look like fix: Fixed Hello World and added Page 1. This commit, once pushed, appears on GitHub and anyone pulling the project will get the updates.

VS Code's Source Control makes it easy to visualize and handle changes without needing to type all the commands. It provides a GUI for staging, committing, and pushing, built on top of Git
code.visualstudio.com
code.visualstudio.com
.

13. Cloning the Repository on Another Computer

One advantage of using GitHub is that your project is now backed up to the cloud and can be accessed from anywhere. If you need to work on another computer:

Clone the Repository: On the new computer, ensure Git is installed. Then, in a terminal, run:

git clone <repo-url.git>


Use the same repository URL from earlier. This will download the entire repository (all files and history) into a new folder on that computer.

Continue Working: Open the folder in VS Code and you can continue development. You can create branches, make changes, commit, and push back to GitHub from the new location. Just remember to pull (git pull) any new changes if multiple machines or collaborators are involved, so you stay up to date.

(Your GitHub repository acts as a central source of truth for your project. By cloning, you can easily get a copy of your project on any machine. This remote backup and sharing capability is a key benefit of using GitHub
docs.github.com
.)

14. Maintaining the README.md (Project Documentation)

Now that everything is set up, don't forget to keep your README.md updated:

Purpose of README: The README file is the first thing people see when they visit your repository on GitHub. Use it to describe your project, how to run it, what the project contains, and any other relevant info. This is especially useful for your instructor or team to understand your work.

Edit and Commit: Add some information to your README.md (for example, a project title, your name, course details, and a brief description of the midterm project). Save the file, stage the changes, and commit them (you can use VS Code or git add/git commit in the terminal). Don't forget to push the commit so the changes reflect on GitHub.

Format with Markdown: README files are written in Markdown, a simple formatting language. Below are some basics to make your README more readable.

15. Markdown Basics for README

Markdown allows you to add formatting using plain text markup. Here are a few examples you can use in README.md:

# Heading 1 
## Heading 2 
**Bold text** 
Regular text for paragraphs.
- Bullet list item 1  
- Bullet list item 2


The # at the start of a line makes a heading. # for a main heading, ## for sub-headings, etc.

Surrounding text with ** ** makes it bold. For italic, use one asterisk each side (*italic*).

Just writing plain text will produce normal paragraph text.

Using - or * will create bullet points, as shown above.

When you view your repository on GitHub, the Markdown in README.md will automatically render with this formatting. For example, # Heading 1 will appear as a large title. Use these formatting tools to make your README informative and nice-looking.
