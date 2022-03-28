# Project info
Polish OmegaT Localisation

# Access tokens

To be able to use this project with OmegaT, the user who was added to the project with write permissions needs to create an access token. This token will be used instead of the GitHub password when OmegaT promts the user to specify their credentials (GitHub username for the username, and the access token instead of the password). Here's the instruction: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

When following that instruction, in p.8 the user may select all the permissions.

# How to start translating in the project

1. You need to have a GitHub access token.
2. Make sure you have been added to the project with the write permission (this is done by the project manager).
3. Open OmegaT, select **Project** → **Download Team Project**. In the dialog window that will pop up, enter https://github.com/OmegaT-L10N/pl.git for the repository URL. Then select the parent folder where the project's folder will be located, and then type in the folder's name, for instance `PL-L10N` (or any other name). The project's folder will be created in the selected location. Click OK. OmegaT will download the project's data, it may take some time.
4. At some point OmegaT will prompt you for your username and password. Enter your GitHub username and the access token. The prompt may pop up several times.
5. If you have problems with the user's credentials, make sure that your username had been added to the list of the users with write permissions (contact your project manager), and that you entered the access token correctly (no spaces, etc).
6. Step 3 above needs to be done only once. After that you need to open the project from the location where it was saved.
7. In case the project fails to open or synchronize with the server, just redownload it again (step 3 above) into a new location. The old location then can be deleted (but before you delete it, make sure to open the project from the new location and to check that all your previous work had been saved). 

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

