---
path: abcd
date: 2020-06-06T10:07:14.931Z
title: Hello ABCD
description: Some description
---
> A crontask is  a scheduled job which runs periodically at fixed times, dates, or intervals

In this tutorial I will show you how to write a Crontask for Maximo in Jython and schedule it inside Maximo.

**Note:** If you are looking for Java based crontask. Please [see](https://maximomize.wordpress.com/2016/02/25/writing-your-first-crontask-maximo-java/ "java crontask") this tutorial

This is a very powerful feature of Maximo which can take customization to a new level. In my experience they can be more versatile than Escalations in Maximo.

Follow the following steps to create a Crontask  

# Header 1

## Header 2

### Header 3

#### Header 4

##### Header 5

###### Header 6

1. #### Write Automation Script using Jython
   Goto _System Configuration – Platform Configuration – Automation Scripts_
   Create a new script without any launch point.\
   ![Create Script](./create.jpg)
   Select jython as the script language.\
   Optionally, you can add variables. You can add LITERAL, SYSPROP and MAXVAR bindings.
   To keep it simple, we will add one line which will just print ‘Hello, from my Crontask’ in console.\
   ![script source](./scriptsource.jpg)
   In the next screen add the following line of code
   ```python
   print 'Hello, from my Crontask'
   ```
2. \##Define a New Crontask in Maximo
   Goto _System Configuration -Platform Configuration – Cron Task Setup_
   Click on the new icon to create New Cron Task. 
   Give it any name and for the class enter this `com.ibm.tivoli.maximo.script.ScriptCrontask`. This is the built in class maximo provides to run automation scripts in crontasks.  

![Cron Task Setup](./crontasksetup.jpg)

2. **Create and schedule an Instance for the crontask**
   When you select this class. Two new parameters will appear
   * `SCRIPTARG` – (optional) This is used for passing arguments to script
   * `SCRIPTNAME` – (required) This is the name of the script you want this cron to run. It is case sensitive.
