Overview
--------

Included MSBuild targets file uses VSIX manifest version to generate output .vsix package file with version suffix. Additionally, it automatically updates package assembly version and file version with the same VSIX manifest version.

How To Use
----------

* Copy usysware.targets to your VSIX project root folder
* Add usysware.targets to your VSIX project as follows:

```  <Import Project="$(MSBuildProjectDirectory)\usysware.targets" />```
* Make sure usysware.targets is added after Microsoft.VsSDK.targets
* Modify AssemblyInfo and remove AssemblyVersion and AssemblyFileVersion attributes

Troubleshooting
---------------

This targets file is tied to .vsixmanifest file changes. Thus it doesn't pick up on any AssemblyInfo changes. If duplicate attributes are detected then simply initiate a full project re-build.
