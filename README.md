Sharing dependency versions with TOML catalog

## 1. Usage

Modifiy settings.gradle like this:
```gradle
dependencyResolutionManagement {
    //...

    // use version catalog
    versionCatalogs {
        libs {
            //from(files("../../libs.versions.toml"))
            from("com.github.rwsbillyang:version-catalog:1.0.0")
        }
    }
}
```
More info: [Importing a published catalog](https://docs.gradle.org/current/userguide/platforms.html#sec:importing-published-catalog)


## 2. Using catalog

In build.gradle:
```gradle
dependencies {
    implementation libs.kotlin.stdlib.jdk8
    implementation libs.kotlin.serialization.json
    //...
    implementation libs.rule.runtime
    //implementation project(":ktorKit")
    implementation libs.ktorKit
}
```