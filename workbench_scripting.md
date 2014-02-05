Title: Customizing MySQL Workbench
Date: 2014-02-04
Category: blog
Tags: mysql, workbench, python
Author: berend
Summary: Add custom python scripts and edit/add icons ans keyboard shotcuts

**Overview**

First let us outline the targets we want to archieve with this blog posting:
* Write a plugin for MySQL Workbench to do something with the sql output
* For this script add an icon to the query window toolbar and assign a shortcut to it

Since I have to work a lot with Jira, the bug/issue tracker from Atlassian, I sometimes have to put some sql results into a ticket. Jira has a description syntax that is really easy but formatting longer tables is boring, so lets automate this.

So our custom script should do the following:
* execute the current query in the query window (or selection if some text is selected)
* generate a text output with the query with code formatting and the result in a jira formatted table with header


**Writing a plugin script**
There are at least two supported languages: lua and python. I chose python. There is not much documentation, but I found this page, which links some ressource. One of them shows us how to execute a query and return the output to the text output tab of mysql workbench. This is exactly what we want. 5 min later after some string addition stuff the script is complete and works! Most of the things are straight forward, but I will explain some parts that are needed for interaction with workbench.

add code plugin here, check gist integration
