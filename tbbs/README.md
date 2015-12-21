SI4T Solution
=============

The SI4T.Templating project contains a post-build event to upload the
TBB to the SDL Tridion Content Manager. The event is disabled by
default. To enable it just go through the following steps.

Update the post build event
---------------------------
1. Open the SI4T Templating project. Go to the post-build events and
find the post build event.
2. In the post build event remove the prepending `REM` which disables
the event.
3. In the post build event find the `/folder` parameter and replace the
folder TCM URI with the URI of the Tridion folder containing the SI4T 
TBB named `SI4T.Templating`.

Make a _tools folder with some resources for the post build event
-----------------------------------------------------------------
1. In the root of the SI4T project source create a `_tools` folder
2. Copy `%TRIDION_HOME%\bin\client\TcmUploadAssembly.exe` to the _tools
folder
3. Open a command line in _tools and run
`TcmUploadAssembly.exe config.xml` and fill in the server details the 
tool asks for. This step will create `_tools\config.xml`