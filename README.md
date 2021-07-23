# USFM Editor High-Level Design

This document **draft** describes planned software changes to improve the [USFM Editor component](https://github.com/friendsofagape/usfm-editor).

***

# Version 0.10 plans

## ➖ Partial USFM (a.k.a. "chunk" or "block" or "snippet" mode)

The editor should be able to display partial USFM when in read-only mode. This will allow the application to omit headers or chapter markers when displaying snippets.

## ➖ Search 

To support search features in the containing application, the editor should provide highlighting of a given search term. Search terms will be literal (no fuzzy search or wildcards) and will be passed in as a React prop. Instances of the search term will be highlighted in the editor if they are visible, but the editor need not scroll to bring them into view.

A list of highlighted locations (chapter/verse) will be sent to a callback function if the application provides one.

## ➖ New USFM tags

The list of supported formatting tags will be expanded to include the following [poetry](https://ubsicap.github.io/usfm/poetry) and [special text](https://ubsicap.github.io/usfm/characters/index.html#special-text) styles:

1. Poetry line (\q#)
2. Paragraph (\p)
3. Name of Deity (\nd ..\nd\*)
4. Words of Jesus (\wj .. \wj\*)
5. Selah (\qs ... \qs\*)
6. Inscriptions (\pc and/or \qc)

## ➖ Versions and compatibility

At time of release, the editor should be current with the following:

#### ➖ Slate
The [Slate library](https://www.npmjs.com/package/slate) should be updated to the current version in the Slate v0.50+ (a.k.a. 0.5x) architecture. The architecture is not expected to change from 0.50+ soon, but if and when that happens, [migrating](https://docs.slatejs.org/concepts/xx-migrating) will be a significant task and is beyond the scope of this work.

#### ➖ Browsers

The editor should function under current versions of Chrome, Safari, and Firefox.

## ➖ Web development frameworks

#### Next.js
The editor should function in a Next.js project.

#### Tailwind CSS
The components should allow CSS styling with Tailwind CSS classes.

#### Tailwind's Headless UI
The components should allow use of Tailwind's Headless UI components.

## Footnote editor

A footnote editor RCL. This will require the "Partial USFM" and "Inline components" tasks (also in this document). It will provide appropriate toolbar, tags, and rendering.
TODO: flesh this task out further.

## Inline components

The application may provide arbitrary components to be inserted at any verse.

For example, if a translator's comment has been left for a verse, the application may choose to provide an icon indicator that will fire an action for the application to display the comment. The editor will render this component inline at the end (beginning?) of the verse text.

## Interlinear components

As an alternative to Inline Components, investigate whether interlinear (between the lines of text) components are feasible, and advise. Potential uses are comment snippets, footnotes, and cross-references.

