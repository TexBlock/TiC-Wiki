_**The current version is 1.10.2-2.6.3.500**_

To get TiC into your dev environment you need to add it as a dependency.

First you need to add our maven repo to your **build.gradle**:

    repositories {
        ...
        maven {
            name 'DVS1 Maven FS'
            url 'http://dvs1.progwml6.com/files/maven'
        }
    }

Then you need to tell it to get TiC from there:

    dependencies {
        deobfCompile "slimeknights.mantle:Mantle:1.9-<mantle_build>"
        deobfCompile "slimeknights:TConstruct:1.9-<tic_build>"
    }

Mantle is needed for TiC, you can find the mantle_build [here](https://github.com/SlimeKnights/TinkersConstruct/blob/master/build.properties#L6) in TiCs build info.
The tic_build corresponds to the latest release and its jenkins build. You can find the latest build on the [release](https://github.com/SlimeKnights/TinkersConstruct/releases) page. As the time of writing the build would be "2.5.0.jenkins345"