# Mention what is Jenkins?
Jenkins is an open source tool with plugin built for continuous integration purpose.  
The principle functionality of Jenkins is to keep a track of version control system and to initiate and 
monitor a build system if changes occur. It monitors the whole process and provides reports and notifications to alert.

# Explain what is continuous integration?
In software development, when multiple developers or teams are working on different segments of same web application, 
we need to perform integration test by integrating all modules.  In order to do that an automated process for 
each piece of code is performed on daily bases so that all your code get tested.

# What is the requirement for using Jenkins?
To use Jenkins you require
•A source code repository which is accessible, for instance, a Git repository
•A working build script, e.g., a Maven script, checked into the repository

# Mention what are the advantages of Jenkins?
Advantage of Jenkins include
•At integration stage, build failures are cached
•For each code commit changes an automatic build report notification generates
•To notify developers about build report success or failure, it is integrated with LDAP mail server
•Achieves continuous integration agile development and test driven development
•With simple steps, maven release project is automated
•Easy tracking of bugs at early stage in development environment than production

# Explain how you can move or copy Jenkins from one server to another?
•Slide a job from one installation of Jenkins to another by copying the related job directory
•Make a copy of an already existing job by making clone of a job directory by a different name
•Renaming an existing job by renaming a directory.

# Mention what are the commands you can use to start Jenkins manually?
To start Jenkins manually, you can use either of the following
•(Jenkins_url)/restart: Forces a restart without waiting for builds to complete
•(Jenkin_url)/safeRestart: Allows all running builds to complete

# Mention some of the useful plugins in Jenkin?
Some of the important plugins in Jenkin includes
•Maven 2 project
•Amazon EC2
•HTML publisher
•Copy artifact
•Join
•Green Balls

# Explain how you can deploy a custom build of a core plugin?
To deploy a custom field of a core plugin, you have to do following things
•Stop Jenkins
•Copy the custom HPI to $Jenkins_Home/plugins
•Delete the previously expanded plugin directory
•Make an empty file called <plugin>.hpi.pinned
•Start Jenkins

# Explain how can create a backup and copy files in Jenkins?
Jenkins saves all the setting, build artifacts and logs in its home directory, to create a back-up of your Jenkins setup, 
just copy this directory. You can also copy a job directory to clone or replicate a job or rename the directory.

# Explain how you can clone a Git repository via Jenkins?
To clone a Git repository via Jenkins, you have to enter the e-mail and user name for your Jenkins system.  
For that, you have to switch into your job directory and execute the “git config” command.

# Explain how you can set up Jenkins job?
To create a project that is handled via jobs in Jenkins.  Select New item from the menu, 
once this done enter a name for the job and select free-style job. Then click OK to create new job in Jenkins.  
The next page enables you to configure your job.

# Mention what are the two components Jenkins is mainly integrated with?
Jenkin is mainly integrated with two components
•Version Control system like GIT, SVN
•And build tools like Apache Maven.
