To get TiC into your dev environment you need to add it as a dependency.


## Repository
First you need to add our maven repo to your **build.gradle**:

```gradle
repositories {
    ...
    maven {
        name 'DVS1 Maven FS'
        url 'http://dvs1.progwml6.com/files/maven'
    }
}
```

## Dependency

Then you need to tell it to get Tinkers' Construct from there.

### For 1.12

```gradle
dependencies {
    deobfCompile "slimeknights.mantle:Mantle:1.12-<mantle_build>"
    deobfCompile "slimeknights:TConstruct:1.12.2-<tic_build>"
}
```

### For 1.16

```gradle
dependencies {
    compile fg.deobf("slimeknights.mantle:Mantle:1.16.5-<mantle_build>")
    compile fg.deobf("slimeknights.tconstruct:TConstruct:1.16.5-<tic_build>")
}
```

## Versions

Mantle is needed for Tinkers' Construct. You can find the `<mantle_build>` [here](https://github.com/SlimeKnights/TinkersConstruct/blob/1.16/gradle.properties#L20) in Tinkers' Construct build info.

The `<tic_build>` corresponds to the latest release and its jenkins build. You can find the latest build on the [release](/SlimeKnights/TinkersConstruct/releases) page. As the time of writing the build would be "3.0.3.111"