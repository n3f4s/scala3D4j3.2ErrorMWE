# scala3D4j3.2ErrorMWE
MWE for a compilation error with scala 3 and Di4j 3.2

When using code for slash command from `Discord4J` in `scala 3` code, the compiler emit a `Bad symbolic reference` error:

```
[error] Bad symbolic reference. A signature
[error] refers to Value/T in package org.immutables.value which is not available.
[error] It may be completely missing from the current classpath, or the version on
[error] the classpath might be incompatible with the version used when compiling the signature.
[warn] Caught: java.lang.AssertionError: assertion failed: failure to resolve inner class:
[warn] externalName = org.immutables.value.Value$Immutable,
[warn] outerName = org.immutables.value.Value,
[warn] innerName = Immutable
[warn] owner.fullName = org.immutables.value.Value
[warn] while parsing ~/.cache/coursier/v1/https/oss.sonatype.org/content/repositories/snapshots/com/discord4j/discord4j-core/3.2.0-SNAPSHOT/discord4j-core-3.2.0-20210908.030540-190.jar(discord4j/core/spec/InteractionApplicationCommandCallbackReplyMonoGenerator.class) while parsing annotations in ~/.cache/coursier/v1/https/oss.sonatype.org/content/repositories/snapshots/com/discord4j/discord4j-core/3.2.0-SNAPSHOT/discord4j-core-3.2.0-20210908.030540-190.jar(discord4j/core/spec/InteractionApplicationCommandCallbackReplyMonoGenerator.class)
[warn] 5 warnings found
```

Removing the `scalaVersion := scala3Version,` line from `build.sbt` fix the issue but use `Scala 2` compiler.
