# Changelog

(_Note: This changelog will only cover **meaningful** commits and changes_)

## [Latest](https://github.com/That-TransGirl/Color-Bot/commit/master) - Role Menu is done (finally).

-   **Finally** finished the role menu so it is fully functioning. All that I have really done \
    was move the 1,000+ lines to a seperate file ([`roleMenu.ts`](./handlers/roleMenu.ts)), with a few major (but mostly minor) changes and additions.
    -   As part of this rewrite, I used a temporary local data storage system (`tempData.json`, which would be under [`localData`](./localData)) \
        to store important information between interactions without using the `customId` property, \
        allowing for a lot more freedom with how I choose to use it in the future.
-   Renamed this to [`README.md`](./README.md) so it appears in the main page of the repository.
-   Took the bot out of Dev Mode™ - Currently working on a system so that Dev Mode™ is toggle-able, \
    didn't make much progress in that regard.
    -   _Ignore [`botConfig.ts`](./classes/botConfig.ts) for now._
-   A lot of code cleanup - which consisted of me hating on `if` statements and only using \
    `statement ? true : false` statements cause why not.
-   Added `checkRolesAgainstUser` and `checkRolesToReplace` methods because declattering is important (learned that the hard way).
-   Added more [component builders](./helpers/componentBuilders.ts) because... do I need to repeat myself?
-   Renamed `constants.ts` to [`globals.ts`](./helpers/globals.ts) (both the file and class name) and moved \
    all classes (for example, [`RoleConstants`](./classes/RoleConstants.ts)) to their respective file under the folder [classes](./classes).
-   Updated [`.gitignore`](./.gitignore) to include the _folder_ [`localData`](./localData) but exclude anything inside.
-   I probably missed something (like I always do) 🤷‍♀️

## [82e3161](https://github.com/That-TransGirl/Color-Bot/commit/82e3161) - This changelog (and other stuff).

-   Created this changelog
-   **Removed Role Menu Handling From `interactionCreate.ts`** - which means that, for now, the menu is not fully implemented yet. \
    Sure, some might question why the _fuck_ would I do that but the answer is simple:
    _The current code was so bad that I'd rather rewrite it all_.
-   Added `buildCustomId` function to [`utils.ts`](./helpers/utils.ts)
-   Added ground work for a change-able Role Menu config (see the class [`RoleConstants`](./helpers/constants.ts)):
    -   The class supports removing and updating roles, as well as updating local role data with the server's role data.
    -   The function `verifyStoredRoles` now runs after the client is ready and it updates the local data with the data from the server.
-   Started reworking the role menu handling - current plan is to seperate stages into different functions.
-   Added [`roleUpdate.ts`](./events/roleUpdate.ts) & [`roleDelete.ts`](./events/roleDelete.ts) to allow the `RoleConstants` class to stay up to date with changes to the roles registered under it.
-   Moved `mainAction`, `secondaryAction`, etc. to one object (called `customIdObj`). I don't know if I'm going to keep it this way but that's how it is for now.
-   General rewrites and cleanups.

## [a4380f5](https://github.com/That-TransGirl/Color-Bot/commit/a4380f5) - The start of a painful rewrite.

-   Updated [`.gitignore`](./.gitignore).
-   Added settings to [`.prettierrc`](./.prettierrc) to support uniform formatting.
-   Moved everything out of `src` to the top level to fix an issue with relative pathing.
-   (**WIP**) Started rewriting and seperating the code in [`interactionCreate.ts`](./events/interactionCreate.ts) to declatter the massive file (1,600+ lines o_0).
-   Created new builders to minimize repeated code writing
-   Added [`constants.ts`](./helpers/constants.ts) to further declatter the code.
-   Seperated the getting and loading of the event & command files into functions.
-   Added `interactionTypeToString` & `uppercaseWord` functions to [`utils.ts`](./helpers/utils.ts).
-   Other misc. changes that I can't remember 🤷‍♀️.