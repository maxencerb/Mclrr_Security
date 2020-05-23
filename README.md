# Mclrr Security
Mclrr is a package written by Maxence Raballand. This is free to use if you're using it on your own systems. It is now avalaible in **C#**. It is under a MIT license. Please review it.
Feel free to checkout [my website](https://maxenceraballand.com) to learn more about me.
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
