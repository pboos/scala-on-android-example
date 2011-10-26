Small base project for your scala android applications
============

You can use this immediatly with a text editor and ant from command line.

    android update project -p .
    ant debug
    ant installd
    adb shell am start -a android.intent.action.MAIN -n com.example.android.scala/.MainActivity

Based on https://github.com/gamlerhart/scala-on-droid-example which is based on http://lamp.epfl.ch/~michelou/android/scala-to-android.html

Adjust project name and package name
============

- Inside AndroidManifest.xml replace package with new package name.
- Inside ant.properties replace manifest.package value with new package name.
- Inside src/com/example/android/scala/MainActivity.scala replace package at top line with new package name
- Move src/com/example/android/scala/MainActivity.scala to corresponding folder src/com/new/package/MainActivity.scala (if new package name is com.new.package)

Set up in IntelliJ Idea
============

1. Open IntelliJ Idea
2. Create new Project
3. "Create project from scratch"
4. "New project" dialog
 1. Give it the same name as you specified above in the settings
 2. Choose "Android Module"
 3. Next
5. Choose "Do not create source directory" and Next
6. Android settings
 1. Select the same Android SDK as you have set in project.properties (7 = Android 2.1)
 2. Uncheck "Create default Android application structure"
 3. Finish
7. Copy all files from this repository into the newly created IntelliJ Idea project
8. Open a command line window and run the following command while inside your project: "android update project -p ."
9. In the main window of the IDE click on the "Ant build" tab
 1. Click on add (+)
 2. Choose the build.xml from your project folder
10. File -> Project Structure
 1. In the left choose "Project"
 2. In the dropdown below "Project SDK" choose the correct Android Target (or make new if needed)
 3. In the left choose "Modules"
 4. In the middle choose the top node
 5. On the right click on "src" in the file tree structure
 6. Above click on "Sources" (blue) and it should appear on the left below "Source folders"
11. Run -> Edit configurations
 1. Click on add new configuration (+) and choose "Android Application"
 2. Give it a nice name like "ScalaAndroidProject - Debug"
 3. Module: Choose your project
 4. Check "Choose target device manually"
 5. Uncheck "Make"
 6. Check "Run Ant target"
 7. Click on the "..." next to "Run Ant target"
 8. Choose "debug-install-for-intellij" and click OK
 9. Apply and OK
12. Run it :) (will take a while to compile and run proguard)
