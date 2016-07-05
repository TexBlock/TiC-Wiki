# Frequently Asked Questions

* _I suggested X, why did you close the issue?_

I don't take suggestions. I might consider things in the overall context, but generally suggestions will just be closed to keep the issue tracker clean. Tinkers' Constructs mechanics are designed to work as is. New tools or weapons would either be added if they fulfill a missing demand and nothing more important is to be done.

* _Why did my issue get closed?_

This can have several reasons: Unsupported version, missing information, outdated versions or it was a suggestion and not an issue.
In general issues will be closed after about 2 weeks without activity unless their issue has not been resolved and all needed information is present.
Any 1.7.10 related things will be closed. No more work will be done on the 1.7.10 branch in favor of the reworked version.

* _Why did my pull request get rejected?_

Always talk to me first before working on pull requests. Pull requests will only be accepted if they contribute something meaningful and do not hinder maintainability. Furthermore pull requests must be tested and ensure to not break anything.

* _When will you update X? Why was X removed in 1.8?_

1.8 and onward is a long term project which changes many things about Tinkers' while keeping the core the same. If something is not present in the new version it either was removed by design, or it simply didn't get reimplemented since other things were more important.

* _Armor?_

No.

* _I'm getting a "dangerous alternative prefix 'tconstruct'"_

No reason to worry, this is intended. TCon only registers some of its things (fluid blocks for example) if the required things are present. This allows us to e.g. only have molten copper if there actually is copper in the game, saving a lot of texture space. The only place to do that is during the oredict event. Forge complains because we're adding TCon blocks while it's not TCons turn to add things. So normally it'd be an error, since it means you're registering blocks and the like wrong, but in this case it's intended.