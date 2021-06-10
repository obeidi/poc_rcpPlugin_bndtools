# poc_rcpPlugin_bndtools
Die Umsetzung ist an den GitHub Repo : https://github.com/peterkir/example.bnd.rcp.git angelehnt.

## How to run:
 1. open the Shell and go to the Folder you want to clone the Repo.
 2. git clone https://github.com/obeidi/poc_rcpPlugin_bndtools.git
 3. open Eclipse and import the cloned Repo as "Existing Projects into Workspace" 
 4. go to the master-Branch.
 5. open the Project an go to rcpPlugin2 and open the .bndrun File.  
    For mac: app.ui_macosx.cocoa.x86-64.bndrun and  
	for windows: app.ui_win32.win32.x86-64.bndrun
 6. start the .bndrun with the play-Button. 
 
 ## to implement bndtools in a Eclipse RCP Application 
 1. install bndtools above Eclipse Marketplace.
 2. create a Folder and call it "root", this is you root-folder.
 3. create in root a simple Java-Project.
 4. create a BND-Workspace in the root:
	File->new->other->Bndtools->"Bnd OSGI Workspace" -> click next.  
	navigate to your RCP-Workarea.  
	choose the workspace 5.3 (we use it hier)  
	create your BND-Workspace
    ![bndtools-Workspace](pic/workspace-eclipse.png "bndtools-Workspace")
 5. create a Folder "rcpApp" next to cnf. 
 6. create in the Folder "rcpApp" an Eclipse RCP with the same Name!!!! (https://www.vogella.com/tutorials/EclipseRCP/article.html)
    ![rcpApp-init](pic/rcpApp-init.png "rcpApp-init") 
 7. add a "app" and "workspace" Folder in the RCP Application in the Folder "rcpApp".
 8. add BND-Nature to the RCP-Project that you build in "rcpApp"
    ![rcp-bnd-nature](pic/rcp-bnd-nature.png "rcp-bnd-nature") 
    add the follow code in you bnd.bnd:
    ![bnd-BND](pic/bnd-bnd.png "bnd-BND")
	[bnd.bn](./rcpPlugin2/bnd.bnd "bnd.bnd") 
 9. go in the Shell to the root and build with gradle, "gradle build".
 10. create a BNDtools "Run Descriptor File (.bndrun)".  
	 select the Folder rcpApp.  
     File->new->other->Bndtools->"Run Descriptor File (.bndrun)" click next.  
	 select the Empty one  
	 select rcpApp and give the File a Name.
 11. copy the follow code in Run Descriptor: 
    [app.ui_macosx.cocoa.x86-64.bndrun](./rcpPlugin2/app.ui_macosx.cocoa.x86-64.bndrun "app.ui_macosx.cocoa.x86-64.bndrun") 