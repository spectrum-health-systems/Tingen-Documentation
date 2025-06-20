<!-- u250306 -->

> Last updated: March 6, 2025

<div align="center">

  ![logo](/.github/image/logo/TingenDevelopmentDocumentation_logo_320x420.png)

  ![TINGEN_VERSION](https://img.shields.io/badge/TINGEN%2025.6-white?style=for-the-badge)

  <h1>Development workflows</h1>

</div>
### CONTENTS

[Overview](#overview)
[In-line comments](#in-line-comments)  
[XML documentation](#xml-documentation)  

# Overview

Longer form stuff is used (e.g., if...then instead of conditionals, no expression statements). For now. Things will be made more efficient over time, but not at the expense of readability.


# In-line comments



# XML documentation



## Example of XML documentation

```xml
<!--
    u241031
    This is the external XML Documentation file for the Tingen.Tingen.asmx.cs class.
-->

<Tingen>

    <!-- Classes -->
    <Type name="Class">

        <!-- Tingen.cs -->
        <Tingen>
            <remarks>
                <para>
                    There should only two methods in this class, both of which are required by Avatar:
                    <list type="bullet">
                        <item><see cref="GetVersion()"/></item>
                        <item><see cref="RunScript(OptionObject2015, string)"/></item>
                    </list>
                </para>
                <para>
                    This class doesn't do much actual work, and should remain fairly static. For the<br/>
                    most part, it just hands information to  <see href="https://github.com/spectrum-health-systems/Outpost31">Outpost31</see>, where the heavy lifting is done.<br/>
                </para>
            </remarks>
            <seealso href="https://github.com/spectrum-health-systems/Tingen-Documentation">Tingen documentation</seealso>
        </Tingen>

    </Type>

    <!-- Properties-->
    <Type name="Property">

        <!-- TingenVersionNumber -->
        <TingenVersionNumber>
            <remarks>
                <para>
                    The syntax for the Tingen version number is "<c>YY.MM&lt;.patch&gt;</c>".<br/>
                    <br/>
                    The version number is pulled from <c>Properties/AssemblyInfo.cs</c>.
                </para>
                <para>
                    This isn't 'Nam, there are rules:
                    <list type="bullet">
                        <item>The <c>MM</c> component is always two digits (ex: July would be "<c>07</c>")</item>
                        <item>If a release doesn't include a patch number, omit the <c>&lt;.patch&gt;</c> component.</item>
                        <item>The version number cannot exceed three components (example: "<c>25.07.1</c>")</item>
                    </list>
                </para>
                <para>
                    For each release of Tingen the following lines:<br/>
                    <code>
                        [assembly: AssemblyVersion("#.#.#.#")]
                        [assembly: AssemblyFileVersion("#.#.#.#")]
                    </code>
                    Need to be modified as so:<br/>
                    <code>
                        [assembly: AssemblyVersion("YY.MM.&lt;.patch&gt;.0")]
                        [assembly: AssemblyFileVersion("YY.MM.&lt;.patch&gt;.0")]
                    </code>
                </para>
            </remarks>
            <example>
                The December 2024 release would look like:<br/>
                <code>
                    [assembly: AssemblyVersion("24.12.0.0")]
                    [assembly: AssemblyFileVersion("24.12.0.0")]
                </code>
            </example>
            <value>
                <list type="bullet">
                    <item>December 2024 release: <c>24.12</c></item>
                    <item>July 2025 release: <c>25.07</c></item>
                    <item>Patched July 2025 release: <c>25.07.1</c></item>
                </list>
            </value>
        </TingenVersionNumber>

        <!-- TingenBuildNumber -->
        <TingenBuildNumber>
            <remarks>
                <para>
                    The syntax for the Tingen build number is "<c>HHMM</c>", and is set at runtime<br/>
                    via <see href="https://spectrum-health-systems.github.io/Tingen-Documentation/API/Outpost31/html/M_Outpost31_Core_Session_TingenSession_BuildStaticVars.htm">TingenSession.BuildStaticVars()</see>.<br/>                    <br/>
                    The build number is used in log files, and to help troubleshoot issues. For the<br/>
                    most part it's not visible to the user.
                </para>
            </remarks>
            <value>If Tingen is built at 10:30AM, the build number would be "<c>1030</c>"</value>
        </TingenBuildNumber>

        <!-- DEPRECIATED 241031
        <TingenConfig>
            <remarks>
                <para>
                    See <b>Outpost31.Core.Configuration.TingenFramework.cs</b> for more information.
                </para>
            </remarks>
        </TingenConfig
        -->

    </Type>

    <!-- Methods -->
    <Type name="Method">

        <!-- GetVersion() -->
        <GetVersion>
            <remarks>
                <para>
                    <b>This method is required by Avatar and should not be modified.</b><br/>
                    <br/>
                    The Tingen <see cref="TingenVersionNumber">Version Number</see> is kinda complex, so it might make sense to<br/>
                    read about it.
                </para>
            </remarks>
        </GetVersion>

        <!-- RunScript() -->
        <RunScript>
            <remarks>
                <para>
                    <b>This method is required by Avatar and should not be modified.</b><br/>
                    <br/>
                    The only difference between the development and stable versions of Tingen is that<br/>
                    the development version uses the<i>"UAT"</i> Avatar System Code, while the stable<br/>
                    version uses the <i>"LIVE"</i> Avatar System Code.<br/>
                    <br/>
                    For the development/UAT version of Tingen, you will see the following line:<br/>
                    <br/>
                    <code>
                        tnSession.AvData.SystemCode = "UAT";
                    </code>
                    And for the stable/LIVE version of Tingen, you will see the following line:<br/>
                    <br/>
                    <code>
                        tnSession.AvData.SystemCode = "LIVE";
                    </code>
                </para>
            </remarks>
        </RunScript>

    </Type>

</Tingen>
```