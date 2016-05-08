_**The current version is 1.9-2.3.0.jenkins193**_

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
        deobfCompile "slimeknights:TConstruct:1.9-<build>"
    }

The build corresponds to the latest release and its jenkins build. You can find the latest build on the [release](https://github.com/SlimeKnights/TinkersConstruct/releases) page. As the time of writing the build would be "2.3.0.jenkins193"