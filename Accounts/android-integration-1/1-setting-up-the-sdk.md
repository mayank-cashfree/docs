---
title: "1. Setting up the SDK"
slug: "1-setting-up-the-sdk"
excerpt: ""
hidden: true
createdAt: "Fri Nov 04 2022 07:36:35 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 05 2023 13:45:29 GMT+0000 (Coordinated Universal Time)"
---
# Gradle Changes

### Add Cashfree maven repository

Add to your module's build.gradle file if your gradle version is less than 6.+ or below.

```groovy
repositories 
{
    maven 
    { 
      url 'https://maven.cashfree.com/development'
    }
}
```

If you are using Gradle version 7.+ in your project then add the maven repository in your settings.gradle file

```groovy
dependencyResolutionManagement {
   repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
   repositories {
       google()
       mavenCentral()
       maven{
           url "https://maven.cashfree.com/development/"
       }
   }
}
```

Add below line under dependencies on the app level build.gradle

```groovy
dependencies {
     implementation("com.cashfree.prepaidcards:android-sdk:1.0.1")
}
```

Library class will be ready to use after adding on gradle.
