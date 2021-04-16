# Project info
Polish OmegaT Localisation

# How to test ongoing translation
## 1. Open your local copy of this project in OmegaT.

## 2. Create target documents

## 3. Go to the target file (`Project → Access Project Contents → Target Files`).

You will find `Bundle_pl.properties` there. This is the file that contains every GUI string, and you will need its complete path later on.

## 4. Close OmegaT.

## 5. Change OmegaT startup instructions

OmegaT startup script/launcher will have to include `Bundle_pl.properties` as a custom resource bundle.</br>
In essence it boils down to running this command:
`java -jar OmegaT resource-bundle=/path/to/Bundle_pl.properties`.</br>
This is how it's done on different operating systems:

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

  To be written

## 6. After modifications start OmegaT with the custom bunlde file

  * **Linux/BSD/Haiku**

    Run the modified script

  * **Windows**

    Run OmegaT.ext

  * **MacOS**

    To be written

