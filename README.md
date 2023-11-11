##

This fork exists because development upstream seems to have slowed down but there are some fixes in the PR's and some forks that I'd like to pull in, build and publish.  
Most notably and as the name of the fork implies, Project RimWorldFactory compatibility, made by [rli-efrantz](https://github.com/rli-efrantz)

# Building

To build, just build the .sln in VS 2022. A distribution zip will be created in a `dist` directory at the root of the repo.   

Before a release, update `AssemblyInfo.cs` in the project directory to increase the build number (3rd version field) of `AssemblyVersion` and `AssemblyFileVersion` by one. If the a Steam installation of RimWorld is detected, the major & minor version fields of `AssemblyInfo.cs` and the `targetVersion` field of `mod-structure\About\About.xml` will be updated automatically. If a Steam installation is not detected, these must be updated manually.

If RimWorld is installed in a custom location, like a Steam-Library on another drive, a `CustomPath.txt` file can be created at the root of the repository with the path to RimWorld installation inside, i.e. `E:\SteamLibrary\steamapps\common\RimWorld`

HugsLib dependencies are fetched via NuGet and the RimWorld and Unity assemblies will be copied out of the game's Steam directory if available. The output will automatically be copied into the game's mod directory if a Steam installation of the game is detected or set.

If you are not using Steam, create a `ThirdParty` directory at the root of the repository and copy `Assembly-CSharp.dll` and any `dll` file starting with `Unity` from the games `RimWorld\RimWorldWin64_Data\Managed` directory into there.