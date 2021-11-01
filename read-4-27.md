# Intents, Activities, and SharedPreferences

Understand Tasks and Back Stack
**Tasks:**
It is a collection of metadata and information around a stack of activities.

The activities are arranged in a stack—the back stack—in the order in which each activity is opened.

“last in, first out” stack.

startActivity():pushing a new activity onto your task causing stop or pause the previous activity if exists.

finish():it pops the stack,removing activity from the back stack and moving to the previous stak.

**app tasks in stack.**
1. when user open application in the home screen, the application task is brought to the front of the screen.

2. open a task and fire another task from this task it will add new activity on top of previous activity in the stack.

3. when the activity is stopped it will be removed from stack and previous one continue.

4. activity in back stack only pushed and poped from stack.

5. for example when i open what's app then go to status and open one status.

6. these were 3 activites added to a stack and ther application is a task.

7. when i press back it will take me back to list of status and kill previous activity and so on.

8. when i back to home page, task back to background activities are poped out but task remain.

9. when i give user chance to open ativity from different places, it will create instance each time user click on it

**Using the manifest file (Links to an external site.)**
we can specify how the activity should associate with a task using the <activity> element’s launchMode attribute in manifest file.
launch modes have four different mode can assign to the launchMode attribute:
1. standard
2. singleTop
3. singleTask
4. singleInstance

**Save key-value data**
To save small collection of key-values you should use the SharedPreferences APIs. A SharedPreferences object points to a file containing key-value pairs and provides simple methods to read and write them. Each SharedPreferences file is managed by the framework and can be private or shared. create a new shared preference file or access an existing one by calling one of these methods:

getSharedPreferences()
getPreferences()
