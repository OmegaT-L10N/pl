# Project info
Polish OmegaT Localisation

# How to test ongoing translation

To properly test the UI translation, you *must* use a version of OmegaT that corresponds to the UI file version that you translate. Otherwise, when you ask OmegaT to run with that translated file (which is the procedure we describe here) OmegaT will refuse to run because some UI strings do not correspond to what its UI requires.

## 1. Open your local copy of this project in OmegaT

## 2. Create target documents

## 3. Go to the target file

In OmegaT you can click `Project → Access Project Contents → Target Files`.

You will find `Bundle_pl.properties` there. This is the file that contains every GUI string, and you will need its complete path later on.

## 4. Close OmegaT

## 5. Change OmegaT startup instructions

OmegaT startup script/launcher will have to include `Bundle_pl.properties` as a custom resource bundle.

Regardless of the platform, the following command can be run:
`java -jar /path/to/OmegaT.jar resource-bundle=/path/to/Bundle_pl.properties`.

This command works on any operating system but some operating system specific facilities are also provided:

  * **Linux/BSD/Haiku**

    Edit the `OmegaT` script in the installation folder so that the last line looks like this:<br/>
  `"${JAVA}" -jar -Xmx1024M "${REALOMEGATPATH}/@JAR_SUBST@" resource-bundle=/path/to/Bundle_pl.properties "$@"`<br/>
  (**`/path/to/Bundle_pl.properties`** should be the actual path on your computer, of course).


  * **Windows**

    Go to OmegaT installation folder (usually `C:\Program Files\OmegaT`) and locate a file named `OmegaT.l4J.ini`.

    If file extensions are not shown, the name will look like `OmegaT.l4J`. It's a plain text file.

    Open it in any text editor and at the very end of the file add this line:<br/>
    `-jar OmegaT.jar resource-bundle=C:\Users\User\Folder\Bundle_pl.properties`<br/>
     (**`C:\Users\User\Folder\Bundle_pl.properties`** should be the actual path on your computer, of course).

    Save the file, make sure it's saved as plain text. If your system doesn't let you to change files under Program Files, then copy it somewhere to your Desktop or Documents folder before editing, and then paste the edited copy back into OmegaT installation folder.

* **MacOS**

  OmegaT.app is not available as a developer build. If you translate the latest code, you'll have to use OmegaT_5.5.0_Beta_Without_JRE.zip to test your strings. If you translate the Standard or Latest version of the code, you can use the corresponding OmegaT.app to test your strings.
  
  Right click on OmegaT.app, "Show Package Contents" and open the file:
  `OmegaT.app/Contents/Resources/Configuration.properties`
  
  Copy the resource-bundle parameter at the end of the file:
  `resource-bundle=/path/to/Bundle_pl.properties`
  
  and save.
  
## 6. After modifications start OmegaT with the custom bundle file

  * **Linux/BSD/Haiku**

    Run the modified script

  * **Windows**

    Run OmegaT.ext

  * **MacOS**
  
    If you used OmegaT_5.5.0_Beta_Without_JRE.zip, just run the following command from the Terminal:<br/>
    `java -jar /path/to/OmegaT.jar resource-bundle=/path/to/Bundle_pl.properties`.
  
    If you used OmegaT.app, just reopen OmegaT.app

