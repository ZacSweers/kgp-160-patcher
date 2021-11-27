# kgp-160-patcher

A simple monkeypatch for issues in Kotlin Gradle Plugin 1.6.0.
- [KT-49822](https://youtrack.jetbrains.com/issue/KT-49822) by using [this patch](https://github.com/JetBrains/kotlin/pull/4661).

Note that other patches may be added to this in the future. This namely targets `KT-49822` because it is a significant
performance regression in 1.6.0.

This dependency works as a "monkeypatch", which is to say it relies on a Gradle classpath trick to force use of its 
patched versions of files fixed in the aforementioned patch PRs.

## Usage

Add this dependency to your buildscript classpath _before_ the Kotlin plugin, no other configuration needed. Note that
you should not use this on any version of Kotlin other than 1.6.0.

```kotlin
buildscript {
  dependencies {
    // Must go before the real KGP plugin!
    classpath("dev.zacsweers:kgp-160-patcher:1.0.0")
  }
}
```

Snapshots of the development version are available in [Sonatype's `snapshots` repository][snapshots].

License
-------

    Copyright (C) 2021 Zac Sweers

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

[snapshots]: https://oss.sonatype.org/content/repositories/snapshots/
