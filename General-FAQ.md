This FAQ is for general questions related to SlimeKnight's mods. For questions about Tinkers' Construct 3 gameplay, see [[Tinkers' Construct 3 FAQ]]. For questions related to Tinkers' Construct 2, see [[Tinkers' Construct 2 FAQ]].

<table>
  <thead><th>Table of Contents</th></thead>
  <tbody><td>

- [Can you backport Tinkers' Construct to X?](#can-you-backport-tinkers-construct-to-x)
- [What versions of Minecraft do you support?](#what-versions-of-minecraft-do-you-support)
- [What are your plans for 1.17?](#what-are-your-plans-for-117)
- [Do you plan to port the mod to Fabric, Bedrock, or any other platform besides Forge?](#do-you-plan-to-port-the-mod-to-fabric-bedrock-or-any-other-platform-besides-forge)
- [I found a bug, what do I do?](#i-found-a-bug--what-do-i-do)
- [I have a suggestion, can I share it?](#i-have-a-suggestion-can-i-share-it)
- [Will you add support for X to your mod?](#will-you-add-support-for-x-to-your-mod)
- [Why is the wiki wrong?](#why-is-the-wiki-wrong)
- [Where did the config go? Can you make X configurable?](#where-did-the-config-go-can-you-make-x-configurable)
- [Can I put a SlimeKnights mod in my modpack?](#can-i-put-a-slimeknights-mod-in-my-modpack)
- [Is there an official Minecraft server for SlimeKnights mods?](#is-there-an-official-minecraft-server-for-slimeknights-mods)
</td>
</table>

## Can you backport Tinkers' Construct to X?

If Tinkers' Construct skipped a Minecraft version, we have no plans to backport to it, so don't ask. We additionally have no plans to backport features from newer versions of Tinkers' Construct to older versions.

Note for 1.16.4 specifically, we require features from some of the latest Forge builds, which are only on 1.16.5. There is no reason you should still be on 1.16.4 as nearly every mod that works on 1.16.4 also works on 1.16.5.

## What versions of Minecraft do you support?

We currently support just 1.16, both for new features and for bug fixes. We no longer officially support 1.7.10, you are unlikely to get support for that. 1.12 is nearing end of life, so we are unlikely to do another release except perhaps a single additional bugfix release.

If you want help with gameplay, you are free to ask on [our discord](https://discord.gg/njGrvuh), though note we may be limited help with 1.7.10 or 1.12 due to how old those versions are. Additionally, anything older than 1.7.10 and any version between 1.8 and 1.11 are entirely unsupported. Make sure to mention what version you are talking about if asking about any version other than 1.16, as otherwise we will answer for 1.16.

## What are your plans for 1.17?

Until 1.17 Forge is released, we cannot start development. We will continue to work on the 1.16 version of the mod until 1.17 Forge is released, then make an updated plan.

## Do you plan to port the mod to Fabric, Bedrock, or any other platform besides Forge?

In general, none of us see much point in porting the mod to another mod loader, as Forge has served us well enough for years and contains many systems we rely upon. Porting to another platform would require significant work, which none of us have time for.

A few notable platforms:
* Fabric is missing many systems that we rely upon, including models, events, Forge's fluid API, and the capability system. Replacing any of these or migrating to a Fabric version of the API would take significant effort.
* Bedrock does not have a mature enough addon system for us to make something that is properly Tinkers' Construct.

If another author wants to make a Fabric,  Bedrock, or any other platform version of Tinkers' Construct, they are free to reuse code and assets, as those are under the MIT license. We ask that they do not use the name Tinkers' Construct or something too similar to prevent users from getting the authors confused; preferably, ports would be a pun from "Tinkers' Construct" and the modloader name. Additionally, if you manage to make a release, feel free to post about it on [our discord](https://discord.gg/njGrvuh).

## I found a bug, what do I do?

Start by updating your mods to the latest version, as your bug is possibly fixed in a later version.

If the bug still happens in an up to date pack, you can try searching [our issue tracker](/SlimeKnights/TinkersConstruct/issues) to see if its a known issue, then ask on [our discord](https://discord.gg/njGrvuh) for help debugging it.

If you are certain it is a bug in the latest version and it is not already reported it, you can create a new issue on [our issue tracker](/SlimeKnights/TinkersConstruct/issues).

## I have a suggestion, can I share it?

If you want to make a suggestion, the preferred place to do so is [our discord](https://discord.gg/njGrvuh). Note that we expect suggestions to be thought out. Do not tell us to add your random idea, tell us exactly what you want us to add and why you think it belongs in the mod. A good rule of thumb is new features should have 3 distinct uses.

Posting your suggestion does not mean we will accept it, and in many cases we will critique your idea, so do not make suggestions if you are not open to criticism. Remember that you are asking us to take time out of our plans to work on your idea, coming up with a well thought out suggestion will make us a lot more likely to consider it. Also remember that suggestions can be a good source of addons, you could always learn to create mods by trying to create your idea.

## Will you add support for X to your mod?

When it comes to mod support, it typically must meet one of three criteria to be added:

* Support that works for many mods is preferred over support for a specific mod. For example, adding support for melting tin or alloying bronze supports several mods adding those ores and alloys, but support for knightmetal only helps Twilight Forest.
    * One exception is trivial support, for example support that only requires a couple JSON files and has no balance considerations.
* If I personally play a mod, I am a lot more likely to add support than if I never use the mod.
* If someone else pull requests support, it will typically be added as long as it does not require significant maintenance. Please talk to the devs before making the pull request to prevent wasted work.

Note that these criteria are just guidelines, just because something meets these guidelines does not mean it will definitely be added. A notable case of this is support for a mod that we do not feel can be added without breaking the balance of the mod.

## Why is the wiki wrong?

The only official wikis are those on the GitHub repositories. The other wikis are not made by our team. As a result, they may be a mix of multiple versions, or simply inaccurate.

## Where did the config go? Can you make X configurable?

Configs are located either in `.minecraft/config` as before, or in the world folder.

If you do not see an option to configure the feature in either place, note many of our features are also configurable via datapacks, and in the future we plan to continue to move configuration to data packs. For instance, nearly all our recipes can be changed or disabled via datapacks, and removing recipes can also be used to effectively remove features.

## Can I put a SlimeKnights mod in my modpack?

Feel free to use the mod in any modpacks. You are allowed to use it, you do not need to ask for permission. When using the mod, please use the CurseForge or GitHub download and do not rehost the files if possible. If you need to rehost the mod, link the CurseForge or GitHub page in your modpack description. Never use builds from places besides Curse, CurseForge, or Github releases.

Any modpack using Tinkers' Construct is expected to handle user support queries, specifically related to mod interactions. If you discover the issue is in fact caused by Tinkers' Construct and not just modpack config changing recipes, feel free to report it to us.

## Is there an official Minecraft server for SlimeKnights mods?

We have no plans to maintain a public server for our mods. There are many other public servers that exist that contain our mods, or private servers you can join. Note that our discord server should not be used to seek a server to join or to advertise Minecraft servers.