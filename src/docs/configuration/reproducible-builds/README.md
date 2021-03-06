# Reproducible Builds

Because JAR files contain the timestamp of the included files, it is often difficult to create reproducible builds
from a source commit that results in a hash identical file.
Gradle supports reproducible JAR creation by setting the timestamps of included files to a consistent value.
Shadow includes support for overriding file timestamps starting in version 4.0.0. By default, Shadow will preserve
the file timestamps when creating the Shadow JAR. To set timestamps to a consistent value (1980/1/1 00:00:00),
set the `preserveFileTimestamps` property to `false` on the `ShadowJar` task.

```groovy
// Reset file timestamps
shadowJar {
  preserveFileTimestamps = false
}
```
