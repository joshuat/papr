# Changelog

## 1.0.0 (2024-01-20)


### ⚠ BREAKING CHANGES

* `node` minimum version is now v16.20.1
* Node.js v14 is not supported.
* The return type of `bulkWrite` now includes also `void`
* Nested properties after 6 levels of nesting are no longer type checked.
* Papr is using new internal stricter types for query filters and update
* `Filter` and `UpdateFilter` types are now using the strict counterpart types from mongodb v5.
* Schemas no longer have a default `__v` property defined. Users who have migrated from Mongoose or are otherwise taking advantage of this property will have to manually add it to their schema definitions.
* This changes the produced JSON schema for required `oneOf` types to correctly include it in the resulting `required` properties array.
* Changes the return type for `schema` and the generic arguments for `model` and various utils
* The hook parameters have been merged into a single object parameter.
* Arrays will no longer default to type (T | undefined)[]
* Removed undocumented support for a custom model generic type in the `model()` function.
* `bulkWrite` operations types updated to handle defaults for attributes.
* `schema()` generic types have changed.

### Features

* `decimal` type ([#326](https://github.com/joshuat/papr/issues/326)) ([13443bc](https://github.com/joshuat/papr/commit/13443bc196c369720d5605f26fb513e9b8e27e2e))
* `null` type ([#337](https://github.com/joshuat/papr/issues/337)) ([e78f1ca](https://github.com/joshuat/papr/commit/e78f1ca9e4aeaa61a176201ef38ba50bf98a1dc4))
* `oneOf` type ([#275](https://github.com/joshuat/papr/issues/275)) ([2d55250](https://github.com/joshuat/papr/commit/2d55250a99f0629f051fe7d768080046d30d5866))
* `tuple` type ([#284](https://github.com/joshuat/papr/issues/284)) ([0531447](https://github.com/joshuat/papr/commit/0531447af494e60ff0ecfeeffc29c169a359c7b6))
* `unknown` type ([#276](https://github.com/joshuat/papr/issues/276)) ([716712a](https://github.com/joshuat/papr/commit/716712a0241761a8b3008ef52f090aa9532e9b9f))
* Add `findCursor` model method ([#454](https://github.com/joshuat/papr/issues/454)) ([3b65525](https://github.com/joshuat/papr/commit/3b6552593403d4fd4f2c382f53021e4b5666406e))
* Add `Model.exists(filter)` query helper ([47ee728](https://github.com/joshuat/papr/commit/47ee728c0d8ce36943aa211e98d81f00aa2fe62c))
* Add mongodb v5 support with strict filter types ([#422](https://github.com/joshuat/papr/issues/422)) ([547a794](https://github.com/joshuat/papr/commit/547a794dc4256e5a97f3bf13a08b4de659fd411d))
* Add timestamp option to set property names ([115c805](https://github.com/joshuat/papr/commit/115c805d902176aec11c4b3cb8af2d09fe27b913))
* Adopt filter types from mongodb and enhance strictness ([#430](https://github.com/joshuat/papr/issues/430)) ([b54ef0b](https://github.com/joshuat/papr/commit/b54ef0b76ee899d1a6d7e0fae9b90e3063775eaf))
* Allow const enums ([#497](https://github.com/joshuat/papr/issues/497)) ([194e505](https://github.com/joshuat/papr/commit/194e505ae0837fc53cc746330ca003f7a106e8a0))
* Allow user definition of `_id` property type ([#311](https://github.com/joshuat/papr/issues/311)) ([056928e](https://github.com/joshuat/papr/commit/056928e955a34aa466d547dd99d1cb75f59ece9d))
* Better `bulkWrite` types for insert operations ([#211](https://github.com/joshuat/papr/issues/211)) ([8ae6182](https://github.com/joshuat/papr/commit/8ae6182d871fc6daec346884b3ed5bb2333d4964))
* Make array members non-optional by default ([#231](https://github.com/joshuat/papr/issues/231)) ([2c52719](https://github.com/joshuat/papr/commit/2c52719f0025c85760c3d5a82660cdb5cf2c8c5b))
* Send result to the after hook parameters ([#242](https://github.com/joshuat/papr/issues/242)) ([cef1536](https://github.com/joshuat/papr/commit/cef1536ba7eff4c2e6b52a2106eb88b9bff2149f))
* Support `constant` type ([#312](https://github.com/joshuat/papr/issues/312)) ([e676703](https://github.com/joshuat/papr/commit/e67670399dad5dfbbe7b30ea688f5c7912ba7a8b))
* Support dynamic default values ([#527](https://github.com/joshuat/papr/issues/527)) ([34d0434](https://github.com/joshuat/papr/commit/34d043423f79a541b622053e10793dc22313cb01))
* Support excluding fields in ProjectionType ([#360](https://github.com/joshuat/papr/issues/360)) ([086d8f1](https://github.com/joshuat/papr/commit/086d8f160d7ec6fdd78e439f3d5b8d6d94f5ace2))
* Support for mongodb v4.8.1 ([#262](https://github.com/joshuat/papr/issues/262)) ([0b86f01](https://github.com/joshuat/papr/commit/0b86f01954cd6a9370ae7fd3924b6e862cf94473))
* Support options for upsert model method ([#711](https://github.com/joshuat/papr/issues/711)) ([b92a507](https://github.com/joshuat/papr/commit/b92a507277c734423feb5f3abd163eb1ccafc47a))
* Support TypeScript moduleResolution nodenext option ([#460](https://github.com/joshuat/papr/issues/460)) ([14791f6](https://github.com/joshuat/papr/commit/14791f671e652db1814c618afc67face19271c08))
* Type check nested objects in generic objects ([#439](https://github.com/joshuat/papr/issues/439)) ([3a142f3](https://github.com/joshuat/papr/commit/3a142f333d95c7a4145db2e4deff022655862e6e))
* Upgrade mongodb to v6.0.0 ([#569](https://github.com/joshuat/papr/issues/569)) ([a95bfb4](https://github.com/joshuat/papr/commit/a95bfb45c11d6bcaf48d5ed51f0f7299814776a2))


### Bug Fixes

* Allow explicit optional types on schemas ([#207](https://github.com/joshuat/papr/issues/207)) ([716dbb4](https://github.com/joshuat/papr/commit/716dbb404092162aa438eeb05dfa2afa393b735f))
* Correct `oneOf` required option ([a24054f](https://github.com/joshuat/papr/commit/a24054fbfaeb0f1ad58470080db6cc77bae23533))
* Correct TimestampSchema ternary in DocumentForInsert ([#277](https://github.com/joshuat/papr/issues/277)) ([7e8d750](https://github.com/joshuat/papr/commit/7e8d7504aeee51e6ad0c27a9df7a8597fdb63f74))
* Customisable Hook context type ([#258](https://github.com/joshuat/papr/issues/258)) ([26d4628](https://github.com/joshuat/papr/commit/26d4628ef1fef0ca9266d4a4c6d21c3fc53313e7))
* Improve defaults type at schema declaration ([#178](https://github.com/joshuat/papr/issues/178)) ([efa5d92](https://github.com/joshuat/papr/commit/efa5d92b1ed47a4145b5bac7e27c1793ca029954))
* Update sed command for macOS ([#234](https://github.com/joshuat/papr/issues/234)) ([0b6c476](https://github.com/joshuat/papr/commit/0b6c47620e670ac00ae42681b7f9f74c478e8112))
* Upgrade mongodb to v4.11.0 ([#343](https://github.com/joshuat/papr/issues/343)) ([f7db8b7](https://github.com/joshuat/papr/commit/f7db8b70b1fcf294890319d374151dbb67e2af44))
* Upgrade mongodb to v4.9.0 ([#292](https://github.com/joshuat/papr/issues/292)) ([64de742](https://github.com/joshuat/papr/commit/64de742dfbc07e16611de4e3f05128fd92c6ff31))
* Upgrade mongodb to v4.9.1 ([#304](https://github.com/joshuat/papr/issues/304)) ([cc2e975](https://github.com/joshuat/papr/commit/cc2e97562bb9bd502b1851debdc58727f7a1d398))
* Upgrade typescript to v4.8.2 ([#300](https://github.com/joshuat/papr/issues/300)) ([fd3ee59](https://github.com/joshuat/papr/commit/fd3ee591b281adcabc8d5207244283063592b19f))
* Use Record for objectGeneric type ([#274](https://github.com/joshuat/papr/issues/274)) ([59f3664](https://github.com/joshuat/papr/commit/59f3664389a4ead84cae185ab4526a3f04f580da))
* Util getIds accepts readonly structures ([#381](https://github.com/joshuat/papr/issues/381)) ([940d519](https://github.com/joshuat/papr/commit/940d519c9b05af42efa1b3a8c7373753abc3bc47))


### Performance Improvements

* Improve update filter types check times ([#440](https://github.com/joshuat/papr/issues/440)) ([15d1ba9](https://github.com/joshuat/papr/commit/15d1ba903d3d7ecba3522d5b8908014ad2b5355d))


### Code Refactoring

* Perform no-op on `bulkWrite` when no operations provided ([#455](https://github.com/joshuat/papr/issues/455)) ([d56a0f6](https://github.com/joshuat/papr/commit/d56a0f67e00de30e13b1be814a5f33bb455f0004))
* Remove custom model type support ([#219](https://github.com/joshuat/papr/issues/219)) ([8675ffa](https://github.com/joshuat/papr/commit/8675ffa0cfcf247c85f41ed2254b497ae3cd1ff1))
* Remove default schema `__v` version property ([86bca4f](https://github.com/joshuat/papr/commit/86bca4f4b45fa06cc3be9536bd0f0b51e27228e0))
* Remove node.js v14 support ([#464](https://github.com/joshuat/papr/issues/464)) ([935b331](https://github.com/joshuat/papr/commit/935b33162aa41356779131182767630f8776b1c4))
