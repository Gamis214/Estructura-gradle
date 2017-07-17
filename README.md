# Estructura-gradle
Forma para tener mayor control sobre las dependencias en gradle.

## Gradle.app
```java
ext {
    // Variables to keep libraries consistent
    supportLibrary = "23.2.0"
    googlePlayServicesVersion = '9.4.0'

    // Support Libraries dependencies
    supportDependencies = [
            design           :         "com.android.support:design:${supportLibrary}",
            recyclerView     :         "com.android.support:recyclerview-v7:${supportLibrary}",
            cardView         :         "com.android.support:cardview-v7:${supportLibrary}",
            appCompatV7      :         "com.android.support:appcompat-v7:${supportLibrary}"
    ]

    googlePlayServicesDepends = [
            analytics   : "com.google.android.gms:play-services-analytics:${googlePlayServicesVersion}"
            plus        : "com.google.android.gms:play-services-plus:${googlePlayServicesVersion}"
            location    : "com.google.android.gms:play-services-location:${googlePlayServicesVersion}"
            fitness     : "com.google.android.gms:play-services-fitness:${googlePlayServicesVersion}"
            appindexing : "com.google.android.gms:play-services-appindexing:${googlePlayServicesVersion}"
            auth        : "com.google.android.gms:play-services-auth:${googlePlayServicesVersion}"
            gcm         : "com.google.android.gms:play-services-gcm:${googlePlayServicesVersion}"
    ]

}

dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])

    // compile supportDependencies.appCompatV7
    // compile supportDependencies.recyclerView

    // recommended - includes those above
    compile supportDependencies.design

    // extras
    compile supportDependencies.cardView

    // The correct Volley library
    compile 'com.android.volley:volley:1.0.0'

    compile 'com.squareup.picasso:picasso:2.5.2'
    compile "com.google.code.gson:gson:2.6.2"

    // Google Play Services
    compile googlePlayServicesDepends.location
    // TODO: Add others

}
```
