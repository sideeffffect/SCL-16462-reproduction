# SCL-16462 sbt-tc-logger error when importing project to IntelliJ

Reported at https://youtrack.jetbrains.com/issue/SCL-16462

Having `addSbtPlugin("org.jetbrains.teamcity.plugins" % "sbt-teamcity-logger" % "0.6.0")` in `project/plugins.sbt` results in this error when "using sbt to import project " to IntelliJ:

```
[IJ]sbt:SCL-16462-reproduction> ;reload; set _root_.org.jetbrains.sbt.StructureKeys.sbtStructureOptions in Global := "download resolveClassifiers resolveSbtClassifiers" ;*/*:dumpStructureTo /tmp/sbt-structure.xml; session clear-all ; set ideaPort in Global := 38633
[info] welcome to sbt 1.3.12 (AdoptOpenJDK Java 11.0.6)
[info] loading global plugins from /home/ondra/.sbt/1.0/plugins
[info] loading settings for project scl-16462-reproduction-build from plugins.sbt,idea11.sbt ...
[info] loading project definition from /home/ondra/Projects/SCL-16462-reproduction/project
[info] loading settings for project scl-16462-reproduction from build.sbt ...
[warn] Discarding 1 session setting.  Use 'session save' to persist session settings.
[info] set current project to SCL-16462-reproduction (in build file:/home/ondra/Projects/SCL-16462-reproduction/)
[info] Defining Global / sbtStructureOptions
[info] The new value will be used by Global / ssOptions
[info] Reapplying settings...
[info] set current project to SCL-16462-reproduction (in build file:/home/ondra/Projects/SCL-16462-reproduction/)
[error] stack trace is suppressed; run last ssExtractBuild for the full output
[error] (Global / ssExtractRepository) java.lang.NoSuchMethodError: 'java.lang.String sbt.jetbrains.apiAdapter$.configReportName(sbt.librarymanagement.ConfigurationReport)'
[error] (ssExtractBuild) java.lang.NoSuchMethodError: 'java.lang.String sbt.jetbrains.apiAdapter$.configReportName(sbt.librarymanagement.ConfigurationReport)'
[error] Total time: 2 s, completed Jun 2, 2020, 6:51:30 PM
```
