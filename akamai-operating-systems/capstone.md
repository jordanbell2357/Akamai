# Capstone

Akamai is an international leader in cyber-security and content delivery. Its customer list includes many clients that are household names across the globe. 

For the capstone projects in this certificate program, all the capstone projects will take place in the context of a made-up scenario.  In this scenario, Akamai would like to create a new project to attract customers in the Small Office Home Office (SOHO) market. The company has tasked you with starting a small subsidiary dedicated to this market. Throughout the course, you will complete projects that focus on cyber security and building this fictitious company.

For this capstone, Akamai has ordered a file server for your company to use.

## Task A

Create a name for this company.

## Task B

Decide on an authentication system for your file server:

What usernames will you use? (You may assume that your company will have 2 employees and 2 interns that will work for 6 months.)

Do you plan to customize those accounts? How? (Example: will some accounts have expiration dates?  Will you use the default home directories? Will the default profiles be customized in any way?)

Decide on a file structure:

What data will you need to store on the server?

What directories will you create to support these needs?(Minimum of two directories.)

Will you need any groups to accomplish the security needs for this data?

Will there be any hidden files, files with special permissions or any files/directories that are immutable?

How will you handle backing up this data?

How often will you need to back up?

Will the backup be compressed?

When will the backups be created? Will you need to use anything to ensure they are completed if you’re going to create them after your normal working hours?

## Review criteria

You will be uploading either a video or a PowerPoint presentation. You will be graded on whether this file contains the required deliverables.

## Step-By-Step Assignment Instructions

Create a virtual machine to be the file server. 

Create the users you specified.

Create the file structure you designed.(Minimum of two directories.)

Add some sample files to the directories.(Minimum of two sample files per directory. Sample files do not need to have any data in them.)

Configure any appropriate permissions to the file system.

Add any appropriate attributes or special permissions.

Create a text file that has all the commands needed to perform the backup you designed.

## Oral Presentation or PowerPoint

You may record an oral presentation or create a PowerPoint presentation. If you choose an oral presentation, try to keep it under 10 of recorded video. An oral presentation does not have to be perfect. You’re not being evaluated on your ability to edit video. If there are speaking mistakes, that’s ok. You can also choose to combine both solutions and record your PowerPoint with a voiceover. The oral presentation must capture your screen so that the viewer can see what you’ve done on the file server. Essentially, the oral presentation will be like the demos you’ve seen in the class, but it does not have to have mistakes edited out.

The oral presentation or the PowerPoint must include the following:

The name of your company.

Demonstration of the users you have created. Reference the naming system you chose and demonstrate any changes you made to the user account. If you do a demo, you can demonstrate this in the video. If you chose PowerPoint, include screenshots of the relevant information from the virtual machine.

Demonstration of the file system. If you do a demo, show the directories you created for your business. If you chose PowerPoint, include screenshots of the relevant information from the virtual machine. Show the directories, directory contents and permissions. If applicable, show the special permissions and attributes. If not applicable, mention that you have not used special permissions or attributes.

Demonstration of the backup plan. If you do a demo, show the contents of the text file you created. If you chose PowerPoint, include screenshots of the relevant information from the virtual machine. Include the contents of the text files with the commands. If you are scheduling the backup using a detached or delayed job, or with a cron task, include those commands. If the backups will not be scheduled, mention that they will be run manually.

## Recommendations 

If you’re recording a voiceover for PowerPoint, keep your presentation lean: use bullets that remind you of what you want to say but do not write everything on the slides. 

If you’re only providing a PowerPoint presentation, put enough information that your audience can understand the choices that you made.

It is more important to convey a presentation that is understandable and meets the time requirements than to present every single bit of trivia on your design. For example, you can provide a screenshot of the text file with the commands to create the backup. Instead of reading each line and explaining the exact options, provide an explanation. (Example: line one reads chmod u=rwx,g=rwx,o=r /etc/sharedfolders explanation, “I created a shared directory where whoever creates a file has full control of the file, the members of the Interns group has full control, and everyone else in the company can only read the files.”)

You can assume your audience has a basic Linux education; you do not need to explain how permissions work, what the mount command does, etc.

You do not need to narrate everything in your design during the presentation; if you show the text file with the backup plan, just point out the important information. The reviewer can pause the video if they want to read the script. 

Feel free to be creative and try your best to engage your audience. Your presentation does not have to be humorous or entertaining, but it should keep the audience interested (engaged).

There are many free software programs that will allow you to record a demonstration. OBS Studio is a great program that’s free and will record the screen. Otherwise, simply upload a PowerPoint presentation. 