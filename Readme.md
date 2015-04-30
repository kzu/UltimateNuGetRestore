This solution shows several real-world scenarios:

- Solution inside a subfolder of the repository root
- Solution inside a nested folder inside the above solution
- Solution inside a nested folder alognside the first folder
  (i.e. an external submodule)

The first goal is to keep all nuget packages referenced and 
downloaded to a single folder in the repository root. 

The second goal is to automatically restore all packages 
when building from the command line, either via msbuild or 
xbuild (the IDEs do that automatically today). This second 
goal is achieved by a very simple targets file (nuget.targets) 
that is combined with the Before.[solution file].targets 
alongside each solution, which works across xbuild and msbuild.

You can read more about the second goal and how it works at [Ultimate Cross Platform NuGet Restore](http://www.cazzulino.com/ultimate-cross-platform-nuget-restore.html).

You can get it as a nuget by running: 

    nuget install build -excludeversion


