# USFM Editor High-Level Design

This document **draft** describes planned software changes to improve the [USFM Editor component](https://github.com/friendsofagape/usfm-editor).

***

# Version 0.10 plans

## ➖ Search 

To support search features in the containing application, the editor should provide highlighting of a given search term. Search terms will be literal (no fuzzy search or wildcards) and will be passed in as a React prop. Instances of the search term will be highlighted in the editor if they are visible, but the editor need not scroll to bring them into view.

A list of highlighted locations (chapter/verse) will be sent to a callback function if the application provides one.

## ➖ New USFM tags

The list of supported formatting tags will be expanded to include the following [poetry](https://ubsicap.github.io/usfm/poetry) and [special text](https://ubsicap.github.io/usfm/characters/index.html#special-text) styles:

1. Poetry line (\q#)
2. Paragraph (\p)
3. Name of Deity (\nd ..\nd\*)
4. Words of Jesus (\wj .. \wj\*)

## ➖ Versions and compatibility

At time of release, the editor should be current with the following:

#### ➖ Slate
The [Slate library](https://www.npmjs.com/package/slate) should be updated to the current version in the Slate v0.50+ (a.k.a. 0.5x) architecture. The architecture is not expected to change from 0.50+ soon, but if and when that happens, [migrating](https://docs.slatejs.org/concepts/xx-migrating) will be a significant task and is beyond the scope of this work.

#### ➖ Browsers

The editor should function under current versions of Chrome, Safari, and Firefox.

## ➖ Web development frameworks

#### Next.js
The editor should function in a Next.js project with Tailwind CSS styling.

#### Tailwind CSS
The components should allow CSS styling with Tailwind CSS classes.

#### Tailwind UI
The components should allow use of Tailwind UI widgets.

