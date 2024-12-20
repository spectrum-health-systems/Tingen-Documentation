<!-- u241205 -->

<div align="center">

  ![logo](../../.github/Images/Logos/TingenDocumentation-232x308.png)

  ![BASEDON_VERSION](https://img.shields.io/badge/BASED%20ON%20Tingen%2024.12-white?style=for-the-badge)

  <h1>
    Tingen development processes
  </h1>

</div>

# Monthly development

When development starts for a new month:

## 1. Archive current Tingen_development branch

Create a `YY.DD.##-development+final` branch of Tingen_development using the current development branch.

## 2. Archive current Outpost31 development branch

Create a `YY.DD.##-development+final` branch of Outpost31 using the current development branch.

## 3. Archive the documentation

Create a `YY.DD.##-development+final` branch of Tingen-Documentation using the current development branch.

# 4. Update the AssemblyInfo.cs files

Update the following AssemblyInfo.cs files with the current version number:

- Tingen_development/Properties/AssemblyInfo.cs
- Outpost31/Properties/AssemblyInfo.cs

## 5. Update file headers

Update the file headers for both `Tingen.Tingen.asmx.cs` and `Outpost31.WelcomeToOutpost31.cs` with the current the datestamp information:

For example:

```text
// ================================================================ 241031 =====
```

## 6 Update the tnBuild value

Update `tnBuild` value in `Core.Session.TingenSession.BuildStaticVars()` to the current `YYMMDD.HHMM` value.

For example:

```csharp
return new Dictionary<string, string>
{
    { "tnBuild",              "241205.0944" },
    { "avSystemCode",         "UAT" },
    { "tnDataRoot",           @"C:\TingenData" },
    { "tnConfigFileName",     "Tingen.config" },
    { "ntstSecurityFileName", "NtstSecurity.config" }
};
```

# 7. Update the documentation

Search for the following string in the documentation...

```
![BASEDON_VERSION](https://img.shields.io/badge/BASED%20ON%20Tingen%20YY.MM-white?style=for-the-badge)
```

...where `YY.MM` is the Year.Month value for the current documentation, and keeping in mind that the "***%20***" in "**%20***MM*" is a space!

Replace the value of `YY.MM` with the current Year.Month.

For example:
```
![BASEDON_VERSION](https://img.shields.io/badge/BASED%20ON%20Tingen%2024.12-white?style=for-the-badge)
```

# 8. Update the AutoHotKey script

# 9. Update the Sandcastle help file versions

Update the Sandcastle "Help file version" in the following Sandcastle profiles:

- Tingen
- Outpost31

***

Update README.md files