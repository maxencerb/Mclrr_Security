# Mclrr_Security C#

You can check this package on [NuGet package website](https://www.nuget.org/packages/Mclrr_Security_maxence_raballand).
For **How to Install** and **How to use it**, view root directory README.md file.
For security issues on this particular package [email me here](mailto:maxenceraballand00@gmail.com?subject=Security%20issues%20CS%20Package%201.0.x)

# C# Security Package

## Installation

Several options available :
##
Right-click on **references** in your solution explorer and go to **manage NuGet 	packages**. Then search for "Mclrr_Security_maxence_raballand" and install it.
##
Open the **Package Manager console** and type :

    Install-Package Mclrr_Security_maxence_raballand -Version 1.0.1
##
With **.Net CLI** type the command :

	dotnet add package Mclrr_Security_maxence_raballand --version 1.0.1
##
If your projects supports **PackageReference**, copy this XML node to your project file :

	<PackageReference Include="Mclrr_Security_maxence_raballand" Version="1.0.1" />
##
(**Not Recommended**) if you use **Packet CLI** type in :

	paket add Mclrr_Security_maxence_raballand --version 1.0.1
##
Finally, you can simply download the *.nupkg from this GitHub repository and install it from Visual Studio.
## How to use ?

Install the package to your solution.
Then import the namespace to your class

    using Mclrr_Security;
Then you can use the package :

    string hash = cs_mclrr_security.Encode("bonjour");
    cs_mclrr_security.CheckPassword("bonjour", hash);

