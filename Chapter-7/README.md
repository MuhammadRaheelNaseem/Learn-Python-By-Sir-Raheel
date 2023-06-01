<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Python_Lecture_Chapter_07_Functions</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>




<style type="text/css">
    pre { line-height: 125%; }
td.linenos .normal { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
span.linenos { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
td.linenos .special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>



<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/* tiny scrollbar */

.jp-scrollbar-tiny {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
  scrollbar-width: thin;
}

/*
 * Webkit scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-corner {
  background: var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-thumb {
  background: rgb(var(--jp-scrollbar-thumb-color));
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-right: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-bottom: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar */

[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-corner,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-corner {
  background-color: transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-thumb,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid transparent;
  border-right: var(--jp-scrollbar-endpad) solid transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid transparent;
  border-bottom: var(--jp-scrollbar-endpad) solid transparent;
}

/* tiny scrollbar */

.jp-scrollbar-tiny::-webkit-scrollbar,
.jp-scrollbar-tiny::-webkit-scrollbar-corner {
  background-color: transparent;
  height: 4px;
  width: 4px;
}

.jp-scrollbar-tiny::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:horizontal {
  border-left: 0px solid transparent;
  border-right: 0px solid transparent;
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:vertical {
  border-top: 0px solid transparent;
  border-bottom: 0px solid transparent;
}

/*
 * Phosphor
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Widget, /* </DEPRECATED> */
.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  cursor: default;
}


/* <DEPRECATED> */ .p-Widget.p-mod-hidden, /* </DEPRECATED> */
.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-CommandPalette, /* </DEPRECATED> */
.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-CommandPalette-search, /* </DEPRECATED> */
.lm-CommandPalette-search {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-content, /* </DEPRECATED> */
.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-CommandPalette-header, /* </DEPRECATED> */
.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}


/* <DEPRECATED> */ .p-CommandPalette-item, /* </DEPRECATED> */
.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}


/* <DEPRECATED> */ .p-CommandPalette-itemIcon, /* </DEPRECATED> */
.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemContent, /* </DEPRECATED> */
.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}


/* <DEPRECATED> */ .p-CommandPalette-itemShortcut, /* </DEPRECATED> */
.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemLabel, /* </DEPRECATED> */
.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.lm-close-icon {
	border:1px solid transparent;
  background-color: transparent;
  position: absolute;
	z-index:1;
	right:3%;
	top: 0;
	bottom: 0;
	margin: auto;
	padding: 7px 0;
	display: none;
	vertical-align: middle;
  outline: 0;
  cursor: pointer;
}
.lm-close-icon:after {
	content: "X";
	display: block;
	width: 15px;
	height: 15px;
	text-align: center;
	color:#000;
	font-weight: normal;
	font-size: 12px;
	cursor: pointer;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-DockPanel, /* </DEPRECATED> */
.lm-DockPanel {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-widget, /* </DEPRECATED> */
.lm-DockPanel-widget {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-tabBar, /* </DEPRECATED> */
.lm-DockPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-DockPanel-handle, /* </DEPRECATED> */
.lm-DockPanel-handle {
  z-index: 2;
}


/* <DEPRECATED> */ .p-DockPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-DockPanel-handle:after, /* </DEPRECATED> */
.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}


/* <DEPRECATED> */ .p-DockPanel-overlay, /* </DEPRECATED> */
.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}


/* <DEPRECATED> */ .p-DockPanel-overlay.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Menu, /* </DEPRECATED> */
.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-Menu-content, /* </DEPRECATED> */
.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-Menu-item, /* </DEPRECATED> */
.lm-Menu-item {
  display: table-row;
}


/* <DEPRECATED> */
.p-Menu-item.p-mod-hidden,
.p-Menu-item.p-mod-collapsed,
/* </DEPRECATED> */
.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}


/* <DEPRECATED> */
.p-Menu-itemIcon,
.p-Menu-itemSubmenuIcon,
/* </DEPRECATED> */
.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}


/* <DEPRECATED> */ .p-Menu-itemLabel, /* </DEPRECATED> */
.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}


/* <DEPRECATED> */ .p-Menu-itemShortcut, /* </DEPRECATED> */
.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-MenuBar, /* </DEPRECATED> */
.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-MenuBar-content, /* </DEPRECATED> */
.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}


/* <DEPRECATED> */ .p--MenuBar-item, /* </DEPRECATED> */
.lm-MenuBar-item {
  box-sizing: border-box;
}


/* <DEPRECATED> */
.p-MenuBar-itemIcon,
.p-MenuBar-itemLabel,
/* </DEPRECATED> */
.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-ScrollBar, /* </DEPRECATED> */
.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-ScrollBar-button, /* </DEPRECATED> */
.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-track, /* </DEPRECATED> */
.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-thumb, /* </DEPRECATED> */
.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-SplitPanel-child, /* </DEPRECATED> */
.lm-SplitPanel-child {
  z-index: 0;
}


/* <DEPRECATED> */ .p-SplitPanel-handle, /* </DEPRECATED> */
.lm-SplitPanel-handle {
  z-index: 1;
}


/* <DEPRECATED> */ .p-SplitPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-SplitPanel-handle:after, /* </DEPRECATED> */
.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabBar, /* </DEPRECATED> */
.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='horizontal'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
  align-items: flex-end;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='vertical'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
  align-items: flex-end;
}


/* <DEPRECATED> */ .p-TabBar-content, /* </DEPRECATED> */
.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='horizontal'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='vertical'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
}


/* <DEPRECATED> */
.p-TabBar-tabIcon,
.p-TabBar-tabCloseIcon,
/* </DEPRECATED> */
.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-TabBar-tabLabel, /* </DEPRECATED> */
.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}


.lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing : border-box;
}


/* <DEPRECATED> */ .p-TabBar-tab.p-mod-hidden, /* </DEPRECATED> */
.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}


.lm-TabBar-addButton.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-TabBar.p-mod-dragging .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='horizontal'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='vertical'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging .p-TabBar-tab.p-mod-dragging,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

.lm-TabBar-tabLabel .lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing : border-box;
  background: inherit;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabPanel-tabBar, /* </DEPRECATED> */
.lm-TabPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-TabPanel-stackedPanel, /* </DEPRECATED> */
.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

@charset "UTF-8";
html{
  -webkit-box-sizing:border-box;
          box-sizing:border-box; }

*,
*::before,
*::after{
  -webkit-box-sizing:inherit;
          box-sizing:inherit; }

body{
  font-size:14px;
  font-weight:400;
  letter-spacing:0;
  line-height:1.28581;
  text-transform:none;
  color:#182026;
  font-family:-apple-system, "BlinkMacSystemFont", "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Open Sans", "Helvetica Neue", "Icons16", sans-serif; }

p{
  margin-bottom:10px;
  margin-top:0; }

small{
  font-size:12px; }

strong{
  font-weight:600; }

::-moz-selection{
  background:rgba(125, 188, 255, 0.6); }

::selection{
  background:rgba(125, 188, 255, 0.6); }
.bp3-heading{
  color:#182026;
  font-weight:600;
  margin:0 0 10px;
  padding:0; }
  .bp3-dark .bp3-heading{
    color:#f5f8fa; }

h1.bp3-heading, .bp3-running-text h1{
  font-size:36px;
  line-height:40px; }

h2.bp3-heading, .bp3-running-text h2{
  font-size:28px;
  line-height:32px; }

h3.bp3-heading, .bp3-running-text h3{
  font-size:22px;
  line-height:25px; }

h4.bp3-heading, .bp3-running-text h4{
  font-size:18px;
  line-height:21px; }

h5.bp3-heading, .bp3-running-text h5{
  font-size:16px;
  line-height:19px; }

h6.bp3-heading, .bp3-running-text h6{
  font-size:14px;
  line-height:16px; }
.bp3-ui-text{
  font-size:14px;
  font-weight:400;
  letter-spacing:0;
  line-height:1.28581;
  text-transform:none; }

.bp3-monospace-text{
  font-family:monospace;
  text-transform:none; }

.bp3-text-muted{
  color:#5c7080; }
  .bp3-dark .bp3-text-muted{
    color:#a7b6c2; }

.bp3-text-disabled{
  color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-text-disabled{
    color:rgba(167, 182, 194, 0.6); }

.bp3-text-overflow-ellipsis{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal; }
.bp3-running-text{
  font-size:14px;
  line-height:1.5; }
  .bp3-running-text h1{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h1{
      color:#f5f8fa; }
  .bp3-running-text h2{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h2{
      color:#f5f8fa; }
  .bp3-running-text h3{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h3{
      color:#f5f8fa; }
  .bp3-running-text h4{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h4{
      color:#f5f8fa; }
  .bp3-running-text h5{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h5{
      color:#f5f8fa; }
  .bp3-running-text h6{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h6{
      color:#f5f8fa; }
  .bp3-running-text hr{
    border:none;
    border-bottom:1px solid rgba(16, 22, 26, 0.15);
    margin:20px 0; }
    .bp3-dark .bp3-running-text hr{
      border-color:rgba(255, 255, 255, 0.15); }
  .bp3-running-text p{
    margin:0 0 10px;
    padding:0; }

.bp3-text-large{
  font-size:16px; }

.bp3-text-small{
  font-size:12px; }
a{
  color:#106ba3;
  text-decoration:none; }
  a:hover{
    color:#106ba3;
    cursor:pointer;
    text-decoration:underline; }
  a .bp3-icon, a .bp3-icon-standard, a .bp3-icon-large{
    color:inherit; }
  a code,
  .bp3-dark a code{
    color:inherit; }
  .bp3-dark a,
  .bp3-dark a:hover{
    color:#48aff0; }
    .bp3-dark a .bp3-icon, .bp3-dark a .bp3-icon-standard, .bp3-dark a .bp3-icon-large,
    .bp3-dark a:hover .bp3-icon,
    .bp3-dark a:hover .bp3-icon-standard,
    .bp3-dark a:hover .bp3-icon-large{
      color:inherit; }
.bp3-running-text code, .bp3-code{
  font-family:monospace;
  text-transform:none;
  background:rgba(255, 255, 255, 0.7);
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
  color:#5c7080;
  font-size:smaller;
  padding:2px 5px; }
  .bp3-dark .bp3-running-text code, .bp3-running-text .bp3-dark code, .bp3-dark .bp3-code{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#a7b6c2; }
  .bp3-running-text a > code, a > .bp3-code{
    color:#137cbd; }
    .bp3-dark .bp3-running-text a > code, .bp3-running-text .bp3-dark a > code, .bp3-dark a > .bp3-code{
      color:inherit; }

.bp3-running-text pre, .bp3-code-block{
  font-family:monospace;
  text-transform:none;
  background:rgba(255, 255, 255, 0.7);
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
  color:#182026;
  display:block;
  font-size:13px;
  line-height:1.4;
  margin:10px 0;
  padding:13px 15px 12px;
  word-break:break-all;
  word-wrap:break-word; }
  .bp3-dark .bp3-running-text pre, .bp3-running-text .bp3-dark pre, .bp3-dark .bp3-code-block{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
  .bp3-running-text pre > code, .bp3-code-block > code{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:inherit;
    font-size:inherit;
    padding:0; }

.bp3-running-text kbd, .bp3-key{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  color:#5c7080;
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  font-family:inherit;
  font-size:12px;
  height:24px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  line-height:24px;
  min-width:24px;
  padding:3px 6px;
  vertical-align:middle; }
  .bp3-running-text kbd .bp3-icon, .bp3-key .bp3-icon, .bp3-running-text kbd .bp3-icon-standard, .bp3-key .bp3-icon-standard, .bp3-running-text kbd .bp3-icon-large, .bp3-key .bp3-icon-large{
    margin-right:5px; }
  .bp3-dark .bp3-running-text kbd, .bp3-running-text .bp3-dark kbd, .bp3-dark .bp3-key{
    background:#394b59;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
    color:#a7b6c2; }
.bp3-running-text blockquote, .bp3-blockquote{
  border-left:solid 4px rgba(167, 182, 194, 0.5);
  margin:0 0 10px;
  padding:0 20px; }
  .bp3-dark .bp3-running-text blockquote, .bp3-running-text .bp3-dark blockquote, .bp3-dark .bp3-blockquote{
    border-color:rgba(115, 134, 148, 0.5); }
.bp3-running-text ul,
.bp3-running-text ol, .bp3-list{
  margin:10px 0;
  padding-left:30px; }
  .bp3-running-text ul li:not(:last-child), .bp3-running-text ol li:not(:last-child), .bp3-list li:not(:last-child){
    margin-bottom:5px; }
  .bp3-running-text ul ol, .bp3-running-text ol ol, .bp3-list ol,
  .bp3-running-text ul ul,
  .bp3-running-text ol ul,
  .bp3-list ul{
    margin-top:5px; }

.bp3-list-unstyled{
  list-style:none;
  margin:0;
  padding:0; }
  .bp3-list-unstyled li{
    padding:0; }
.bp3-rtl{
  text-align:right; }

.bp3-dark{
  color:#f5f8fa; }

:focus{
  outline:rgba(19, 124, 189, 0.6) auto 2px;
  outline-offset:2px;
  -moz-outline-radius:6px; }

.bp3-focus-disabled :focus{
  outline:none !important; }
  .bp3-focus-disabled :focus ~ .bp3-control-indicator{
    outline:none !important; }

.bp3-alert{
  max-width:400px;
  padding:20px; }

.bp3-alert-body{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-alert-body .bp3-icon{
    font-size:40px;
    margin-right:20px;
    margin-top:0; }

.bp3-alert-contents{
  word-break:break-word; }

.bp3-alert-footer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:reverse;
      -ms-flex-direction:row-reverse;
          flex-direction:row-reverse;
  margin-top:10px; }
  .bp3-alert-footer .bp3-button{
    margin-left:10px; }
.bp3-breadcrumbs{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  cursor:default;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:wrap;
      flex-wrap:wrap;
  height:30px;
  list-style:none;
  margin:0;
  padding:0; }
  .bp3-breadcrumbs > li{
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex; }
    .bp3-breadcrumbs > li::after{
      background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.71 7.29l-4-4a1.003 1.003 0 00-1.42 1.42L8.59 8 5.3 11.29c-.19.18-.3.43-.3.71a1.003 1.003 0 001.71.71l4-4c.18-.18.29-.43.29-.71 0-.28-.11-.53-.29-.71z' fill='%235C7080'/%3e%3c/svg%3e");
      content:"";
      display:block;
      height:16px;
      margin:0 5px;
      width:16px; }
    .bp3-breadcrumbs > li:last-of-type::after{
      display:none; }

.bp3-breadcrumb,
.bp3-breadcrumb-current,
.bp3-breadcrumbs-collapsed{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  font-size:16px; }

.bp3-breadcrumb,
.bp3-breadcrumbs-collapsed{
  color:#5c7080; }

.bp3-breadcrumb:hover{
  text-decoration:none; }

.bp3-breadcrumb.bp3-disabled{
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-breadcrumb .bp3-icon{
  margin-right:5px; }

.bp3-breadcrumb-current{
  color:inherit;
  font-weight:600; }
  .bp3-breadcrumb-current .bp3-input{
    font-size:inherit;
    font-weight:inherit;
    vertical-align:baseline; }

.bp3-breadcrumbs-collapsed{
  background:#ced9e0;
  border:none;
  border-radius:3px;
  cursor:pointer;
  margin-right:2px;
  padding:1px 5px;
  vertical-align:text-bottom; }
  .bp3-breadcrumbs-collapsed::before{
    background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cg fill='%235C7080'%3e%3ccircle cx='2' cy='8.03' r='2'/%3e%3ccircle cx='14' cy='8.03' r='2'/%3e%3ccircle cx='8' cy='8.03' r='2'/%3e%3c/g%3e%3c/svg%3e") center no-repeat;
    content:"";
    display:block;
    height:16px;
    width:16px; }
  .bp3-breadcrumbs-collapsed:hover{
    background:#bfccd6;
    color:#182026;
    text-decoration:none; }

.bp3-dark .bp3-breadcrumb,
.bp3-dark .bp3-breadcrumbs-collapsed{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumbs > li::after{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumb.bp3-disabled{
  color:rgba(167, 182, 194, 0.6); }

.bp3-dark .bp3-breadcrumb-current{
  color:#f5f8fa; }

.bp3-dark .bp3-breadcrumbs-collapsed{
  background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-breadcrumbs-collapsed:hover{
    background:rgba(16, 22, 26, 0.6);
    color:#f5f8fa; }
.bp3-button{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  font-size:14px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  padding:5px 10px;
  text-align:left;
  vertical-align:middle;
  min-height:30px;
  min-width:30px; }
  .bp3-button > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-button > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-button::before,
  .bp3-button > *{
    margin-right:7px; }
  .bp3-button:empty::before,
  .bp3-button > :last-child{
    margin-right:0; }
  .bp3-button:empty{
    padding:0 !important; }
  .bp3-button:disabled, .bp3-button.bp3-disabled{
    cursor:not-allowed; }
  .bp3-button.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button.bp3-align-right,
  .bp3-align-right .bp3-button{
    text-align:right; }
  .bp3-button.bp3-align-left,
  .bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-button:not([class*="bp3-intent-"]){
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    color:#182026; }
    .bp3-button:not([class*="bp3-intent-"]):hover{
      background-clip:padding-box;
      background-color:#ebf1f5;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
    .bp3-button:not([class*="bp3-intent-"]):active, .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      background-color:#d8e1e8;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed;
      outline:none; }
      .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active:hover, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-button.bp3-intent-primary{
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover, .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover{
      background-color:#106ba3;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      background-color:#0e5a8a;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-primary:disabled, .bp3-button.bp3-intent-primary.bp3-disabled{
      background-color:rgba(19, 124, 189, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-success{
    background-color:#0f9960;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-success:hover, .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-success:hover{
      background-color:#0d8050;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      background-color:#0a6640;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-success:disabled, .bp3-button.bp3-intent-success.bp3-disabled{
      background-color:rgba(15, 153, 96, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-warning{
    background-color:#d9822b;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover, .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover{
      background-color:#bf7326;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      background-color:#a66321;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-warning:disabled, .bp3-button.bp3-intent-warning.bp3-disabled{
      background-color:rgba(217, 130, 43, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-danger{
    background-color:#db3737;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover, .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover{
      background-color:#c23030;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      background-color:#a82a2a;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-danger:disabled, .bp3-button.bp3-intent-danger.bp3-disabled{
      background-color:rgba(219, 55, 55, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
    stroke:#ffffff; }
  .bp3-button.bp3-large,
  .bp3-large .bp3-button{
    min-height:40px;
    min-width:40px;
    font-size:16px;
    padding:5px 15px; }
    .bp3-button.bp3-large::before,
    .bp3-button.bp3-large > *,
    .bp3-large .bp3-button::before,
    .bp3-large .bp3-button > *{
      margin-right:10px; }
    .bp3-button.bp3-large:empty::before,
    .bp3-button.bp3-large > :last-child,
    .bp3-large .bp3-button:empty::before,
    .bp3-large .bp3-button > :last-child{
      margin-right:0; }
  .bp3-button.bp3-small,
  .bp3-small .bp3-button{
    min-height:24px;
    min-width:24px;
    padding:0 7px; }
  .bp3-button.bp3-loading{
    position:relative; }
    .bp3-button.bp3-loading[class*="bp3-icon-"]::before{
      visibility:hidden; }
    .bp3-button.bp3-loading .bp3-button-spinner{
      margin:0;
      position:absolute; }
    .bp3-button.bp3-loading > :not(.bp3-button-spinner){
      visibility:hidden; }
  .bp3-button[class*="bp3-icon-"]::before{
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-style:normal;
    font-weight:400;
    line-height:1;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    color:#5c7080; }
  .bp3-button .bp3-icon, .bp3-button .bp3-icon-standard, .bp3-button .bp3-icon-large{
    color:#5c7080; }
    .bp3-button .bp3-icon.bp3-align-right, .bp3-button .bp3-icon-standard.bp3-align-right, .bp3-button .bp3-icon-large.bp3-align-right{
      margin-left:7px; }
  .bp3-button .bp3-icon:first-child:last-child,
  .bp3-button .bp3-spinner + .bp3-icon:last-child{
    margin:0 -7px; }
  .bp3-dark .bp3-button:not([class*="bp3-intent-"]){
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover, .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover{
      background-color:#30404d;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      background-color:#202b33;
      background-image:none;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"])[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-large{
      color:#a7b6c2; }
  .bp3-dark .bp3-button[class*="bp3-intent-"]{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:active, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:disabled, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-disabled{
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.3); }
    .bp3-dark .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
      stroke:#8a9ba8; }
  .bp3-button:disabled::before,
  .bp3-button:disabled .bp3-icon, .bp3-button:disabled .bp3-icon-standard, .bp3-button:disabled .bp3-icon-large, .bp3-button.bp3-disabled::before,
  .bp3-button.bp3-disabled .bp3-icon, .bp3-button.bp3-disabled .bp3-icon-standard, .bp3-button.bp3-disabled .bp3-icon-large, .bp3-button[class*="bp3-intent-"]::before,
  .bp3-button[class*="bp3-intent-"] .bp3-icon, .bp3-button[class*="bp3-intent-"] .bp3-icon-standard, .bp3-button[class*="bp3-intent-"] .bp3-icon-large{
    color:inherit !important; }
  .bp3-button.bp3-minimal{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-button.bp3-minimal:hover{
      background:rgba(167, 182, 194, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026;
      text-decoration:none; }
    .bp3-button.bp3-minimal:active, .bp3-button.bp3-minimal.bp3-active{
      background:rgba(115, 134, 148, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026; }
    .bp3-button.bp3-minimal:disabled, .bp3-button.bp3-minimal:disabled:hover, .bp3-button.bp3-minimal.bp3-disabled, .bp3-button.bp3-minimal.bp3-disabled:hover{
      background:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed; }
      .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-minimal{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-minimal:hover, .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none; }
      .bp3-dark .bp3-button.bp3-minimal:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-minimal:disabled, .bp3-dark .bp3-button.bp3-minimal:disabled:hover, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover{
        background:none;
        color:rgba(167, 182, 194, 0.6);
        cursor:not-allowed; }
        .bp3-dark .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover, .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover, .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover, .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover, .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
  .bp3-button.bp3-outlined{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    border:1px solid rgba(24, 32, 38, 0.2);
    -webkit-box-sizing:border-box;
            box-sizing:border-box; }
    .bp3-button.bp3-outlined:hover{
      background:rgba(167, 182, 194, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026;
      text-decoration:none; }
    .bp3-button.bp3-outlined:active, .bp3-button.bp3-outlined.bp3-active{
      background:rgba(115, 134, 148, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026; }
    .bp3-button.bp3-outlined:disabled, .bp3-button.bp3-outlined:disabled:hover, .bp3-button.bp3-outlined.bp3-disabled, .bp3-button.bp3-outlined.bp3-disabled:hover{
      background:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed; }
      .bp3-button.bp3-outlined:disabled.bp3-active, .bp3-button.bp3-outlined:disabled:hover.bp3-active, .bp3-button.bp3-outlined.bp3-disabled.bp3-active, .bp3-button.bp3-outlined.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-outlined{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-outlined:hover, .bp3-dark .bp3-button.bp3-outlined:active, .bp3-dark .bp3-button.bp3-outlined.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none; }
      .bp3-dark .bp3-button.bp3-outlined:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-outlined:active, .bp3-dark .bp3-button.bp3-outlined.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-outlined:disabled, .bp3-dark .bp3-button.bp3-outlined:disabled:hover, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled:hover{
        background:none;
        color:rgba(167, 182, 194, 0.6);
        cursor:not-allowed; }
        .bp3-dark .bp3-button.bp3-outlined:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:hover, .bp3-button.bp3-outlined.bp3-intent-primary:active, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:active, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:hover, .bp3-button.bp3-outlined.bp3-intent-success:active, .bp3-button.bp3-outlined.bp3-intent-success.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:active, .bp3-button.bp3-outlined.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:hover, .bp3-button.bp3-outlined.bp3-intent-warning:active, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:active, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:hover, .bp3-button.bp3-outlined.bp3-intent-danger:active, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:active, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
    .bp3-button.bp3-outlined:disabled, .bp3-button.bp3-outlined.bp3-disabled, .bp3-button.bp3-outlined:disabled:hover, .bp3-button.bp3-outlined.bp3-disabled:hover{
      border-color:rgba(92, 112, 128, 0.1); }
    .bp3-dark .bp3-button.bp3-outlined{
      border-color:rgba(255, 255, 255, 0.4); }
      .bp3-dark .bp3-button.bp3-outlined:disabled, .bp3-dark .bp3-button.bp3-outlined:disabled:hover, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled:hover{
        border-color:rgba(255, 255, 255, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-primary{
      border-color:rgba(16, 107, 163, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
        border-color:rgba(16, 107, 163, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary{
        border-color:rgba(72, 175, 240, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
          border-color:rgba(72, 175, 240, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-success{
      border-color:rgba(13, 128, 80, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
        border-color:rgba(13, 128, 80, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success{
        border-color:rgba(61, 204, 145, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
          border-color:rgba(61, 204, 145, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-warning{
      border-color:rgba(191, 115, 38, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
        border-color:rgba(191, 115, 38, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning{
        border-color:rgba(255, 179, 102, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
          border-color:rgba(255, 179, 102, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-danger{
      border-color:rgba(194, 48, 48, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
        border-color:rgba(194, 48, 48, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger{
        border-color:rgba(255, 115, 115, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
          border-color:rgba(255, 115, 115, 0.2); }

a.bp3-button{
  text-align:center;
  text-decoration:none;
  -webkit-transition:none;
  transition:none; }
  a.bp3-button, a.bp3-button:hover, a.bp3-button:active{
    color:#182026; }
  a.bp3-button.bp3-disabled{
    color:rgba(92, 112, 128, 0.6); }

.bp3-button-text{
  -webkit-box-flex:0;
      -ms-flex:0 1 auto;
          flex:0 1 auto; }

.bp3-button.bp3-align-left .bp3-button-text, .bp3-button.bp3-align-right .bp3-button-text,
.bp3-button-group.bp3-align-left .bp3-button-text,
.bp3-button-group.bp3-align-right .bp3-button-text{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto; }
.bp3-button-group{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex; }
  .bp3-button-group .bp3-button{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    position:relative;
    z-index:4; }
    .bp3-button-group .bp3-button:focus{
      z-index:5; }
    .bp3-button-group .bp3-button:hover{
      z-index:6; }
    .bp3-button-group .bp3-button:active, .bp3-button-group .bp3-button.bp3-active{
      z-index:7; }
    .bp3-button-group .bp3-button:disabled, .bp3-button-group .bp3-button.bp3-disabled{
      z-index:3; }
    .bp3-button-group .bp3-button[class*="bp3-intent-"]{
      z-index:9; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:focus{
        z-index:10; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:hover{
        z-index:11; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:active, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-active{
        z-index:12; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:disabled, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-disabled{
        z-index:8; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:first-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:first-child){
    border-bottom-left-radius:0;
    border-top-left-radius:0; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    border-bottom-right-radius:0;
    border-top-right-radius:0;
    margin-right:-1px; }
  .bp3-button-group.bp3-minimal .bp3-button{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-button-group.bp3-minimal .bp3-button:hover{
      background:rgba(167, 182, 194, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026;
      text-decoration:none; }
    .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
      background:rgba(115, 134, 148, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
      background:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed; }
      .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button-group.bp3-minimal .bp3-button{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:inherit; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
        background:none;
        color:rgba(167, 182, 194, 0.6);
        cursor:not-allowed; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
      color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
      color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
  .bp3-button-group .bp3-popover-wrapper,
  .bp3-button-group .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button-group .bp3-button.bp3-fill,
  .bp3-button-group.bp3-fill .bp3-button:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-vertical{
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    vertical-align:top; }
    .bp3-button-group.bp3-vertical.bp3-fill{
      height:100%;
      width:unset; }
    .bp3-button-group.bp3-vertical .bp3-button{
      margin-right:0 !important;
      width:100%; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:first-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:first-child{
      border-radius:3px 3px 0 0; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:last-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:last-child{
      border-radius:0 0 3px 3px; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:not(:last-child){
      margin-bottom:-1px; }
  .bp3-button-group.bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:1px; }
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-button:not(:last-child){
    margin-bottom:1px; }
.bp3-callout{
  font-size:14px;
  line-height:1.5;
  background-color:rgba(138, 155, 168, 0.15);
  border-radius:3px;
  padding:10px 12px 9px;
  position:relative;
  width:100%; }
  .bp3-callout[class*="bp3-icon-"]{
    padding-left:40px; }
    .bp3-callout[class*="bp3-icon-"]::before{
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-style:normal;
      font-weight:400;
      line-height:1;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      color:#5c7080;
      left:10px;
      position:absolute;
      top:10px; }
  .bp3-callout.bp3-callout-icon{
    padding-left:40px; }
    .bp3-callout.bp3-callout-icon > .bp3-icon:first-child{
      color:#5c7080;
      left:10px;
      position:absolute;
      top:10px; }
  .bp3-callout .bp3-heading{
    line-height:20px;
    margin-bottom:5px;
    margin-top:0; }
    .bp3-callout .bp3-heading:last-child{
      margin-bottom:0; }
  .bp3-dark .bp3-callout{
    background-color:rgba(138, 155, 168, 0.2); }
    .bp3-dark .bp3-callout[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
  .bp3-callout.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15); }
    .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-primary .bp3-heading{
      color:#106ba3; }
    .bp3-dark .bp3-callout.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-primary .bp3-heading{
        color:#48aff0; }
  .bp3-callout.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15); }
    .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-success .bp3-heading{
      color:#0d8050; }
    .bp3-dark .bp3-callout.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-success .bp3-heading{
        color:#3dcc91; }
  .bp3-callout.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15); }
    .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-warning .bp3-heading{
      color:#bf7326; }
    .bp3-dark .bp3-callout.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-warning .bp3-heading{
        color:#ffb366; }
  .bp3-callout.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15); }
    .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-danger .bp3-heading{
      color:#c23030; }
    .bp3-dark .bp3-callout.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-danger .bp3-heading{
        color:#ff7373; }
  .bp3-running-text .bp3-callout{
    margin:20px 0; }
.bp3-card{
  background-color:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
  padding:20px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-card.bp3-dark,
  .bp3-dark .bp3-card{
    background-color:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

.bp3-elevation-0{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }
  .bp3-elevation-0.bp3-dark,
  .bp3-dark .bp3-elevation-0{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

.bp3-elevation-1{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-1.bp3-dark,
  .bp3-dark .bp3-elevation-1{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-elevation-2{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-2.bp3-dark,
  .bp3-dark .bp3-elevation-2{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4); }

.bp3-elevation-3{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-3.bp3-dark,
  .bp3-dark .bp3-elevation-3{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-elevation-4{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-4.bp3-dark,
  .bp3-dark .bp3-elevation-4{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:hover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  cursor:pointer; }
  .bp3-card.bp3-interactive:hover.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:active{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  opacity:0.9;
  -webkit-transition-duration:0;
          transition-duration:0; }
  .bp3-card.bp3-interactive:active.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-collapse{
  height:0;
  overflow-y:hidden;
  -webkit-transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-collapse .bp3-collapse-body{
    -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-collapse .bp3-collapse-body[aria-hidden="true"]{
      display:none; }

.bp3-context-menu .bp3-popover-target{
  display:block; }

.bp3-context-menu-popover-target{
  position:fixed; }

.bp3-divider{
  border-bottom:1px solid rgba(16, 22, 26, 0.15);
  border-right:1px solid rgba(16, 22, 26, 0.15);
  margin:5px; }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-dialog-container{
  opacity:1;
  -webkit-transform:scale(1);
          transform:scale(1);
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  min-height:100%;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none;
  width:100%; }
  .bp3-dialog-container.bp3-overlay-enter > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5); }
  .bp3-dialog-container.bp3-overlay-enter-active > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear-active > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-dialog-container.bp3-overlay-exit > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-dialog-container.bp3-overlay-exit-active > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }

.bp3-dialog{
  background:#ebf1f5;
  border-radius:6px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:30px 0;
  padding-bottom:20px;
  pointer-events:all;
  -webkit-user-select:text;
     -moz-user-select:text;
      -ms-user-select:text;
          user-select:text;
  width:500px; }
  .bp3-dialog:focus{
    outline:0; }
  .bp3-dialog.bp3-dark,
  .bp3-dark .bp3-dialog{
    background:#293742;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }

.bp3-dialog-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background:#ffffff;
  border-radius:6px 6px 0 0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  min-height:40px;
  padding-left:20px;
  padding-right:5px;
  z-index:30; }
  .bp3-dialog-header .bp3-icon-large,
  .bp3-dialog-header .bp3-icon{
    color:#5c7080;
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px; }
  .bp3-dialog-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    line-height:inherit;
    margin:0; }
    .bp3-dialog-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-dialog-header{
    background:#30404d;
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-dialog-header .bp3-icon-large,
    .bp3-dark .bp3-dialog-header .bp3-icon{
      color:#a7b6c2; }

.bp3-dialog-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  line-height:18px;
  margin:20px; }

.bp3-dialog-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  margin:0 20px; }

.bp3-dialog-footer-actions{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:end;
      -ms-flex-pack:end;
          justify-content:flex-end; }
  .bp3-dialog-footer-actions .bp3-button{
    margin-left:10px; }
.bp3-multistep-dialog-panels{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }

.bp3-multistep-dialog-left-panel{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:1;
      -ms-flex:1;
          flex:1;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column; }
  .bp3-dark .bp3-multistep-dialog-left-panel{
    background:#202b33; }

.bp3-multistep-dialog-right-panel{
  background-color:#f5f8fa;
  border-left:1px solid rgba(16, 22, 26, 0.15);
  border-radius:0 0 6px 0;
  -webkit-box-flex:3;
      -ms-flex:3;
          flex:3;
  min-width:0; }
  .bp3-dark .bp3-multistep-dialog-right-panel{
    background-color:#293742;
    border-left:1px solid rgba(16, 22, 26, 0.4); }

.bp3-multistep-dialog-footer{
  background-color:#ffffff;
  border-radius:0 0 6px 0;
  border-top:1px solid rgba(16, 22, 26, 0.15);
  padding:10px; }
  .bp3-dark .bp3-multistep-dialog-footer{
    background:#30404d;
    border-top:1px solid rgba(16, 22, 26, 0.4); }

.bp3-dialog-step-container{
  background-color:#f5f8fa;
  border-bottom:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-dialog-step-container{
    background:#293742;
    border-bottom:1px solid rgba(16, 22, 26, 0.4); }
  .bp3-dialog-step-container.bp3-dialog-step-viewed{
    background-color:#ffffff; }
    .bp3-dark .bp3-dialog-step-container.bp3-dialog-step-viewed{
      background:#30404d; }

.bp3-dialog-step{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background-color:#f5f8fa;
  border-radius:6px;
  cursor:not-allowed;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  margin:4px;
  padding:6px 14px; }
  .bp3-dark .bp3-dialog-step{
    background:#293742; }
  .bp3-dialog-step-viewed .bp3-dialog-step{
    background-color:#ffffff;
    cursor:pointer; }
    .bp3-dark .bp3-dialog-step-viewed .bp3-dialog-step{
      background:#30404d; }
  .bp3-dialog-step:hover{
    background-color:#f5f8fa; }
    .bp3-dark .bp3-dialog-step:hover{
      background:#293742; }

.bp3-dialog-step-icon{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background-color:rgba(92, 112, 128, 0.6);
  border-radius:50%;
  color:#ffffff;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  height:25px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:25px; }
  .bp3-dark .bp3-dialog-step-icon{
    background-color:rgba(167, 182, 194, 0.6); }
  .bp3-active.bp3-dialog-step-viewed .bp3-dialog-step-icon{
    background-color:#2b95d6; }
  .bp3-dialog-step-viewed .bp3-dialog-step-icon{
    background-color:#8a9ba8; }

.bp3-dialog-step-title{
  color:rgba(92, 112, 128, 0.6);
  -webkit-box-flex:1;
      -ms-flex:1;
          flex:1;
  padding-left:10px; }
  .bp3-dark .bp3-dialog-step-title{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-active.bp3-dialog-step-viewed .bp3-dialog-step-title{
    color:#2b95d6; }
  .bp3-dialog-step-viewed:not(.bp3-active) .bp3-dialog-step-title{
    color:#182026; }
    .bp3-dark .bp3-dialog-step-viewed:not(.bp3-active) .bp3-dialog-step-title{
      color:#f5f8fa; }
.bp3-drawer{
  background:#ffffff;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0;
  padding:0; }
  .bp3-drawer:focus{
    outline:0; }
  .bp3-drawer.bp3-position-top{
    height:50%;
    left:0;
    right:0;
    top:0; }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter, .bp3-drawer.bp3-position-top.bp3-overlay-appear{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%); }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter-active, .bp3-drawer.bp3-position-top.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit-active{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-position-bottom{
    bottom:0;
    height:50%;
    left:0;
    right:0; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter-active, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-position-left{
    bottom:0;
    left:0;
    top:0;
    width:50%; }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter, .bp3-drawer.bp3-position-left.bp3-overlay-appear{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%); }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter-active, .bp3-drawer.bp3-position-left.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit-active{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-position-right{
    bottom:0;
    right:0;
    top:0;
    width:50%; }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter, .bp3-drawer.bp3-position-right.bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter-active, .bp3-drawer.bp3-position-right.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right):not(.bp3-vertical){
    bottom:0;
    right:0;
    top:0;
    width:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right).bp3-vertical{
    bottom:0;
    height:50%;
    left:0;
    right:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-dark,
  .bp3-dark .bp3-drawer{
    background:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }

.bp3-drawer-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border-radius:0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  min-height:40px;
  padding:5px;
  padding-left:20px;
  position:relative; }
  .bp3-drawer-header .bp3-icon-large,
  .bp3-drawer-header .bp3-icon{
    color:#5c7080;
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px; }
  .bp3-drawer-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    line-height:inherit;
    margin:0; }
    .bp3-drawer-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-drawer-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-drawer-header .bp3-icon-large,
    .bp3-dark .bp3-drawer-header .bp3-icon{
      color:#a7b6c2; }

.bp3-drawer-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  line-height:18px;
  overflow:auto; }

.bp3-drawer-footer{
  -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  padding:10px 20px;
  position:relative; }
  .bp3-dark .bp3-drawer-footer{
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4); }
.bp3-editable-text{
  cursor:text;
  display:inline-block;
  max-width:100%;
  position:relative;
  vertical-align:top;
  white-space:nowrap; }
  .bp3-editable-text::before{
    bottom:-3px;
    left:-3px;
    position:absolute;
    right:-3px;
    top:-3px;
    border-radius:3px;
    content:"";
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-editable-text.bp3-editable-text-editing::before{
    background-color:#ffffff;
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#137cbd; }
  .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4); }
  .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#0f9960; }
  .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4); }
  .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#d9822b; }
  .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4); }
  .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#db3737; }
  .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4); }
  .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15); }
  .bp3-dark .bp3-editable-text.bp3-editable-text-editing::before{
    background-color:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#48aff0; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4);
            box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#3dcc91; }
  .bp3-dark .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4);
            box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#ffb366; }
  .bp3-dark .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4);
            box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#ff7373; }
  .bp3-dark .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4);
            box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-editable-text-input,
.bp3-editable-text-content{
  color:inherit;
  display:inherit;
  font:inherit;
  letter-spacing:inherit;
  max-width:inherit;
  min-width:inherit;
  position:relative;
  resize:none;
  text-transform:inherit;
  vertical-align:top; }

.bp3-editable-text-input{
  background:none;
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0;
  white-space:pre-wrap;
  width:100%; }
  .bp3-editable-text-input::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input:focus{
    outline:none; }
  .bp3-editable-text-input::-ms-clear{
    display:none; }

.bp3-editable-text-content{
  overflow:hidden;
  padding-right:2px;
  text-overflow:ellipsis;
  white-space:pre; }
  .bp3-editable-text-editing > .bp3-editable-text-content{
    left:0;
    position:absolute;
    visibility:hidden; }
  .bp3-editable-text-placeholder > .bp3-editable-text-content{
    color:rgba(92, 112, 128, 0.6); }
    .bp3-dark .bp3-editable-text-placeholder > .bp3-editable-text-content{
      color:rgba(167, 182, 194, 0.6); }

.bp3-editable-text.bp3-multiline{
  display:block; }
  .bp3-editable-text.bp3-multiline .bp3-editable-text-content{
    overflow:auto;
    white-space:pre-wrap;
    word-wrap:break-word; }
.bp3-divider{
  border-bottom:1px solid rgba(16, 22, 26, 0.15);
  border-right:1px solid rgba(16, 22, 26, 0.15);
  margin:5px; }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-control-group{
  -webkit-transform:translateZ(0);
          transform:translateZ(0);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:stretch;
      -ms-flex-align:stretch;
          align-items:stretch; }
  .bp3-control-group > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select,
  .bp3-control-group .bp3-input,
  .bp3-control-group .bp3-select{
    position:relative; }
  .bp3-control-group .bp3-input{
    border-radius:inherit;
    z-index:2; }
    .bp3-control-group .bp3-input:focus{
      border-radius:3px;
      z-index:14; }
    .bp3-control-group .bp3-input[class*="bp3-intent"]{
      z-index:13; }
      .bp3-control-group .bp3-input[class*="bp3-intent"]:focus{
        z-index:15; }
    .bp3-control-group .bp3-input[readonly], .bp3-control-group .bp3-input:disabled, .bp3-control-group .bp3-input.bp3-disabled{
      z-index:1; }
  .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input{
    z-index:13; }
    .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input:focus{
      z-index:15; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select select,
  .bp3-control-group .bp3-select select{
    -webkit-transform:translateZ(0);
            transform:translateZ(0);
    border-radius:inherit;
    z-index:4; }
    .bp3-control-group .bp3-button:focus,
    .bp3-control-group .bp3-html-select select:focus,
    .bp3-control-group .bp3-select select:focus{
      z-index:5; }
    .bp3-control-group .bp3-button:hover,
    .bp3-control-group .bp3-html-select select:hover,
    .bp3-control-group .bp3-select select:hover{
      z-index:6; }
    .bp3-control-group .bp3-button:active,
    .bp3-control-group .bp3-html-select select:active,
    .bp3-control-group .bp3-select select:active{
      z-index:7; }
    .bp3-control-group .bp3-button[readonly], .bp3-control-group .bp3-button:disabled, .bp3-control-group .bp3-button.bp3-disabled,
    .bp3-control-group .bp3-html-select select[readonly],
    .bp3-control-group .bp3-html-select select:disabled,
    .bp3-control-group .bp3-html-select select.bp3-disabled,
    .bp3-control-group .bp3-select select[readonly],
    .bp3-control-group .bp3-select select:disabled,
    .bp3-control-group .bp3-select select.bp3-disabled{
      z-index:3; }
    .bp3-control-group .bp3-button[class*="bp3-intent"],
    .bp3-control-group .bp3-html-select select[class*="bp3-intent"],
    .bp3-control-group .bp3-select select[class*="bp3-intent"]{
      z-index:9; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:focus{
        z-index:10; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:hover{
        z-index:11; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:active{
        z-index:12; }
      .bp3-control-group .bp3-button[class*="bp3-intent"][readonly], .bp3-control-group .bp3-button[class*="bp3-intent"]:disabled, .bp3-control-group .bp3-button[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"].bp3-disabled{
        z-index:8; }
  .bp3-control-group .bp3-input-group > .bp3-icon,
  .bp3-control-group .bp3-input-group > .bp3-button,
  .bp3-control-group .bp3-input-group > .bp3-input-left-container,
  .bp3-control-group .bp3-input-group > .bp3-input-action{
    z-index:16; }
  .bp3-control-group .bp3-select::after,
  .bp3-control-group .bp3-html-select::after,
  .bp3-control-group .bp3-select > .bp3-icon,
  .bp3-control-group .bp3-html-select > .bp3-icon{
    z-index:17; }
  .bp3-control-group .bp3-select:focus-within{
    z-index:5; }
  .bp3-control-group:not(.bp3-vertical) > *:not(.bp3-divider){
    margin-right:-1px; }
  .bp3-control-group:not(.bp3-vertical) > .bp3-divider:not(:first-child){
    margin-left:6px; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > *:not(.bp3-divider){
    margin-right:0; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > .bp3-button + .bp3-button{
    margin-left:1px; }
  .bp3-control-group .bp3-popover-wrapper,
  .bp3-control-group .bp3-popover-target{
    border-radius:inherit; }
  .bp3-control-group > :first-child{
    border-radius:3px 0 0 3px; }
  .bp3-control-group > :last-child{
    border-radius:0 3px 3px 0;
    margin-right:0; }
  .bp3-control-group > :only-child{
    border-radius:3px;
    margin-right:0; }
  .bp3-control-group .bp3-input-group .bp3-button{
    border-radius:3px; }
  .bp3-control-group .bp3-numeric-input:not(:first-child) .bp3-input-group{
    border-bottom-left-radius:0;
    border-top-left-radius:0; }
  .bp3-control-group.bp3-fill{
    width:100%; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-fill > *:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-control-group.bp3-vertical > *{
      margin-top:-1px; }
    .bp3-control-group.bp3-vertical > :first-child{
      border-radius:3px 3px 0 0;
      margin-top:0; }
    .bp3-control-group.bp3-vertical > :last-child{
      border-radius:0 0 3px 3px; }
.bp3-control{
  cursor:pointer;
  display:block;
  margin-bottom:10px;
  position:relative;
  text-transform:none; }
  .bp3-control input:checked ~ .bp3-control-indicator{
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
  .bp3-control:hover input:checked ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
  .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    background:#0e5a8a;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control:hover input:checked ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    background-color:#0e5a8a;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-control:not(.bp3-align-right){
    padding-left:26px; }
    .bp3-control:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-26px; }
  .bp3-control.bp3-align-right{
    padding-right:26px; }
    .bp3-control.bp3-align-right .bp3-control-indicator{
      margin-right:-26px; }
  .bp3-control.bp3-disabled{
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
  .bp3-control.bp3-inline{
    display:inline-block;
    margin-right:20px; }
  .bp3-control input{
    left:0;
    opacity:0;
    position:absolute;
    top:0;
    z-index:-1; }
  .bp3-control .bp3-control-indicator{
    background-clip:padding-box;
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    border:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    cursor:pointer;
    display:inline-block;
    font-size:16px;
    height:1em;
    margin-right:10px;
    margin-top:-3px;
    position:relative;
    -webkit-user-select:none;
       -moz-user-select:none;
        -ms-user-select:none;
            user-select:none;
    vertical-align:middle;
    width:1em; }
    .bp3-control .bp3-control-indicator::before{
      content:"";
      display:block;
      height:1em;
      width:1em; }
  .bp3-control:hover .bp3-control-indicator{
    background-color:#ebf1f5; }
  .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
    background:#d8e1e8;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-control input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none;
    cursor:not-allowed; }
  .bp3-control input:focus ~ .bp3-control-indicator{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:2px;
    -moz-outline-radius:6px; }
  .bp3-control.bp3-align-right .bp3-control-indicator{
    float:right;
    margin-left:10px;
    margin-top:1px; }
  .bp3-control.bp3-large{
    font-size:16px; }
    .bp3-control.bp3-large:not(.bp3-align-right){
      padding-left:30px; }
      .bp3-control.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
        margin-left:-30px; }
    .bp3-control.bp3-large.bp3-align-right{
      padding-right:30px; }
      .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
        margin-right:-30px; }
    .bp3-control.bp3-large .bp3-control-indicator{
      font-size:20px; }
    .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-top:0; }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
  .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
  .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    background:#0e5a8a;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    background-color:#0e5a8a;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-control.bp3-checkbox .bp3-control-indicator{
    border-radius:3px; }
  .bp3-control.bp3-checkbox input:checked ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M12 5c-.28 0-.53.11-.71.29L7 9.59l-2.29-2.3a1.003 1.003 0 00-1.42 1.42l3 3c.18.18.43.29.71.29s.53-.11.71-.29l5-5A1.003 1.003 0 0012 5z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M11 7H5c-.55 0-1 .45-1 1s.45 1 1 1h6c.55 0 1-.45 1-1s-.45-1-1-1z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-radio .bp3-control-indicator{
    border-radius:50%; }
  .bp3-control.bp3-radio input:checked ~ .bp3-control-indicator::before{
    background-image:radial-gradient(#ffffff, #ffffff 28%, transparent 32%); }
  .bp3-control.bp3-radio input:checked:disabled ~ .bp3-control-indicator::before{
    opacity:0.5; }
  .bp3-control.bp3-radio input:focus ~ .bp3-control-indicator{
    -moz-outline-radius:16px; }
  .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(167, 182, 194, 0.5); }
  .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(115, 134, 148, 0.5); }
  .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(92, 112, 128, 0.5); }
  .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5); }
    .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5); }
    .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch:not(.bp3-align-right){
    padding-left:38px; }
    .bp3-control.bp3-switch:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-38px; }
  .bp3-control.bp3-switch.bp3-align-right{
    padding-right:38px; }
    .bp3-control.bp3-switch.bp3-align-right .bp3-control-indicator{
      margin-right:-38px; }
  .bp3-control.bp3-switch .bp3-control-indicator{
    border:none;
    border-radius:1.75em;
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    min-width:1.75em;
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    width:auto; }
    .bp3-control.bp3-switch .bp3-control-indicator::before{
      background:#ffffff;
      border-radius:50%;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
      height:calc(1em - 4px);
      left:0;
      margin:2px;
      position:absolute;
      -webkit-transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      width:calc(1em - 4px); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    left:calc(100% - 1em); }
  .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right){
    padding-left:45px; }
    .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-45px; }
  .bp3-control.bp3-switch.bp3-large.bp3-align-right{
    padding-right:45px; }
    .bp3-control.bp3-switch.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-right:-45px; }
  .bp3-dark .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.7); }
  .bp3-dark .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.9); }
  .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(57, 75, 89, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-dark .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-dark .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch .bp3-control-indicator::before{
    background:#394b59;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-control.bp3-switch .bp3-switch-inner-text{
    font-size:0.7em;
    text-align:center; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:first-child{
    line-height:0;
    margin-left:0.5em;
    margin-right:1.2em;
    visibility:hidden; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:last-child{
    line-height:1em;
    margin-left:1.2em;
    margin-right:0.5em;
    visibility:visible; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:first-child{
    line-height:1em;
    visibility:visible; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:last-child{
    line-height:0;
    visibility:hidden; }
  .bp3-dark .bp3-control{
    color:#f5f8fa; }
    .bp3-dark .bp3-control.bp3-disabled{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-control .bp3-control-indicator{
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-control:hover .bp3-control-indicator{
      background-color:#30404d; }
    .bp3-dark .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
      background:#202b33;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-control input:disabled ~ .bp3-control-indicator{
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      cursor:not-allowed; }
    .bp3-dark .bp3-control.bp3-checkbox input:disabled:checked ~ .bp3-control-indicator, .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
      color:rgba(167, 182, 194, 0.6); }
.bp3-file-input{
  cursor:pointer;
  display:inline-block;
  height:30px;
  position:relative; }
  .bp3-file-input input{
    margin:0;
    min-width:200px;
    opacity:0; }
    .bp3-file-input input:disabled + .bp3-file-upload-input,
    .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
      background:rgba(206, 217, 224, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed;
      resize:none; }
      .bp3-file-input input:disabled + .bp3-file-upload-input::after,
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
        background-color:rgba(206, 217, 224, 0.5);
        background-image:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:rgba(92, 112, 128, 0.6);
        cursor:not-allowed;
        outline:none; }
        .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active:hover,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active:hover{
          background:rgba(206, 217, 224, 0.7); }
      .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input, .bp3-dark
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
        background:rgba(57, 75, 89, 0.5);
        -webkit-box-shadow:none;
                box-shadow:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after, .bp3-dark
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
          background-color:rgba(57, 75, 89, 0.5);
          background-image:none;
          -webkit-box-shadow:none;
                  box-shadow:none;
          color:rgba(167, 182, 194, 0.6); }
          .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-dark
          .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active{
            background:rgba(57, 75, 89, 0.7); }
  .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#182026; }
  .bp3-dark .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#f5f8fa; }
  .bp3-file-input.bp3-fill{
    width:100%; }
  .bp3-file-input.bp3-large,
  .bp3-large .bp3-file-input{
    height:40px; }
  .bp3-file-input .bp3-file-upload-input-custom-text::after{
    content:attr(bp3-button-text); }

.bp3-file-upload-input{
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  background:#ffffff;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  color:#182026;
  font-size:14px;
  font-weight:400;
  height:30px;
  line-height:30px;
  outline:none;
  padding:0 10px;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  vertical-align:middle;
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  color:rgba(92, 112, 128, 0.6);
  left:0;
  padding-right:80px;
  position:absolute;
  right:0;
  top:0;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-file-upload-input::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input:focus, .bp3-file-upload-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-file-upload-input[type="search"], .bp3-file-upload-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-file-upload-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-file-upload-input:disabled, .bp3-file-upload-input.bp3-disabled{
    background:rgba(206, 217, 224, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    resize:none; }
  .bp3-file-upload-input::after{
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    color:#182026;
    min-height:24px;
    min-width:24px;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    border-radius:3px;
    content:"Browse";
    line-height:24px;
    margin:3px;
    position:absolute;
    right:0;
    text-align:center;
    top:0;
    width:70px; }
    .bp3-file-upload-input::after:hover{
      background-clip:padding-box;
      background-color:#ebf1f5;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
    .bp3-file-upload-input::after:active, .bp3-file-upload-input::after.bp3-active{
      background-color:#d8e1e8;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-file-upload-input::after:disabled, .bp3-file-upload-input::after.bp3-disabled{
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed;
      outline:none; }
      .bp3-file-upload-input::after:disabled.bp3-active, .bp3-file-upload-input::after:disabled.bp3-active:hover, .bp3-file-upload-input::after.bp3-disabled.bp3-active, .bp3-file-upload-input::after.bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-file-upload-input:hover::after{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
  .bp3-file-upload-input:active::after{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-large .bp3-file-upload-input{
    font-size:16px;
    height:40px;
    line-height:40px;
    padding-right:95px; }
    .bp3-large .bp3-file-upload-input[type="search"], .bp3-large .bp3-file-upload-input.bp3-round{
      padding:0 15px; }
    .bp3-large .bp3-file-upload-input::after{
      min-height:30px;
      min-width:30px;
      line-height:30px;
      margin:5px;
      width:85px; }
  .bp3-dark .bp3-file-upload-input{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:disabled, .bp3-dark .bp3-file-upload-input.bp3-disabled{
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::after{
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover, .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover{
        background-color:#30404d;
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        background-color:#202b33;
        background-image:none;
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
      .bp3-dark .bp3-file-upload-input::after:disabled, .bp3-dark .bp3-file-upload-input::after.bp3-disabled{
        background-color:rgba(57, 75, 89, 0.5);
        background-image:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-upload-input::after:disabled.bp3-active, .bp3-dark .bp3-file-upload-input::after.bp3-disabled.bp3-active{
          background:rgba(57, 75, 89, 0.7); }
      .bp3-dark .bp3-file-upload-input::after .bp3-button-spinner .bp3-spinner-head{
        background:rgba(16, 22, 26, 0.5);
        stroke:#8a9ba8; }
    .bp3-dark .bp3-file-upload-input:hover::after{
      background-color:#30404d;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:active::after{
      background-color:#202b33;
      background-image:none;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
.bp3-file-upload-input::after{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
.bp3-form-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0 0 15px; }
  .bp3-form-group label.bp3-label{
    margin-bottom:5px; }
  .bp3-form-group .bp3-control{
    margin-top:7px; }
  .bp3-form-group .bp3-form-helper-text{
    color:#5c7080;
    font-size:12px;
    margin-top:5px; }
  .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#106ba3; }
  .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#0d8050; }
  .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#bf7326; }
  .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#c23030; }
  .bp3-form-group.bp3-inline{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row; }
    .bp3-form-group.bp3-inline.bp3-large label.bp3-label{
      line-height:40px;
      margin:0 10px 0 0; }
    .bp3-form-group.bp3-inline label.bp3-label{
      line-height:30px;
      margin:0 10px 0 0; }
  .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-dark .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#48aff0; }
  .bp3-dark .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#3dcc91; }
  .bp3-dark .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#ffb366; }
  .bp3-dark .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#ff7373; }
  .bp3-dark .bp3-form-group .bp3-form-helper-text{
    color:#a7b6c2; }
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(167, 182, 194, 0.6) !important; }
.bp3-input-group{
  display:block;
  position:relative; }
  .bp3-input-group .bp3-input{
    position:relative;
    width:100%; }
    .bp3-input-group .bp3-input:not(:first-child){
      padding-left:30px; }
    .bp3-input-group .bp3-input:not(:last-child){
      padding-right:30px; }
  .bp3-input-group .bp3-input-action,
  .bp3-input-group > .bp3-input-left-container,
  .bp3-input-group > .bp3-button,
  .bp3-input-group > .bp3-icon{
    position:absolute;
    top:0; }
    .bp3-input-group .bp3-input-action:first-child,
    .bp3-input-group > .bp3-input-left-container:first-child,
    .bp3-input-group > .bp3-button:first-child,
    .bp3-input-group > .bp3-icon:first-child{
      left:0; }
    .bp3-input-group .bp3-input-action:last-child,
    .bp3-input-group > .bp3-input-left-container:last-child,
    .bp3-input-group > .bp3-button:last-child,
    .bp3-input-group > .bp3-icon:last-child{
      right:0; }
  .bp3-input-group .bp3-button{
    min-height:24px;
    min-width:24px;
    margin:3px;
    padding:0 7px; }
    .bp3-input-group .bp3-button:empty{
      padding:0; }
  .bp3-input-group > .bp3-input-left-container,
  .bp3-input-group > .bp3-icon{
    z-index:1; }
  .bp3-input-group > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group > .bp3-icon{
    color:#5c7080; }
    .bp3-input-group > .bp3-input-left-container > .bp3-icon:empty,
    .bp3-input-group > .bp3-icon:empty{
      font-family:"Icons16", sans-serif;
      font-size:16px;
      font-style:normal;
      font-weight:400;
      line-height:1;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased; }
  .bp3-input-group > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group > .bp3-icon,
  .bp3-input-group .bp3-input-action > .bp3-spinner{
    margin:7px; }
  .bp3-input-group .bp3-tag{
    margin:5px; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus),
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
    color:#5c7080; }
    .bp3-dark .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus), .bp3-dark
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
      color:#a7b6c2; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large{
      color:#5c7080; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled,
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled{
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-large{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-input-group.bp3-disabled{
    cursor:not-allowed; }
    .bp3-input-group.bp3-disabled .bp3-icon{
      color:rgba(92, 112, 128, 0.6); }
  .bp3-input-group.bp3-large .bp3-button{
    min-height:30px;
    min-width:30px;
    margin:5px; }
  .bp3-input-group.bp3-large > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group.bp3-large > .bp3-icon,
  .bp3-input-group.bp3-large .bp3-input-action > .bp3-spinner{
    margin:12px; }
  .bp3-input-group.bp3-large .bp3-input{
    font-size:16px;
    height:40px;
    line-height:40px; }
    .bp3-input-group.bp3-large .bp3-input[type="search"], .bp3-input-group.bp3-large .bp3-input.bp3-round{
      padding:0 15px; }
    .bp3-input-group.bp3-large .bp3-input:not(:first-child){
      padding-left:40px; }
    .bp3-input-group.bp3-large .bp3-input:not(:last-child){
      padding-right:40px; }
  .bp3-input-group.bp3-small .bp3-button{
    min-height:20px;
    min-width:20px;
    margin:2px; }
  .bp3-input-group.bp3-small .bp3-tag{
    min-height:20px;
    min-width:20px;
    margin:2px; }
  .bp3-input-group.bp3-small > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group.bp3-small > .bp3-icon,
  .bp3-input-group.bp3-small .bp3-input-action > .bp3-spinner{
    margin:4px; }
  .bp3-input-group.bp3-small .bp3-input{
    font-size:12px;
    height:24px;
    line-height:24px;
    padding-left:8px;
    padding-right:8px; }
    .bp3-input-group.bp3-small .bp3-input[type="search"], .bp3-input-group.bp3-small .bp3-input.bp3-round{
      padding:0 12px; }
    .bp3-input-group.bp3-small .bp3-input:not(:first-child){
      padding-left:24px; }
    .bp3-input-group.bp3-small .bp3-input:not(:last-child){
      padding-right:24px; }
  .bp3-input-group.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-input-group.bp3-round .bp3-button,
  .bp3-input-group.bp3-round .bp3-input,
  .bp3-input-group.bp3-round .bp3-tag{
    border-radius:30px; }
  .bp3-dark .bp3-input-group .bp3-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-input-group.bp3-disabled .bp3-icon{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-input-group.bp3-intent-primary .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input-group.bp3-intent-primary .bp3-input:disabled, .bp3-input-group.bp3-intent-primary .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-primary > .bp3-icon{
    color:#106ba3; }
    .bp3-dark .bp3-input-group.bp3-intent-primary > .bp3-icon{
      color:#48aff0; }
  .bp3-input-group.bp3-intent-success .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input-group.bp3-intent-success .bp3-input:disabled, .bp3-input-group.bp3-intent-success .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-success > .bp3-icon{
    color:#0d8050; }
    .bp3-dark .bp3-input-group.bp3-intent-success > .bp3-icon{
      color:#3dcc91; }
  .bp3-input-group.bp3-intent-warning .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input-group.bp3-intent-warning .bp3-input:disabled, .bp3-input-group.bp3-intent-warning .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-warning > .bp3-icon{
    color:#bf7326; }
    .bp3-dark .bp3-input-group.bp3-intent-warning > .bp3-icon{
      color:#ffb366; }
  .bp3-input-group.bp3-intent-danger .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input-group.bp3-intent-danger .bp3-input:disabled, .bp3-input-group.bp3-intent-danger .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-danger > .bp3-icon{
    color:#c23030; }
    .bp3-dark .bp3-input-group.bp3-intent-danger > .bp3-icon{
      color:#ff7373; }
.bp3-input{
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  background:#ffffff;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  color:#182026;
  font-size:14px;
  font-weight:400;
  height:30px;
  line-height:30px;
  outline:none;
  padding:0 10px;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  vertical-align:middle; }
  .bp3-input::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input:focus, .bp3-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-input[type="search"], .bp3-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-input:disabled, .bp3-input.bp3-disabled{
    background:rgba(206, 217, 224, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    resize:none; }
  .bp3-input.bp3-large{
    font-size:16px;
    height:40px;
    line-height:40px; }
    .bp3-input.bp3-large[type="search"], .bp3-input.bp3-large.bp3-round{
      padding:0 15px; }
  .bp3-input.bp3-small{
    font-size:12px;
    height:24px;
    line-height:24px;
    padding-left:8px;
    padding-right:8px; }
    .bp3-input.bp3-small[type="search"], .bp3-input.bp3-small.bp3-round{
      padding:0 12px; }
  .bp3-input.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-dark .bp3-input{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark .bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input:disabled, .bp3-dark .bp3-input.bp3-disabled{
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
  .bp3-input.bp3-intent-primary{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input.bp3-intent-primary:disabled, .bp3-input.bp3-intent-primary.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary:focus{
        -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #137cbd;
                box-shadow:inset 0 0 0 1px #137cbd; }
      .bp3-dark .bp3-input.bp3-intent-primary:disabled, .bp3-dark .bp3-input.bp3-intent-primary.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-success{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input.bp3-intent-success:disabled, .bp3-input.bp3-intent-success.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-success{
      -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success:focus{
        -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #0f9960;
                box-shadow:inset 0 0 0 1px #0f9960; }
      .bp3-dark .bp3-input.bp3-intent-success:disabled, .bp3-dark .bp3-input.bp3-intent-success.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-warning{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input.bp3-intent-warning:disabled, .bp3-input.bp3-intent-warning.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning:focus{
        -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #d9822b;
                box-shadow:inset 0 0 0 1px #d9822b; }
      .bp3-dark .bp3-input.bp3-intent-warning:disabled, .bp3-dark .bp3-input.bp3-intent-warning.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-danger{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input.bp3-intent-danger:disabled, .bp3-input.bp3-intent-danger.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger:focus{
        -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #db3737;
                box-shadow:inset 0 0 0 1px #db3737; }
      .bp3-dark .bp3-input.bp3-intent-danger:disabled, .bp3-dark .bp3-input.bp3-intent-danger.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input::-ms-clear{
    display:none; }
textarea.bp3-input{
  max-width:100%;
  padding:10px; }
  textarea.bp3-input, textarea.bp3-input.bp3-large, textarea.bp3-input.bp3-small{
    height:auto;
    line-height:inherit; }
  textarea.bp3-input.bp3-small{
    padding:8px; }
  .bp3-dark textarea.bp3-input{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark textarea.bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input:disabled, .bp3-dark textarea.bp3-input.bp3-disabled{
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
label.bp3-label{
  display:block;
  margin-bottom:15px;
  margin-top:0; }
  label.bp3-label .bp3-html-select,
  label.bp3-label .bp3-input,
  label.bp3-label .bp3-select,
  label.bp3-label .bp3-slider,
  label.bp3-label .bp3-popover-wrapper{
    display:block;
    margin-top:5px;
    text-transform:none; }
  label.bp3-label .bp3-button-group{
    margin-top:5px; }
  label.bp3-label .bp3-select select,
  label.bp3-label .bp3-html-select select{
    font-weight:400;
    vertical-align:top;
    width:100%; }
  label.bp3-label.bp3-disabled,
  label.bp3-label.bp3-disabled .bp3-text-muted{
    color:rgba(92, 112, 128, 0.6); }
  label.bp3-label.bp3-inline{
    line-height:30px; }
    label.bp3-label.bp3-inline .bp3-html-select,
    label.bp3-label.bp3-inline .bp3-input,
    label.bp3-label.bp3-inline .bp3-input-group,
    label.bp3-label.bp3-inline .bp3-select,
    label.bp3-label.bp3-inline .bp3-popover-wrapper{
      display:inline-block;
      margin:0 0 0 5px;
      vertical-align:top; }
    label.bp3-label.bp3-inline .bp3-button-group{
      margin:0 0 0 5px; }
    label.bp3-label.bp3-inline .bp3-input-group .bp3-input{
      margin-left:0; }
    label.bp3-label.bp3-inline.bp3-large{
      line-height:40px; }
  label.bp3-label:not(.bp3-inline) .bp3-popover-target{
    display:block; }
  .bp3-dark label.bp3-label{
    color:#f5f8fa; }
    .bp3-dark label.bp3-label.bp3-disabled,
    .bp3-dark label.bp3-label.bp3-disabled .bp3-text-muted{
      color:rgba(167, 182, 194, 0.6); }
.bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button{
  -webkit-box-flex:1;
      -ms-flex:1 1 14px;
          flex:1 1 14px;
  min-height:0;
  padding:0;
  width:30px; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:first-child{
    border-radius:0 3px 0 0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:last-child{
    border-radius:0 0 3px 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:first-child{
  border-radius:3px 0 0 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:last-child{
  border-radius:0 0 0 3px; }

.bp3-numeric-input.bp3-large .bp3-button-group.bp3-vertical > .bp3-button{
  width:40px; }

form{
  display:block; }
.bp3-html-select select,
.bp3-select select{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  font-size:14px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  padding:5px 10px;
  text-align:left;
  vertical-align:middle;
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  color:#182026;
  -moz-appearance:none;
  -webkit-appearance:none;
  border-radius:3px;
  height:30px;
  padding:0 25px 0 10px;
  width:100%; }
  .bp3-html-select select > *, .bp3-select select > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-html-select select > .bp3-fill, .bp3-select select > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-html-select select::before,
  .bp3-select select::before, .bp3-html-select select > *, .bp3-select select > *{
    margin-right:7px; }
  .bp3-html-select select:empty::before,
  .bp3-select select:empty::before,
  .bp3-html-select select > :last-child,
  .bp3-select select > :last-child{
    margin-right:0; }
  .bp3-html-select select:hover,
  .bp3-select select:hover{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
  .bp3-html-select select:active,
  .bp3-select select:active, .bp3-html-select select.bp3-active,
  .bp3-select select.bp3-active{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-html-select select:disabled,
  .bp3-select select:disabled, .bp3-html-select select.bp3-disabled,
  .bp3-select select.bp3-disabled{
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    outline:none; }
    .bp3-html-select select:disabled.bp3-active,
    .bp3-select select:disabled.bp3-active, .bp3-html-select select:disabled.bp3-active:hover,
    .bp3-select select:disabled.bp3-active:hover, .bp3-html-select select.bp3-disabled.bp3-active,
    .bp3-select select.bp3-disabled.bp3-active, .bp3-html-select select.bp3-disabled.bp3-active:hover,
    .bp3-select select.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }

.bp3-html-select.bp3-minimal select,
.bp3-select.bp3-minimal select{
  background:none;
  -webkit-box-shadow:none;
          box-shadow:none; }
  .bp3-html-select.bp3-minimal select:hover,
  .bp3-select.bp3-minimal select:hover{
    background:rgba(167, 182, 194, 0.3);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:#182026;
    text-decoration:none; }
  .bp3-html-select.bp3-minimal select:active,
  .bp3-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal select.bp3-active,
  .bp3-select.bp3-minimal select.bp3-active{
    background:rgba(115, 134, 148, 0.3);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:#182026; }
  .bp3-html-select.bp3-minimal select:disabled,
  .bp3-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal select:disabled:hover,
  .bp3-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal select.bp3-disabled,
  .bp3-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal select.bp3-disabled:hover,
  .bp3-select.bp3-minimal select.bp3-disabled:hover{
    background:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
    .bp3-html-select.bp3-minimal select:disabled.bp3-active,
    .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active{
      background:rgba(115, 134, 148, 0.3); }
  .bp3-dark .bp3-html-select.bp3-minimal select, .bp3-html-select.bp3-minimal .bp3-dark select,
  .bp3-dark .bp3-select.bp3-minimal select, .bp3-select.bp3-minimal .bp3-dark select{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:inherit; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover, .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover{
      background:rgba(138, 155, 168, 0.15); }
    .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:rgba(138, 155, 168, 0.3);
      color:#f5f8fa; }
    .bp3-dark .bp3-html-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal .bp3-dark select:disabled,
    .bp3-dark .bp3-select.bp3-minimal select:disabled, .bp3-select.bp3-minimal .bp3-dark select:disabled, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select:disabled:hover, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover{
      background:none;
      color:rgba(167, 182, 194, 0.6);
      cursor:not-allowed; }
      .bp3-dark .bp3-html-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active{
        background:rgba(138, 155, 168, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-primary,
  .bp3-select.bp3-minimal select.bp3-intent-primary{
    color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover{
      background:rgba(19, 124, 189, 0.15);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      background:rgba(19, 124, 189, 0.3);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled{
      background:none;
      color:rgba(16, 107, 163, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active{
        background:rgba(19, 124, 189, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
      stroke:#106ba3; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary{
      color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.2);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(72, 175, 240, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-success,
  .bp3-select.bp3-minimal select.bp3-intent-success{
    color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover{
      background:rgba(15, 153, 96, 0.15);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      background:rgba(15, 153, 96, 0.3);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled{
      background:none;
      color:rgba(13, 128, 80, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active{
        background:rgba(15, 153, 96, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
      stroke:#0d8050; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success{
      color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.2);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(61, 204, 145, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-warning,
  .bp3-select.bp3-minimal select.bp3-intent-warning{
    color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover{
      background:rgba(217, 130, 43, 0.15);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      background:rgba(217, 130, 43, 0.3);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled{
      background:none;
      color:rgba(191, 115, 38, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active{
        background:rgba(217, 130, 43, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
      stroke:#bf7326; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning{
      color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.2);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(255, 179, 102, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-danger,
  .bp3-select.bp3-minimal select.bp3-intent-danger{
    color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover{
      background:rgba(219, 55, 55, 0.15);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      background:rgba(219, 55, 55, 0.3);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled{
      background:none;
      color:rgba(194, 48, 48, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active{
        background:rgba(219, 55, 55, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
      stroke:#c23030; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger{
      color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.2);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(255, 115, 115, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }

.bp3-html-select.bp3-large select,
.bp3-select.bp3-large select{
  font-size:16px;
  height:40px;
  padding-right:35px; }

.bp3-dark .bp3-html-select select, .bp3-dark .bp3-select select{
  background-color:#394b59;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
  color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover, .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover{
    background-color:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    background-color:#202b33;
    background-image:none;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-html-select select:disabled, .bp3-dark .bp3-select select:disabled, .bp3-dark .bp3-html-select select.bp3-disabled, .bp3-dark .bp3-select select.bp3-disabled{
    background-color:rgba(57, 75, 89, 0.5);
    background-image:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-html-select select:disabled.bp3-active, .bp3-dark .bp3-select select:disabled.bp3-active, .bp3-dark .bp3-html-select select.bp3-disabled.bp3-active, .bp3-dark .bp3-select select.bp3-disabled.bp3-active{
      background:rgba(57, 75, 89, 0.7); }
  .bp3-dark .bp3-html-select select .bp3-button-spinner .bp3-spinner-head, .bp3-dark .bp3-select select .bp3-button-spinner .bp3-spinner-head{
    background:rgba(16, 22, 26, 0.5);
    stroke:#8a9ba8; }

.bp3-html-select select:disabled,
.bp3-select select:disabled{
  background-color:rgba(206, 217, 224, 0.5);
  -webkit-box-shadow:none;
          box-shadow:none;
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-html-select .bp3-icon,
.bp3-select .bp3-icon, .bp3-select::after{
  color:#5c7080;
  pointer-events:none;
  position:absolute;
  right:7px;
  top:7px; }
  .bp3-html-select .bp3-disabled.bp3-icon,
  .bp3-select .bp3-disabled.bp3-icon, .bp3-disabled.bp3-select::after{
    color:rgba(92, 112, 128, 0.6); }
.bp3-html-select,
.bp3-select{
  display:inline-block;
  letter-spacing:normal;
  position:relative;
  vertical-align:middle; }
  .bp3-html-select select::-ms-expand,
  .bp3-select select::-ms-expand{
    display:none; }
  .bp3-html-select .bp3-icon,
  .bp3-select .bp3-icon{
    color:#5c7080; }
    .bp3-html-select .bp3-icon:hover,
    .bp3-select .bp3-icon:hover{
      color:#182026; }
    .bp3-dark .bp3-html-select .bp3-icon, .bp3-dark
    .bp3-select .bp3-icon{
      color:#a7b6c2; }
      .bp3-dark .bp3-html-select .bp3-icon:hover, .bp3-dark
      .bp3-select .bp3-icon:hover{
        color:#f5f8fa; }
  .bp3-html-select.bp3-large::after,
  .bp3-html-select.bp3-large .bp3-icon,
  .bp3-select.bp3-large::after,
  .bp3-select.bp3-large .bp3-icon{
    right:12px;
    top:12px; }
  .bp3-html-select.bp3-fill,
  .bp3-html-select.bp3-fill select,
  .bp3-select.bp3-fill,
  .bp3-select.bp3-fill select{
    width:100%; }
  .bp3-dark .bp3-html-select option, .bp3-dark
  .bp3-select option{
    background-color:#30404d;
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select option:disabled, .bp3-dark
  .bp3-select option:disabled{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-html-select::after, .bp3-dark
  .bp3-select::after{
    color:#a7b6c2; }

.bp3-select::after{
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-style:normal;
  font-weight:400;
  line-height:1;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  content:""; }
.bp3-running-text table, table.bp3-html-table{
  border-spacing:0;
  font-size:14px; }
  .bp3-running-text table th, table.bp3-html-table th,
  .bp3-running-text table td,
  table.bp3-html-table td{
    padding:11px;
    text-align:left;
    vertical-align:top; }
  .bp3-running-text table th, table.bp3-html-table th{
    color:#182026;
    font-weight:600; }
  
  .bp3-running-text table td,
  table.bp3-html-table td{
    color:#182026; }
  .bp3-running-text table tbody tr:first-child th, table.bp3-html-table tbody tr:first-child th,
  .bp3-running-text table tbody tr:first-child td,
  table.bp3-html-table tbody tr:first-child td,
  .bp3-running-text table tfoot tr:first-child th,
  table.bp3-html-table tfoot tr:first-child th,
  .bp3-running-text table tfoot tr:first-child td,
  table.bp3-html-table tfoot tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-running-text table th, .bp3-running-text .bp3-dark table th, .bp3-dark table.bp3-html-table th{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table td, .bp3-running-text .bp3-dark table td, .bp3-dark table.bp3-html-table td{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table tbody tr:first-child th, .bp3-running-text .bp3-dark table tbody tr:first-child th, .bp3-dark table.bp3-html-table tbody tr:first-child th,
  .bp3-dark .bp3-running-text table tbody tr:first-child td,
  .bp3-running-text .bp3-dark table tbody tr:first-child td,
  .bp3-dark table.bp3-html-table tbody tr:first-child td,
  .bp3-dark .bp3-running-text table tfoot tr:first-child th,
  .bp3-running-text .bp3-dark table tfoot tr:first-child th,
  .bp3-dark table.bp3-html-table tfoot tr:first-child th,
  .bp3-dark .bp3-running-text table tfoot tr:first-child td,
  .bp3-running-text .bp3-dark table tfoot tr:first-child td,
  .bp3-dark table.bp3-html-table tfoot tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }

table.bp3-html-table.bp3-html-table-condensed th,
table.bp3-html-table.bp3-html-table-condensed td, table.bp3-html-table.bp3-small th,
table.bp3-html-table.bp3-small td{
  padding-bottom:6px;
  padding-top:6px; }

table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(191, 204, 214, 0.15); }

table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered tbody tr td,
table.bp3-html-table.bp3-html-table-bordered tfoot tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child),
  table.bp3-html-table.bp3-html-table-bordered tfoot tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:none;
          box-shadow:none; }
  table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(191, 204, 214, 0.3);
  cursor:pointer; }

table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(191, 204, 214, 0.4); }

.bp3-dark table.bp3-html-table{ }
  .bp3-dark table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
    background:rgba(92, 112, 128, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td,
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tfoot tr td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }
    .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child),
    .bp3-dark table.bp3-html-table.bp3-html-table-bordered tfoot tr td:not(:first-child){
      -webkit-box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15);
              box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
    -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
    .bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:first-child{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-dark table.bp3-html-table.bp3-interactive tbody tr:hover td{
    background-color:rgba(92, 112, 128, 0.3);
    cursor:pointer; }
  .bp3-dark table.bp3-html-table.bp3-interactive tbody tr:active td{
    background-color:rgba(92, 112, 128, 0.4); }

.bp3-key-combo{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center; }
  .bp3-key-combo > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-key-combo > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-key-combo::before,
  .bp3-key-combo > *{
    margin-right:5px; }
  .bp3-key-combo:empty::before,
  .bp3-key-combo > :last-child{
    margin-right:0; }

.bp3-hotkey-dialog{
  padding-bottom:0;
  top:40px; }
  .bp3-hotkey-dialog .bp3-dialog-body{
    margin:0;
    padding:0; }
  .bp3-hotkey-dialog .bp3-hotkey-label{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1; }

.bp3-hotkey-column{
  margin:auto;
  max-height:80vh;
  overflow-y:auto;
  padding:30px; }
  .bp3-hotkey-column .bp3-heading{
    margin-bottom:20px; }
    .bp3-hotkey-column .bp3-heading:not(:first-child){
      margin-top:40px; }

.bp3-hotkey{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:justify;
      -ms-flex-pack:justify;
          justify-content:space-between;
  margin-left:0;
  margin-right:0; }
  .bp3-hotkey:not(:last-child){
    margin-bottom:10px; }
.bp3-icon{
  display:inline-block;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  vertical-align:text-bottom; }
  .bp3-icon:not(:empty)::before{
    content:"" !important;
    content:unset !important; }
  .bp3-icon > svg{
    display:block; }
    .bp3-icon > svg:not([fill]){
      fill:currentColor; }

.bp3-icon.bp3-intent-primary, .bp3-icon-standard.bp3-intent-primary, .bp3-icon-large.bp3-intent-primary{
  color:#106ba3; }
  .bp3-dark .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-icon-large.bp3-intent-primary{
    color:#48aff0; }

.bp3-icon.bp3-intent-success, .bp3-icon-standard.bp3-intent-success, .bp3-icon-large.bp3-intent-success{
  color:#0d8050; }
  .bp3-dark .bp3-icon.bp3-intent-success, .bp3-dark .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-icon-large.bp3-intent-success{
    color:#3dcc91; }

.bp3-icon.bp3-intent-warning, .bp3-icon-standard.bp3-intent-warning, .bp3-icon-large.bp3-intent-warning{
  color:#bf7326; }
  .bp3-dark .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-icon-large.bp3-intent-warning{
    color:#ffb366; }

.bp3-icon.bp3-intent-danger, .bp3-icon-standard.bp3-intent-danger, .bp3-icon-large.bp3-intent-danger{
  color:#c23030; }
  .bp3-dark .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-icon-large.bp3-intent-danger{
    color:#ff7373; }

span.bp3-icon-standard{
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-style:normal;
  font-weight:400;
  line-height:1;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon-large{
  font-family:"Icons20", sans-serif;
  font-size:20px;
  font-style:normal;
  font-weight:400;
  line-height:1;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon:empty{
  font-family:"Icons20";
  font-size:inherit;
  font-style:normal;
  font-weight:400;
  line-height:1; }
  span.bp3-icon:empty::before{
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased; }

.bp3-icon-add::before{
  content:""; }

.bp3-icon-add-column-left::before{
  content:""; }

.bp3-icon-add-column-right::before{
  content:""; }

.bp3-icon-add-row-bottom::before{
  content:""; }

.bp3-icon-add-row-top::before{
  content:""; }

.bp3-icon-add-to-artifact::before{
  content:""; }

.bp3-icon-add-to-folder::before{
  content:""; }

.bp3-icon-airplane::before{
  content:""; }

.bp3-icon-align-center::before{
  content:""; }

.bp3-icon-align-justify::before{
  content:""; }

.bp3-icon-align-left::before{
  content:""; }

.bp3-icon-align-right::before{
  content:""; }

.bp3-icon-alignment-bottom::before{
  content:""; }

.bp3-icon-alignment-horizontal-center::before{
  content:""; }

.bp3-icon-alignment-left::before{
  content:""; }

.bp3-icon-alignment-right::before{
  content:""; }

.bp3-icon-alignment-top::before{
  content:""; }

.bp3-icon-alignment-vertical-center::before{
  content:""; }

.bp3-icon-annotation::before{
  content:""; }

.bp3-icon-application::before{
  content:""; }

.bp3-icon-applications::before{
  content:""; }

.bp3-icon-archive::before{
  content:""; }

.bp3-icon-arrow-bottom-left::before{
  content:"↙"; }

.bp3-icon-arrow-bottom-right::before{
  content:"↘"; }

.bp3-icon-arrow-down::before{
  content:"↓"; }

.bp3-icon-arrow-left::before{
  content:"←"; }

.bp3-icon-arrow-right::before{
  content:"→"; }

.bp3-icon-arrow-top-left::before{
  content:"↖"; }

.bp3-icon-arrow-top-right::before{
  content:"↗"; }

.bp3-icon-arrow-up::before{
  content:"↑"; }

.bp3-icon-arrows-horizontal::before{
  content:"↔"; }

.bp3-icon-arrows-vertical::before{
  content:"↕"; }

.bp3-icon-asterisk::before{
  content:"*"; }

.bp3-icon-automatic-updates::before{
  content:""; }

.bp3-icon-badge::before{
  content:""; }

.bp3-icon-ban-circle::before{
  content:""; }

.bp3-icon-bank-account::before{
  content:""; }

.bp3-icon-barcode::before{
  content:""; }

.bp3-icon-blank::before{
  content:""; }

.bp3-icon-blocked-person::before{
  content:""; }

.bp3-icon-bold::before{
  content:""; }

.bp3-icon-book::before{
  content:""; }

.bp3-icon-bookmark::before{
  content:""; }

.bp3-icon-box::before{
  content:""; }

.bp3-icon-briefcase::before{
  content:""; }

.bp3-icon-bring-data::before{
  content:""; }

.bp3-icon-build::before{
  content:""; }

.bp3-icon-calculator::before{
  content:""; }

.bp3-icon-calendar::before{
  content:""; }

.bp3-icon-camera::before{
  content:""; }

.bp3-icon-caret-down::before{
  content:"⌄"; }

.bp3-icon-caret-left::before{
  content:"〈"; }

.bp3-icon-caret-right::before{
  content:"〉"; }

.bp3-icon-caret-up::before{
  content:"⌃"; }

.bp3-icon-cell-tower::before{
  content:""; }

.bp3-icon-changes::before{
  content:""; }

.bp3-icon-chart::before{
  content:""; }

.bp3-icon-chat::before{
  content:""; }

.bp3-icon-chevron-backward::before{
  content:""; }

.bp3-icon-chevron-down::before{
  content:""; }

.bp3-icon-chevron-forward::before{
  content:""; }

.bp3-icon-chevron-left::before{
  content:""; }

.bp3-icon-chevron-right::before{
  content:""; }

.bp3-icon-chevron-up::before{
  content:""; }

.bp3-icon-circle::before{
  content:""; }

.bp3-icon-circle-arrow-down::before{
  content:""; }

.bp3-icon-circle-arrow-left::before{
  content:""; }

.bp3-icon-circle-arrow-right::before{
  content:""; }

.bp3-icon-circle-arrow-up::before{
  content:""; }

.bp3-icon-citation::before{
  content:""; }

.bp3-icon-clean::before{
  content:""; }

.bp3-icon-clipboard::before{
  content:""; }

.bp3-icon-cloud::before{
  content:"☁"; }

.bp3-icon-cloud-download::before{
  content:""; }

.bp3-icon-cloud-upload::before{
  content:""; }

.bp3-icon-code::before{
  content:""; }

.bp3-icon-code-block::before{
  content:""; }

.bp3-icon-cog::before{
  content:""; }

.bp3-icon-collapse-all::before{
  content:""; }

.bp3-icon-column-layout::before{
  content:""; }

.bp3-icon-comment::before{
  content:""; }

.bp3-icon-comparison::before{
  content:""; }

.bp3-icon-compass::before{
  content:""; }

.bp3-icon-compressed::before{
  content:""; }

.bp3-icon-confirm::before{
  content:""; }

.bp3-icon-console::before{
  content:""; }

.bp3-icon-contrast::before{
  content:""; }

.bp3-icon-control::before{
  content:""; }

.bp3-icon-credit-card::before{
  content:""; }

.bp3-icon-cross::before{
  content:"✗"; }

.bp3-icon-crown::before{
  content:""; }

.bp3-icon-cube::before{
  content:""; }

.bp3-icon-cube-add::before{
  content:""; }

.bp3-icon-cube-remove::before{
  content:""; }

.bp3-icon-curved-range-chart::before{
  content:""; }

.bp3-icon-cut::before{
  content:""; }

.bp3-icon-dashboard::before{
  content:""; }

.bp3-icon-data-lineage::before{
  content:""; }

.bp3-icon-database::before{
  content:""; }

.bp3-icon-delete::before{
  content:""; }

.bp3-icon-delta::before{
  content:"Δ"; }

.bp3-icon-derive-column::before{
  content:""; }

.bp3-icon-desktop::before{
  content:""; }

.bp3-icon-diagnosis::before{
  content:""; }

.bp3-icon-diagram-tree::before{
  content:""; }

.bp3-icon-direction-left::before{
  content:""; }

.bp3-icon-direction-right::before{
  content:""; }

.bp3-icon-disable::before{
  content:""; }

.bp3-icon-document::before{
  content:""; }

.bp3-icon-document-open::before{
  content:""; }

.bp3-icon-document-share::before{
  content:""; }

.bp3-icon-dollar::before{
  content:"$"; }

.bp3-icon-dot::before{
  content:"•"; }

.bp3-icon-double-caret-horizontal::before{
  content:""; }

.bp3-icon-double-caret-vertical::before{
  content:""; }

.bp3-icon-double-chevron-down::before{
  content:""; }

.bp3-icon-double-chevron-left::before{
  content:""; }

.bp3-icon-double-chevron-right::before{
  content:""; }

.bp3-icon-double-chevron-up::before{
  content:""; }

.bp3-icon-doughnut-chart::before{
  content:""; }

.bp3-icon-download::before{
  content:""; }

.bp3-icon-drag-handle-horizontal::before{
  content:""; }

.bp3-icon-drag-handle-vertical::before{
  content:""; }

.bp3-icon-draw::before{
  content:""; }

.bp3-icon-drive-time::before{
  content:""; }

.bp3-icon-duplicate::before{
  content:""; }

.bp3-icon-edit::before{
  content:"✎"; }

.bp3-icon-eject::before{
  content:"⏏"; }

.bp3-icon-endorsed::before{
  content:""; }

.bp3-icon-envelope::before{
  content:"✉"; }

.bp3-icon-equals::before{
  content:""; }

.bp3-icon-eraser::before{
  content:""; }

.bp3-icon-error::before{
  content:""; }

.bp3-icon-euro::before{
  content:"€"; }

.bp3-icon-exchange::before{
  content:""; }

.bp3-icon-exclude-row::before{
  content:""; }

.bp3-icon-expand-all::before{
  content:""; }

.bp3-icon-export::before{
  content:""; }

.bp3-icon-eye-off::before{
  content:""; }

.bp3-icon-eye-on::before{
  content:""; }

.bp3-icon-eye-open::before{
  content:""; }

.bp3-icon-fast-backward::before{
  content:""; }

.bp3-icon-fast-forward::before{
  content:""; }

.bp3-icon-feed::before{
  content:""; }

.bp3-icon-feed-subscribed::before{
  content:""; }

.bp3-icon-film::before{
  content:""; }

.bp3-icon-filter::before{
  content:""; }

.bp3-icon-filter-keep::before{
  content:""; }

.bp3-icon-filter-list::before{
  content:""; }

.bp3-icon-filter-open::before{
  content:""; }

.bp3-icon-filter-remove::before{
  content:""; }

.bp3-icon-flag::before{
  content:"⚑"; }

.bp3-icon-flame::before{
  content:""; }

.bp3-icon-flash::before{
  content:""; }

.bp3-icon-floppy-disk::before{
  content:""; }

.bp3-icon-flow-branch::before{
  content:""; }

.bp3-icon-flow-end::before{
  content:""; }

.bp3-icon-flow-linear::before{
  content:""; }

.bp3-icon-flow-review::before{
  content:""; }

.bp3-icon-flow-review-branch::before{
  content:""; }

.bp3-icon-flows::before{
  content:""; }

.bp3-icon-folder-close::before{
  content:""; }

.bp3-icon-folder-new::before{
  content:""; }

.bp3-icon-folder-open::before{
  content:""; }

.bp3-icon-folder-shared::before{
  content:""; }

.bp3-icon-folder-shared-open::before{
  content:""; }

.bp3-icon-follower::before{
  content:""; }

.bp3-icon-following::before{
  content:""; }

.bp3-icon-font::before{
  content:""; }

.bp3-icon-fork::before{
  content:""; }

.bp3-icon-form::before{
  content:""; }

.bp3-icon-full-circle::before{
  content:""; }

.bp3-icon-full-stacked-chart::before{
  content:""; }

.bp3-icon-fullscreen::before{
  content:""; }

.bp3-icon-function::before{
  content:""; }

.bp3-icon-gantt-chart::before{
  content:""; }

.bp3-icon-geolocation::before{
  content:""; }

.bp3-icon-geosearch::before{
  content:""; }

.bp3-icon-git-branch::before{
  content:""; }

.bp3-icon-git-commit::before{
  content:""; }

.bp3-icon-git-merge::before{
  content:""; }

.bp3-icon-git-new-branch::before{
  content:""; }

.bp3-icon-git-pull::before{
  content:""; }

.bp3-icon-git-push::before{
  content:""; }

.bp3-icon-git-repo::before{
  content:""; }

.bp3-icon-glass::before{
  content:""; }

.bp3-icon-globe::before{
  content:""; }

.bp3-icon-globe-network::before{
  content:""; }

.bp3-icon-graph::before{
  content:""; }

.bp3-icon-graph-remove::before{
  content:""; }

.bp3-icon-greater-than::before{
  content:""; }

.bp3-icon-greater-than-or-equal-to::before{
  content:""; }

.bp3-icon-grid::before{
  content:""; }

.bp3-icon-grid-view::before{
  content:""; }

.bp3-icon-group-objects::before{
  content:""; }

.bp3-icon-grouped-bar-chart::before{
  content:""; }

.bp3-icon-hand::before{
  content:""; }

.bp3-icon-hand-down::before{
  content:""; }

.bp3-icon-hand-left::before{
  content:""; }

.bp3-icon-hand-right::before{
  content:""; }

.bp3-icon-hand-up::before{
  content:""; }

.bp3-icon-header::before{
  content:""; }

.bp3-icon-header-one::before{
  content:""; }

.bp3-icon-header-two::before{
  content:""; }

.bp3-icon-headset::before{
  content:""; }

.bp3-icon-heart::before{
  content:"♥"; }

.bp3-icon-heart-broken::before{
  content:""; }

.bp3-icon-heat-grid::before{
  content:""; }

.bp3-icon-heatmap::before{
  content:""; }

.bp3-icon-help::before{
  content:"?"; }

.bp3-icon-helper-management::before{
  content:""; }

.bp3-icon-highlight::before{
  content:""; }

.bp3-icon-history::before{
  content:""; }

.bp3-icon-home::before{
  content:"⌂"; }

.bp3-icon-horizontal-bar-chart::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-asc::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-desc::before{
  content:""; }

.bp3-icon-horizontal-distribution::before{
  content:""; }

.bp3-icon-id-number::before{
  content:""; }

.bp3-icon-image-rotate-left::before{
  content:""; }

.bp3-icon-image-rotate-right::before{
  content:""; }

.bp3-icon-import::before{
  content:""; }

.bp3-icon-inbox::before{
  content:""; }

.bp3-icon-inbox-filtered::before{
  content:""; }

.bp3-icon-inbox-geo::before{
  content:""; }

.bp3-icon-inbox-search::before{
  content:""; }

.bp3-icon-inbox-update::before{
  content:""; }

.bp3-icon-info-sign::before{
  content:"ℹ"; }

.bp3-icon-inheritance::before{
  content:""; }

.bp3-icon-inner-join::before{
  content:""; }

.bp3-icon-insert::before{
  content:""; }

.bp3-icon-intersection::before{
  content:""; }

.bp3-icon-ip-address::before{
  content:""; }

.bp3-icon-issue::before{
  content:""; }

.bp3-icon-issue-closed::before{
  content:""; }

.bp3-icon-issue-new::before{
  content:""; }

.bp3-icon-italic::before{
  content:""; }

.bp3-icon-join-table::before{
  content:""; }

.bp3-icon-key::before{
  content:""; }

.bp3-icon-key-backspace::before{
  content:""; }

.bp3-icon-key-command::before{
  content:""; }

.bp3-icon-key-control::before{
  content:""; }

.bp3-icon-key-delete::before{
  content:""; }

.bp3-icon-key-enter::before{
  content:""; }

.bp3-icon-key-escape::before{
  content:""; }

.bp3-icon-key-option::before{
  content:""; }

.bp3-icon-key-shift::before{
  content:""; }

.bp3-icon-key-tab::before{
  content:""; }

.bp3-icon-known-vehicle::before{
  content:""; }

.bp3-icon-lab-test::before{
  content:""; }

.bp3-icon-label::before{
  content:""; }

.bp3-icon-layer::before{
  content:""; }

.bp3-icon-layers::before{
  content:""; }

.bp3-icon-layout::before{
  content:""; }

.bp3-icon-layout-auto::before{
  content:""; }

.bp3-icon-layout-balloon::before{
  content:""; }

.bp3-icon-layout-circle::before{
  content:""; }

.bp3-icon-layout-grid::before{
  content:""; }

.bp3-icon-layout-group-by::before{
  content:""; }

.bp3-icon-layout-hierarchy::before{
  content:""; }

.bp3-icon-layout-linear::before{
  content:""; }

.bp3-icon-layout-skew-grid::before{
  content:""; }

.bp3-icon-layout-sorted-clusters::before{
  content:""; }

.bp3-icon-learning::before{
  content:""; }

.bp3-icon-left-join::before{
  content:""; }

.bp3-icon-less-than::before{
  content:""; }

.bp3-icon-less-than-or-equal-to::before{
  content:""; }

.bp3-icon-lifesaver::before{
  content:""; }

.bp3-icon-lightbulb::before{
  content:""; }

.bp3-icon-link::before{
  content:""; }

.bp3-icon-list::before{
  content:"☰"; }

.bp3-icon-list-columns::before{
  content:""; }

.bp3-icon-list-detail-view::before{
  content:""; }

.bp3-icon-locate::before{
  content:""; }

.bp3-icon-lock::before{
  content:""; }

.bp3-icon-log-in::before{
  content:""; }

.bp3-icon-log-out::before{
  content:""; }

.bp3-icon-manual::before{
  content:""; }

.bp3-icon-manually-entered-data::before{
  content:""; }

.bp3-icon-map::before{
  content:""; }

.bp3-icon-map-create::before{
  content:""; }

.bp3-icon-map-marker::before{
  content:""; }

.bp3-icon-maximize::before{
  content:""; }

.bp3-icon-media::before{
  content:""; }

.bp3-icon-menu::before{
  content:""; }

.bp3-icon-menu-closed::before{
  content:""; }

.bp3-icon-menu-open::before{
  content:""; }

.bp3-icon-merge-columns::before{
  content:""; }

.bp3-icon-merge-links::before{
  content:""; }

.bp3-icon-minimize::before{
  content:""; }

.bp3-icon-minus::before{
  content:"−"; }

.bp3-icon-mobile-phone::before{
  content:""; }

.bp3-icon-mobile-video::before{
  content:""; }

.bp3-icon-moon::before{
  content:""; }

.bp3-icon-more::before{
  content:""; }

.bp3-icon-mountain::before{
  content:""; }

.bp3-icon-move::before{
  content:""; }

.bp3-icon-mugshot::before{
  content:""; }

.bp3-icon-multi-select::before{
  content:""; }

.bp3-icon-music::before{
  content:""; }

.bp3-icon-new-drawing::before{
  content:""; }

.bp3-icon-new-grid-item::before{
  content:""; }

.bp3-icon-new-layer::before{
  content:""; }

.bp3-icon-new-layers::before{
  content:""; }

.bp3-icon-new-link::before{
  content:""; }

.bp3-icon-new-object::before{
  content:""; }

.bp3-icon-new-person::before{
  content:""; }

.bp3-icon-new-prescription::before{
  content:""; }

.bp3-icon-new-text-box::before{
  content:""; }

.bp3-icon-ninja::before{
  content:""; }

.bp3-icon-not-equal-to::before{
  content:""; }

.bp3-icon-notifications::before{
  content:""; }

.bp3-icon-notifications-updated::before{
  content:""; }

.bp3-icon-numbered-list::before{
  content:""; }

.bp3-icon-numerical::before{
  content:""; }

.bp3-icon-office::before{
  content:""; }

.bp3-icon-offline::before{
  content:""; }

.bp3-icon-oil-field::before{
  content:""; }

.bp3-icon-one-column::before{
  content:""; }

.bp3-icon-outdated::before{
  content:""; }

.bp3-icon-page-layout::before{
  content:""; }

.bp3-icon-panel-stats::before{
  content:""; }

.bp3-icon-panel-table::before{
  content:""; }

.bp3-icon-paperclip::before{
  content:""; }

.bp3-icon-paragraph::before{
  content:""; }

.bp3-icon-path::before{
  content:""; }

.bp3-icon-path-search::before{
  content:""; }

.bp3-icon-pause::before{
  content:""; }

.bp3-icon-people::before{
  content:""; }

.bp3-icon-percentage::before{
  content:""; }

.bp3-icon-person::before{
  content:""; }

.bp3-icon-phone::before{
  content:"☎"; }

.bp3-icon-pie-chart::before{
  content:""; }

.bp3-icon-pin::before{
  content:""; }

.bp3-icon-pivot::before{
  content:""; }

.bp3-icon-pivot-table::before{
  content:""; }

.bp3-icon-play::before{
  content:""; }

.bp3-icon-plus::before{
  content:"+"; }

.bp3-icon-polygon-filter::before{
  content:""; }

.bp3-icon-power::before{
  content:""; }

.bp3-icon-predictive-analysis::before{
  content:""; }

.bp3-icon-prescription::before{
  content:""; }

.bp3-icon-presentation::before{
  content:""; }

.bp3-icon-print::before{
  content:"⎙"; }

.bp3-icon-projects::before{
  content:""; }

.bp3-icon-properties::before{
  content:""; }

.bp3-icon-property::before{
  content:""; }

.bp3-icon-publish-function::before{
  content:""; }

.bp3-icon-pulse::before{
  content:""; }

.bp3-icon-random::before{
  content:""; }

.bp3-icon-record::before{
  content:""; }

.bp3-icon-redo::before{
  content:""; }

.bp3-icon-refresh::before{
  content:""; }

.bp3-icon-regression-chart::before{
  content:""; }

.bp3-icon-remove::before{
  content:""; }

.bp3-icon-remove-column::before{
  content:""; }

.bp3-icon-remove-column-left::before{
  content:""; }

.bp3-icon-remove-column-right::before{
  content:""; }

.bp3-icon-remove-row-bottom::before{
  content:""; }

.bp3-icon-remove-row-top::before{
  content:""; }

.bp3-icon-repeat::before{
  content:""; }

.bp3-icon-reset::before{
  content:""; }

.bp3-icon-resolve::before{
  content:""; }

.bp3-icon-rig::before{
  content:""; }

.bp3-icon-right-join::before{
  content:""; }

.bp3-icon-ring::before{
  content:""; }

.bp3-icon-rotate-document::before{
  content:""; }

.bp3-icon-rotate-page::before{
  content:""; }

.bp3-icon-satellite::before{
  content:""; }

.bp3-icon-saved::before{
  content:""; }

.bp3-icon-scatter-plot::before{
  content:""; }

.bp3-icon-search::before{
  content:""; }

.bp3-icon-search-around::before{
  content:""; }

.bp3-icon-search-template::before{
  content:""; }

.bp3-icon-search-text::before{
  content:""; }

.bp3-icon-segmented-control::before{
  content:""; }

.bp3-icon-select::before{
  content:""; }

.bp3-icon-selection::before{
  content:"⦿"; }

.bp3-icon-send-to::before{
  content:""; }

.bp3-icon-send-to-graph::before{
  content:""; }

.bp3-icon-send-to-map::before{
  content:""; }

.bp3-icon-series-add::before{
  content:""; }

.bp3-icon-series-configuration::before{
  content:""; }

.bp3-icon-series-derived::before{
  content:""; }

.bp3-icon-series-filtered::before{
  content:""; }

.bp3-icon-series-search::before{
  content:""; }

.bp3-icon-settings::before{
  content:""; }

.bp3-icon-share::before{
  content:""; }

.bp3-icon-shield::before{
  content:""; }

.bp3-icon-shop::before{
  content:""; }

.bp3-icon-shopping-cart::before{
  content:""; }

.bp3-icon-signal-search::before{
  content:""; }

.bp3-icon-sim-card::before{
  content:""; }

.bp3-icon-slash::before{
  content:""; }

.bp3-icon-small-cross::before{
  content:""; }

.bp3-icon-small-minus::before{
  content:""; }

.bp3-icon-small-plus::before{
  content:""; }

.bp3-icon-small-tick::before{
  content:""; }

.bp3-icon-snowflake::before{
  content:""; }

.bp3-icon-social-media::before{
  content:""; }

.bp3-icon-sort::before{
  content:""; }

.bp3-icon-sort-alphabetical::before{
  content:""; }

.bp3-icon-sort-alphabetical-desc::before{
  content:""; }

.bp3-icon-sort-asc::before{
  content:""; }

.bp3-icon-sort-desc::before{
  content:""; }

.bp3-icon-sort-numerical::before{
  content:""; }

.bp3-icon-sort-numerical-desc::before{
  content:""; }

.bp3-icon-split-columns::before{
  content:""; }

.bp3-icon-square::before{
  content:""; }

.bp3-icon-stacked-chart::before{
  content:""; }

.bp3-icon-star::before{
  content:"★"; }

.bp3-icon-star-empty::before{
  content:"☆"; }

.bp3-icon-step-backward::before{
  content:""; }

.bp3-icon-step-chart::before{
  content:""; }

.bp3-icon-step-forward::before{
  content:""; }

.bp3-icon-stop::before{
  content:""; }

.bp3-icon-stopwatch::before{
  content:""; }

.bp3-icon-strikethrough::before{
  content:""; }

.bp3-icon-style::before{
  content:""; }

.bp3-icon-swap-horizontal::before{
  content:""; }

.bp3-icon-swap-vertical::before{
  content:""; }

.bp3-icon-symbol-circle::before{
  content:""; }

.bp3-icon-symbol-cross::before{
  content:""; }

.bp3-icon-symbol-diamond::before{
  content:""; }

.bp3-icon-symbol-square::before{
  content:""; }

.bp3-icon-symbol-triangle-down::before{
  content:""; }

.bp3-icon-symbol-triangle-up::before{
  content:""; }

.bp3-icon-tag::before{
  content:""; }

.bp3-icon-take-action::before{
  content:""; }

.bp3-icon-taxi::before{
  content:""; }

.bp3-icon-text-highlight::before{
  content:""; }

.bp3-icon-th::before{
  content:""; }

.bp3-icon-th-derived::before{
  content:""; }

.bp3-icon-th-disconnect::before{
  content:""; }

.bp3-icon-th-filtered::before{
  content:""; }

.bp3-icon-th-list::before{
  content:""; }

.bp3-icon-thumbs-down::before{
  content:""; }

.bp3-icon-thumbs-up::before{
  content:""; }

.bp3-icon-tick::before{
  content:"✓"; }

.bp3-icon-tick-circle::before{
  content:""; }

.bp3-icon-time::before{
  content:"⏲"; }

.bp3-icon-timeline-area-chart::before{
  content:""; }

.bp3-icon-timeline-bar-chart::before{
  content:""; }

.bp3-icon-timeline-events::before{
  content:""; }

.bp3-icon-timeline-line-chart::before{
  content:""; }

.bp3-icon-tint::before{
  content:""; }

.bp3-icon-torch::before{
  content:""; }

.bp3-icon-tractor::before{
  content:""; }

.bp3-icon-train::before{
  content:""; }

.bp3-icon-translate::before{
  content:""; }

.bp3-icon-trash::before{
  content:""; }

.bp3-icon-tree::before{
  content:""; }

.bp3-icon-trending-down::before{
  content:""; }

.bp3-icon-trending-up::before{
  content:""; }

.bp3-icon-truck::before{
  content:""; }

.bp3-icon-two-columns::before{
  content:""; }

.bp3-icon-unarchive::before{
  content:""; }

.bp3-icon-underline::before{
  content:"⎁"; }

.bp3-icon-undo::before{
  content:"⎌"; }

.bp3-icon-ungroup-objects::before{
  content:""; }

.bp3-icon-unknown-vehicle::before{
  content:""; }

.bp3-icon-unlock::before{
  content:""; }

.bp3-icon-unpin::before{
  content:""; }

.bp3-icon-unresolve::before{
  content:""; }

.bp3-icon-updated::before{
  content:""; }

.bp3-icon-upload::before{
  content:""; }

.bp3-icon-user::before{
  content:""; }

.bp3-icon-variable::before{
  content:""; }

.bp3-icon-vertical-bar-chart-asc::before{
  content:""; }

.bp3-icon-vertical-bar-chart-desc::before{
  content:""; }

.bp3-icon-vertical-distribution::before{
  content:""; }

.bp3-icon-video::before{
  content:""; }

.bp3-icon-volume-down::before{
  content:""; }

.bp3-icon-volume-off::before{
  content:""; }

.bp3-icon-volume-up::before{
  content:""; }

.bp3-icon-walk::before{
  content:""; }

.bp3-icon-warning-sign::before{
  content:""; }

.bp3-icon-waterfall-chart::before{
  content:""; }

.bp3-icon-widget::before{
  content:""; }

.bp3-icon-widget-button::before{
  content:""; }

.bp3-icon-widget-footer::before{
  content:""; }

.bp3-icon-widget-header::before{
  content:""; }

.bp3-icon-wrench::before{
  content:""; }

.bp3-icon-zoom-in::before{
  content:""; }

.bp3-icon-zoom-out::before{
  content:""; }

.bp3-icon-zoom-to-fit::before{
  content:""; }
.bp3-submenu > .bp3-popover-wrapper{
  display:block; }

.bp3-submenu .bp3-popover-target{
  display:block; }
  .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{ }

.bp3-submenu.bp3-popover{
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0 5px; }
  .bp3-submenu.bp3-popover > .bp3-popover-content{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-submenu.bp3-popover, .bp3-submenu.bp3-popover.bp3-dark{
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-dark .bp3-submenu.bp3-popover > .bp3-popover-content, .bp3-submenu.bp3-popover.bp3-dark > .bp3-popover-content{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
.bp3-menu{
  background:#ffffff;
  border-radius:3px;
  color:#182026;
  list-style:none;
  margin:0;
  min-width:180px;
  padding:5px;
  text-align:left; }

.bp3-menu-divider{
  border-top:1px solid rgba(16, 22, 26, 0.15);
  display:block;
  margin:5px; }
  .bp3-dark .bp3-menu-divider{
    border-top-color:rgba(255, 255, 255, 0.15); }

.bp3-menu-item{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  border-radius:2px;
  color:inherit;
  line-height:20px;
  padding:5px 7px;
  text-decoration:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-menu-item > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-menu-item > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-menu-item::before,
  .bp3-menu-item > *{
    margin-right:7px; }
  .bp3-menu-item:empty::before,
  .bp3-menu-item > :last-child{
    margin-right:0; }
  .bp3-menu-item > .bp3-fill{
    word-break:break-word; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    background-color:rgba(167, 182, 194, 0.3);
    cursor:pointer;
    text-decoration:none; }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
  .bp3-dark .bp3-menu-item{
    color:inherit; }
    .bp3-dark .bp3-menu-item:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
      background-color:rgba(138, 155, 168, 0.15);
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-disabled{
      background-color:inherit;
      color:rgba(167, 182, 194, 0.6); }
  .bp3-menu-item.bp3-intent-primary{
    color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-primary::before, .bp3-menu-item.bp3-intent-primary::after,
    .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
      color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary.bp3-active{
      background-color:#137cbd; }
    .bp3-menu-item.bp3-intent-primary:active{
      background-color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary:active, .bp3-menu-item.bp3-intent-primary:active::before, .bp3-menu-item.bp3-intent-primary:active::after,
    .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-menu-item.bp3-intent-primary.bp3-active::after,
    .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-success{
    color:#0d8050; }
    .bp3-menu-item.bp3-intent-success .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-success::before, .bp3-menu-item.bp3-intent-success::after,
    .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
      color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success.bp3-active{
      background-color:#0f9960; }
    .bp3-menu-item.bp3-intent-success:active{
      background-color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-menu-item.bp3-intent-success:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success:active, .bp3-menu-item.bp3-intent-success:active::before, .bp3-menu-item.bp3-intent-success:active::after,
    .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-menu-item.bp3-intent-success.bp3-active::after,
    .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-warning{
    color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-warning::before, .bp3-menu-item.bp3-intent-warning::after,
    .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
      color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning.bp3-active{
      background-color:#d9822b; }
    .bp3-menu-item.bp3-intent-warning:active{
      background-color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning:active, .bp3-menu-item.bp3-intent-warning:active::before, .bp3-menu-item.bp3-intent-warning:active::after,
    .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-menu-item.bp3-intent-warning.bp3-active::after,
    .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-danger{
    color:#c23030; }
    .bp3-menu-item.bp3-intent-danger .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-danger::before, .bp3-menu-item.bp3-intent-danger::after,
    .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
      color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger.bp3-active{
      background-color:#db3737; }
    .bp3-menu-item.bp3-intent-danger:active{
      background-color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger:active, .bp3-menu-item.bp3-intent-danger:active::before, .bp3-menu-item.bp3-intent-danger:active::after,
    .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-menu-item.bp3-intent-danger.bp3-active::after,
    .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item::before{
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-style:normal;
    font-weight:400;
    line-height:1;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    margin-right:7px; }
  .bp3-menu-item::before,
  .bp3-menu-item > .bp3-icon{
    color:#5c7080;
    margin-top:2px; }
  .bp3-menu-item .bp3-menu-item-label{
    color:#5c7080; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    color:inherit; }
  .bp3-menu-item.bp3-active, .bp3-menu-item:active{
    background-color:rgba(115, 134, 148, 0.3); }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit !important;
    color:rgba(92, 112, 128, 0.6) !important;
    cursor:not-allowed !important;
    outline:none !important; }
    .bp3-menu-item.bp3-disabled::before,
    .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-large .bp3-menu-item{
    font-size:16px;
    line-height:22px;
    padding:9px 7px; }
    .bp3-large .bp3-menu-item .bp3-icon{
      margin-top:3px; }
    .bp3-large .bp3-menu-item::before{
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-style:normal;
      font-weight:400;
      line-height:1;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      margin-right:10px;
      margin-top:1px; }

button.bp3-menu-item{
  background:none;
  border:none;
  text-align:left;
  width:100%; }
.bp3-menu-header{
  border-top:1px solid rgba(16, 22, 26, 0.15);
  display:block;
  margin:5px;
  cursor:default;
  padding-left:2px; }
  .bp3-dark .bp3-menu-header{
    border-top-color:rgba(255, 255, 255, 0.15); }
  .bp3-menu-header:first-of-type{
    border-top:none; }
  .bp3-menu-header > h6{
    color:#182026;
    font-weight:600;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    line-height:17px;
    margin:0;
    padding:10px 7px 0 1px; }
    .bp3-dark .bp3-menu-header > h6{
      color:#f5f8fa; }
  .bp3-menu-header:first-of-type > h6{
    padding-top:0; }
  .bp3-large .bp3-menu-header > h6{
    font-size:18px;
    padding-bottom:5px;
    padding-top:15px; }
  .bp3-large .bp3-menu-header:first-of-type > h6{
    padding-top:0; }

.bp3-dark .bp3-menu{
  background:#30404d;
  color:#f5f8fa; }

.bp3-dark .bp3-menu-item{ }
  .bp3-dark .bp3-menu-item.bp3-intent-primary{
    color:#48aff0; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-icon{
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary::before, .bp3-dark .bp3-menu-item.bp3-intent-primary::after,
    .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
      color:#48aff0; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active{
      background-color:#137cbd; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary:active{
      background-color:#106ba3; }
    .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
    .bp3-dark .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
    .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label,
    .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary:active, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-dark .bp3-menu-item.bp3-intent-success{
    color:#3dcc91; }
    .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-icon{
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-intent-success::before, .bp3-dark .bp3-menu-item.bp3-intent-success::after,
    .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
      color:#3dcc91; }
    .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active{
      background-color:#0f9960; }
    .bp3-dark .bp3-menu-item.bp3-intent-success:active{
      background-color:#0d8050; }
    .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
    .bp3-dark .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
    .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label,
    .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success:active, .bp3-dark .bp3-menu-item.bp3-intent-success:active::before, .bp3-dark .bp3-menu-item.bp3-intent-success:active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning{
    color:#ffb366; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-icon{
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning::before, .bp3-dark .bp3-menu-item.bp3-intent-warning::after,
    .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
      color:#ffb366; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active{
      background-color:#d9822b; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning:active{
      background-color:#bf7326; }
    .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
    .bp3-dark .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
    .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label,
    .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning:active, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger{
    color:#ff7373; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-icon{
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger::before, .bp3-dark .bp3-menu-item.bp3-intent-danger::after,
    .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
      color:#ff7373; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active{
      background-color:#db3737; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger:active{
      background-color:#c23030; }
    .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
    .bp3-dark .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
    .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label,
    .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger:active, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::after,
    .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-dark .bp3-menu-item::before,
  .bp3-dark .bp3-menu-item > .bp3-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-menu-item .bp3-menu-item-label{
    color:#a7b6c2; }
  .bp3-dark .bp3-menu-item.bp3-active, .bp3-dark .bp3-menu-item:active{
    background-color:rgba(138, 155, 168, 0.3); }
  .bp3-dark .bp3-menu-item.bp3-disabled{
    color:rgba(167, 182, 194, 0.6) !important; }
    .bp3-dark .bp3-menu-item.bp3-disabled::before,
    .bp3-dark .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-dark .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(167, 182, 194, 0.6) !important; }

.bp3-dark .bp3-menu-divider,
.bp3-dark .bp3-menu-header{
  border-color:rgba(255, 255, 255, 0.15); }

.bp3-dark .bp3-menu-header > h6{
  color:#f5f8fa; }

.bp3-label .bp3-menu{
  margin-top:5px; }
.bp3-navbar{
  background-color:#ffffff;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  height:50px;
  padding:0 15px;
  position:relative;
  width:100%;
  z-index:10; }
  .bp3-navbar.bp3-dark,
  .bp3-dark .bp3-navbar{
    background-color:#394b59; }
  .bp3-navbar.bp3-dark{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-navbar{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-navbar.bp3-fixed-top{
    left:0;
    position:fixed;
    right:0;
    top:0; }

.bp3-navbar-heading{
  font-size:16px;
  margin-right:15px; }

.bp3-navbar-group{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  height:50px; }
  .bp3-navbar-group.bp3-align-left{
    float:left; }
  .bp3-navbar-group.bp3-align-right{
    float:right; }

.bp3-navbar-divider{
  border-left:1px solid rgba(16, 22, 26, 0.15);
  height:20px;
  margin:0 10px; }
  .bp3-dark .bp3-navbar-divider{
    border-left-color:rgba(255, 255, 255, 0.15); }
.bp3-non-ideal-state{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  height:100%;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  text-align:center;
  width:100%; }
  .bp3-non-ideal-state > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-non-ideal-state > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-non-ideal-state::before,
  .bp3-non-ideal-state > *{
    margin-bottom:20px; }
  .bp3-non-ideal-state:empty::before,
  .bp3-non-ideal-state > :last-child{
    margin-bottom:0; }
  .bp3-non-ideal-state > *{
    max-width:400px; }

.bp3-non-ideal-state-visual{
  color:rgba(92, 112, 128, 0.6);
  font-size:60px; }
  .bp3-dark .bp3-non-ideal-state-visual{
    color:rgba(167, 182, 194, 0.6); }

.bp3-overflow-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:nowrap;
      flex-wrap:nowrap;
  min-width:0; }

.bp3-overflow-list-spacer{
  -ms-flex-negative:1;
      flex-shrink:1;
  width:1px; }

body.bp3-overlay-open{
  overflow:hidden; }

.bp3-overlay{
  bottom:0;
  left:0;
  position:static;
  right:0;
  top:0;
  z-index:20; }
  .bp3-overlay:not(.bp3-overlay-open){
    pointer-events:none; }
  .bp3-overlay.bp3-overlay-container{
    overflow:hidden;
    position:fixed; }
    .bp3-overlay.bp3-overlay-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-scroll-container{
    overflow:auto;
    position:fixed; }
    .bp3-overlay.bp3-overlay-scroll-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-inline{
    display:inline;
    overflow:visible; }

.bp3-overlay-content{
  position:fixed;
  z-index:20; }
  .bp3-overlay-inline .bp3-overlay-content,
  .bp3-overlay-scroll-container .bp3-overlay-content{
    position:absolute; }

.bp3-overlay-backdrop{
  bottom:0;
  left:0;
  position:fixed;
  right:0;
  top:0;
  opacity:1;
  background-color:rgba(16, 22, 26, 0.7);
  overflow:auto;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none;
  z-index:20; }
  .bp3-overlay-backdrop.bp3-overlay-enter, .bp3-overlay-backdrop.bp3-overlay-appear{
    opacity:0; }
  .bp3-overlay-backdrop.bp3-overlay-enter-active, .bp3-overlay-backdrop.bp3-overlay-appear-active{
    opacity:1;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-overlay-backdrop.bp3-overlay-exit{
    opacity:1; }
  .bp3-overlay-backdrop.bp3-overlay-exit-active{
    opacity:0;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-overlay-backdrop:focus{
    outline:none; }
  .bp3-overlay-inline .bp3-overlay-backdrop{
    position:absolute; }
.bp3-panel-stack{
  overflow:hidden;
  position:relative; }

.bp3-panel-stack-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  height:30px;
  z-index:1; }
  .bp3-dark .bp3-panel-stack-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack-header > span{
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1; }
  .bp3-panel-stack-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack-view{
  bottom:0;
  left:0;
  position:absolute;
  right:0;
  top:0;
  background-color:#ffffff;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  overflow-y:auto;
  z-index:1; }
  .bp3-dark .bp3-panel-stack-view{
    background-color:#30404d; }
  .bp3-panel-stack-view:nth-last-child(n + 4){
    display:none; }

.bp3-panel-stack-push .bp3-panel-stack-enter, .bp3-panel-stack-push .bp3-panel-stack-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack-push .bp3-panel-stack-enter-active, .bp3-panel-stack-push .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack-push .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-push .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack-pop .bp3-panel-stack-enter, .bp3-panel-stack-pop .bp3-panel-stack-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter-active, .bp3-panel-stack-pop .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack-pop .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-pop .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }
.bp3-panel-stack2{
  overflow:hidden;
  position:relative; }

.bp3-panel-stack2-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  height:30px;
  z-index:1; }
  .bp3-dark .bp3-panel-stack2-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack2-header > span{
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1; }
  .bp3-panel-stack2-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack2-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack2-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack2-view{
  bottom:0;
  left:0;
  position:absolute;
  right:0;
  top:0;
  background-color:#ffffff;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  overflow-y:auto;
  z-index:1; }
  .bp3-dark .bp3-panel-stack2-view{
    background-color:#30404d; }
  .bp3-panel-stack2-view:nth-last-child(n + 4){
    display:none; }

.bp3-panel-stack2-push .bp3-panel-stack2-enter, .bp3-panel-stack2-push .bp3-panel-stack2-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack2-push .bp3-panel-stack2-enter-active, .bp3-panel-stack2-push .bp3-panel-stack2-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack2-push .bp3-panel-stack2-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack2-push .bp3-panel-stack2-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack2-pop .bp3-panel-stack2-enter, .bp3-panel-stack2-pop .bp3-panel-stack2-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack2-pop .bp3-panel-stack2-enter-active, .bp3-panel-stack2-pop .bp3-panel-stack2-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack2-pop .bp3-panel-stack2-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack2-pop .bp3-panel-stack2-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }
.bp3-popover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1);
  border-radius:3px;
  display:inline-block;
  z-index:20; }
  .bp3-popover .bp3-popover-arrow{
    height:30px;
    position:absolute;
    width:30px; }
    .bp3-popover .bp3-popover-arrow::before{
      height:20px;
      margin:5px;
      width:20px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover{
    margin-bottom:17px;
    margin-top:-17px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
      bottom:-11px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover{
    margin-left:17px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
      left:-11px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover{
    margin-top:17px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
      top:-11px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover{
    margin-left:-17px;
    margin-right:17px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
      right:-11px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-popover > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-popover > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
    top:-0.3934px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
    right:-0.3934px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
    left:-0.3934px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
    bottom:-0.3934px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-popover .bp3-popover-content{
    background:#ffffff;
    color:inherit; }
  .bp3-popover .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-popover .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-popover .bp3-popover-arrow-fill{
    fill:#ffffff; }
  .bp3-popover-enter > .bp3-popover, .bp3-popover-appear > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3); }
  .bp3-popover-enter-active > .bp3-popover, .bp3-popover-appear-active > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-popover-exit > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-popover .bp3-popover-content{
    border-radius:3px;
    position:relative; }
  .bp3-popover.bp3-popover-content-sizing .bp3-popover-content{
    max-width:350px;
    padding:20px; }
  .bp3-popover-target + .bp3-overlay .bp3-popover.bp3-popover-content-sizing{
    width:350px; }
  .bp3-popover.bp3-minimal{
    margin:0 !important; }
    .bp3-popover.bp3-minimal .bp3-popover-arrow{
      display:none; }
    .bp3-popover.bp3-minimal.bp3-popover{
      -webkit-transform:scale(1);
              transform:scale(1); }
      .bp3-popover-enter > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-enter-active > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-delay:0;
                transition-delay:0;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
      .bp3-popover-exit > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-exit-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-delay:0;
                transition-delay:0;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-popover.bp3-dark,
  .bp3-dark .bp3-popover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-popover .bp3-popover-content{
      background:#30404d;
      color:inherit; }
    .bp3-popover.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-popover .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-popover .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-popover.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-popover .bp3-popover-arrow-fill{
      fill:#30404d; }

.bp3-popover-arrow::before{
  border-radius:2px;
  content:"";
  display:block;
  position:absolute;
  -webkit-transform:rotate(45deg);
          transform:rotate(45deg); }

.bp3-tether-pinned .bp3-popover-arrow{
  display:none; }

.bp3-popover-backdrop{
  background:rgba(255, 255, 255, 0); }

.bp3-transition-container{
  opacity:1;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  z-index:20; }
  .bp3-transition-container.bp3-popover-enter, .bp3-transition-container.bp3-popover-appear{
    opacity:0; }
  .bp3-transition-container.bp3-popover-enter-active, .bp3-transition-container.bp3-popover-appear-active{
    opacity:1;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-transition-container.bp3-popover-exit{
    opacity:1; }
  .bp3-transition-container.bp3-popover-exit-active{
    opacity:0;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-transition-container:focus{
    outline:none; }
  .bp3-transition-container.bp3-popover-leave .bp3-popover-content{
    pointer-events:none; }
  .bp3-transition-container[data-x-out-of-boundaries]{
    display:none; }

span.bp3-popover-target{
  display:inline-block; }

.bp3-popover-wrapper.bp3-fill{
  width:100%; }

.bp3-portal{
  left:0;
  position:absolute;
  right:0;
  top:0; }
@-webkit-keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }
@keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }

.bp3-progress-bar{
  background:rgba(92, 112, 128, 0.2);
  border-radius:40px;
  display:block;
  height:8px;
  overflow:hidden;
  position:relative;
  width:100%; }
  .bp3-progress-bar .bp3-progress-meter{
    background:linear-gradient(-45deg, rgba(255, 255, 255, 0.2) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.2) 50%, rgba(255, 255, 255, 0.2) 75%, transparent 75%);
    background-color:rgba(92, 112, 128, 0.8);
    background-size:30px 30px;
    border-radius:40px;
    height:100%;
    position:absolute;
    -webkit-transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    width:100%; }
  .bp3-progress-bar:not(.bp3-no-animation):not(.bp3-no-stripes) .bp3-progress-meter{
    animation:linear-progress-bar-stripes 300ms linear infinite reverse; }
  .bp3-progress-bar.bp3-no-stripes .bp3-progress-meter{
    background-image:none; }

.bp3-dark .bp3-progress-bar{
  background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-progress-bar .bp3-progress-meter{
    background-color:#8a9ba8; }

.bp3-progress-bar.bp3-intent-primary .bp3-progress-meter{
  background-color:#137cbd; }

.bp3-progress-bar.bp3-intent-success .bp3-progress-meter{
  background-color:#0f9960; }

.bp3-progress-bar.bp3-intent-warning .bp3-progress-meter{
  background-color:#d9822b; }

.bp3-progress-bar.bp3-intent-danger .bp3-progress-meter{
  background-color:#db3737; }
@-webkit-keyframes skeleton-glow{
  from{
    background:rgba(206, 217, 224, 0.2);
    border-color:rgba(206, 217, 224, 0.2); }
  to{
    background:rgba(92, 112, 128, 0.2);
    border-color:rgba(92, 112, 128, 0.2); } }
@keyframes skeleton-glow{
  from{
    background:rgba(206, 217, 224, 0.2);
    border-color:rgba(206, 217, 224, 0.2); }
  to{
    background:rgba(92, 112, 128, 0.2);
    border-color:rgba(92, 112, 128, 0.2); } }
.bp3-skeleton{
  -webkit-animation:1000ms linear infinite alternate skeleton-glow;
          animation:1000ms linear infinite alternate skeleton-glow;
  background:rgba(206, 217, 224, 0.2);
  background-clip:padding-box !important;
  border-color:rgba(206, 217, 224, 0.2) !important;
  border-radius:2px;
  -webkit-box-shadow:none !important;
          box-shadow:none !important;
  color:transparent !important;
  cursor:default;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-skeleton::before, .bp3-skeleton::after,
  .bp3-skeleton *{
    visibility:hidden !important; }
.bp3-slider{
  height:40px;
  min-width:150px;
  width:100%;
  cursor:default;
  outline:none;
  position:relative;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-slider:hover{
    cursor:pointer; }
  .bp3-slider:active{
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-slider.bp3-disabled{
    cursor:not-allowed;
    opacity:0.5; }
  .bp3-slider.bp3-slider-unlabeled{
    height:16px; }

.bp3-slider-track,
.bp3-slider-progress{
  height:6px;
  left:0;
  right:0;
  top:5px;
  position:absolute; }

.bp3-slider-track{
  border-radius:3px;
  overflow:hidden; }

.bp3-slider-progress{
  background:rgba(92, 112, 128, 0.2); }
  .bp3-dark .bp3-slider-progress{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-slider-progress.bp3-intent-primary{
    background-color:#137cbd; }
  .bp3-slider-progress.bp3-intent-success{
    background-color:#0f9960; }
  .bp3-slider-progress.bp3-intent-warning{
    background-color:#d9822b; }
  .bp3-slider-progress.bp3-intent-danger{
    background-color:#db3737; }

.bp3-slider-handle{
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  color:#182026;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
  cursor:pointer;
  height:16px;
  left:0;
  position:absolute;
  top:0;
  width:16px; }
  .bp3-slider-handle:hover{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
  .bp3-slider-handle:active, .bp3-slider-handle.bp3-active{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-slider-handle:disabled, .bp3-slider-handle.bp3-disabled{
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    outline:none; }
    .bp3-slider-handle:disabled.bp3-active, .bp3-slider-handle:disabled.bp3-active:hover, .bp3-slider-handle.bp3-disabled.bp3-active, .bp3-slider-handle.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }
  .bp3-slider-handle:focus{
    z-index:1; }
  .bp3-slider-handle:hover{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
    cursor:-webkit-grab;
    cursor:grab;
    z-index:2; }
  .bp3-slider-handle.bp3-active{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-disabled .bp3-slider-handle{
    background:#bfccd6;
    -webkit-box-shadow:none;
            box-shadow:none;
    pointer-events:none; }
  .bp3-dark .bp3-slider-handle{
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover, .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover{
      background-color:#30404d;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#202b33;
      background-image:none;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-slider-handle:disabled, .bp3-dark .bp3-slider-handle.bp3-disabled{
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-slider-handle:disabled.bp3-active, .bp3-dark .bp3-slider-handle.bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-slider-handle .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-slider-handle, .bp3-dark .bp3-slider-handle:hover{
      background-color:#394b59; }
    .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#293742; }
  .bp3-dark .bp3-disabled .bp3-slider-handle{
    background:#5c7080;
    border-color:#5c7080;
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-slider-handle .bp3-slider-label{
    background:#394b59;
    border-radius:3px;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
    color:#f5f8fa;
    margin-left:8px; }
    .bp3-dark .bp3-slider-handle .bp3-slider-label{
      background:#e1e8ed;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
      color:#394b59; }
    .bp3-disabled .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-slider-handle.bp3-start, .bp3-slider-handle.bp3-end{
    width:8px; }
  .bp3-slider-handle.bp3-start{
    border-bottom-right-radius:0;
    border-top-right-radius:0; }
  .bp3-slider-handle.bp3-end{
    border-bottom-left-radius:0;
    border-top-left-radius:0;
    margin-left:8px; }
    .bp3-slider-handle.bp3-end .bp3-slider-label{
      margin-left:0; }

.bp3-slider-label{
  -webkit-transform:translate(-50%, 20px);
          transform:translate(-50%, 20px);
  display:inline-block;
  font-size:12px;
  line-height:1;
  padding:2px 5px;
  position:absolute;
  vertical-align:top; }

.bp3-slider.bp3-vertical{
  height:150px;
  min-width:40px;
  width:40px; }
  .bp3-slider.bp3-vertical .bp3-slider-track,
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    bottom:0;
    height:auto;
    left:5px;
    top:0;
    width:6px; }
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-label{
    -webkit-transform:translate(20px, 50%);
            transform:translate(20px, 50%); }
  .bp3-slider.bp3-vertical .bp3-slider-handle{
    top:auto; }
    .bp3-slider.bp3-vertical .bp3-slider-handle .bp3-slider-label{
      margin-left:0;
      margin-top:-8px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end, .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      height:8px;
      margin-left:0;
      width:16px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      border-bottom-right-radius:3px;
      border-top-left-radius:0; }
      .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start .bp3-slider-label{
        -webkit-transform:translate(20px);
                transform:translate(20px); }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end{
      border-bottom-left-radius:0;
      border-bottom-right-radius:0;
      border-top-left-radius:3px;
      margin-bottom:8px; }

@-webkit-keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

@keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

.bp3-spinner{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  overflow:visible;
  vertical-align:middle; }
  .bp3-spinner svg{
    display:block; }
  .bp3-spinner path{
    fill-opacity:0; }
  .bp3-spinner .bp3-spinner-head{
    stroke:rgba(92, 112, 128, 0.8);
    stroke-linecap:round;
    -webkit-transform-origin:center;
            transform-origin:center;
    -webkit-transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-spinner .bp3-spinner-track{
    stroke:rgba(92, 112, 128, 0.2); }

.bp3-spinner-animation{
  -webkit-animation:pt-spinner-animation 500ms linear infinite;
          animation:pt-spinner-animation 500ms linear infinite; }
  .bp3-no-spin > .bp3-spinner-animation{
    -webkit-animation:none;
            animation:none; }

.bp3-dark .bp3-spinner .bp3-spinner-head{
  stroke:#8a9ba8; }

.bp3-dark .bp3-spinner .bp3-spinner-track{
  stroke:rgba(16, 22, 26, 0.5); }

.bp3-spinner.bp3-intent-primary .bp3-spinner-head{
  stroke:#137cbd; }

.bp3-spinner.bp3-intent-success .bp3-spinner-head{
  stroke:#0f9960; }

.bp3-spinner.bp3-intent-warning .bp3-spinner-head{
  stroke:#d9822b; }

.bp3-spinner.bp3-intent-danger .bp3-spinner-head{
  stroke:#db3737; }
.bp3-tabs.bp3-vertical{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-tabs.bp3-vertical > .bp3-tab-list{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start;
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab{
      border-radius:3px;
      padding:0 10px;
      width:100%; }
      .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab[aria-selected="true"]{
        background-color:rgba(19, 124, 189, 0.2);
        -webkit-box-shadow:none;
                box-shadow:none; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab-indicator-wrapper .bp3-tab-indicator{
      background-color:rgba(19, 124, 189, 0.2);
      border-radius:3px;
      bottom:0;
      height:auto;
      left:0;
      right:0;
      top:0; }
  .bp3-tabs.bp3-vertical > .bp3-tab-panel{
    margin-top:0;
    padding-left:20px; }

.bp3-tab-list{
  -webkit-box-align:end;
      -ms-flex-align:end;
          align-items:flex-end;
  border:none;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  list-style:none;
  margin:0;
  padding:0;
  position:relative; }
  .bp3-tab-list > *:not(:last-child){
    margin-right:20px; }

.bp3-tab{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  color:#182026;
  cursor:pointer;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  font-size:14px;
  line-height:30px;
  max-width:100%;
  position:relative;
  vertical-align:top; }
  .bp3-tab a{
    color:inherit;
    display:block;
    text-decoration:none; }
  .bp3-tab-indicator-wrapper ~ .bp3-tab{
    background-color:transparent !important;
    -webkit-box-shadow:none !important;
            box-shadow:none !important; }
  .bp3-tab[aria-disabled="true"]{
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
  .bp3-tab[aria-selected="true"]{
    border-radius:0;
    -webkit-box-shadow:inset 0 -3px 0 #106ba3;
            box-shadow:inset 0 -3px 0 #106ba3; }
  .bp3-tab[aria-selected="true"], .bp3-tab:not([aria-disabled="true"]):hover{
    color:#106ba3; }
  .bp3-tab:focus{
    -moz-outline-radius:0; }
  .bp3-large > .bp3-tab{
    font-size:16px;
    line-height:40px; }

.bp3-tab-panel{
  margin-top:20px; }
  .bp3-tab-panel[aria-hidden="true"]{
    display:none; }

.bp3-tab-indicator-wrapper{
  left:0;
  pointer-events:none;
  position:absolute;
  top:0;
  -webkit-transform:translateX(0), translateY(0);
          transform:translateX(0), translateY(0);
  -webkit-transition:height, width, -webkit-transform;
  transition:height, width, -webkit-transform;
  transition:height, transform, width;
  transition:height, transform, width, -webkit-transform;
  -webkit-transition-duration:200ms;
          transition-duration:200ms;
  -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
          transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tab-indicator-wrapper .bp3-tab-indicator{
    background-color:#106ba3;
    bottom:0;
    height:3px;
    left:0;
    position:absolute;
    right:0; }
  .bp3-tab-indicator-wrapper.bp3-no-animation{
    -webkit-transition:none;
    transition:none; }

.bp3-dark .bp3-tab{
  color:#f5f8fa; }
  .bp3-dark .bp3-tab[aria-disabled="true"]{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tab[aria-selected="true"]{
    -webkit-box-shadow:inset 0 -3px 0 #48aff0;
            box-shadow:inset 0 -3px 0 #48aff0; }
  .bp3-dark .bp3-tab[aria-selected="true"], .bp3-dark .bp3-tab:not([aria-disabled="true"]):hover{
    color:#48aff0; }

.bp3-dark .bp3-tab-indicator{
  background-color:#48aff0; }

.bp3-flex-expander{
  -webkit-box-flex:1;
      -ms-flex:1 1;
          flex:1 1; }
.bp3-tag{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background-color:#5c7080;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:none;
          box-shadow:none;
  color:#f5f8fa;
  font-size:12px;
  line-height:16px;
  max-width:100%;
  min-height:20px;
  min-width:20px;
  padding:2px 6px;
  position:relative; }
  .bp3-tag.bp3-interactive{
    cursor:pointer; }
    .bp3-tag.bp3-interactive:hover{
      background-color:rgba(92, 112, 128, 0.85); }
    .bp3-tag.bp3-interactive.bp3-active, .bp3-tag.bp3-interactive:active{
      background-color:rgba(92, 112, 128, 0.7); }
  .bp3-tag > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag::before,
  .bp3-tag > *{
    margin-right:4px; }
  .bp3-tag:empty::before,
  .bp3-tag > :last-child{
    margin-right:0; }
  .bp3-tag:focus{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:0;
    -moz-outline-radius:6px; }
  .bp3-tag.bp3-round{
    border-radius:30px;
    padding-left:8px;
    padding-right:8px; }
  .bp3-dark .bp3-tag{
    background-color:#bfccd6;
    color:#182026; }
    .bp3-dark .bp3-tag.bp3-interactive{
      cursor:pointer; }
      .bp3-dark .bp3-tag.bp3-interactive:hover{
        background-color:rgba(191, 204, 214, 0.85); }
      .bp3-dark .bp3-tag.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-interactive:active{
        background-color:rgba(191, 204, 214, 0.7); }
    .bp3-dark .bp3-tag > .bp3-icon, .bp3-dark .bp3-tag .bp3-icon-standard, .bp3-dark .bp3-tag .bp3-icon-large{
      fill:currentColor; }
  .bp3-tag > .bp3-icon, .bp3-tag .bp3-icon-standard, .bp3-tag .bp3-icon-large{
    fill:#ffffff; }
  .bp3-tag.bp3-large,
  .bp3-large .bp3-tag{
    font-size:14px;
    line-height:20px;
    min-height:30px;
    min-width:30px;
    padding:5px 10px; }
    .bp3-tag.bp3-large::before,
    .bp3-tag.bp3-large > *,
    .bp3-large .bp3-tag::before,
    .bp3-large .bp3-tag > *{
      margin-right:7px; }
    .bp3-tag.bp3-large:empty::before,
    .bp3-tag.bp3-large > :last-child,
    .bp3-large .bp3-tag:empty::before,
    .bp3-large .bp3-tag > :last-child{
      margin-right:0; }
    .bp3-tag.bp3-large.bp3-round,
    .bp3-large .bp3-tag.bp3-round{
      padding-left:12px;
      padding-right:12px; }
  .bp3-tag.bp3-intent-primary{
    background:#137cbd;
    color:#ffffff; }
    .bp3-tag.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.85); }
      .bp3-tag.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.7); }
  .bp3-tag.bp3-intent-success{
    background:#0f9960;
    color:#ffffff; }
    .bp3-tag.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.85); }
      .bp3-tag.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.7); }
  .bp3-tag.bp3-intent-warning{
    background:#d9822b;
    color:#ffffff; }
    .bp3-tag.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.85); }
      .bp3-tag.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.7); }
  .bp3-tag.bp3-intent-danger{
    background:#db3737;
    color:#ffffff; }
    .bp3-tag.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.85); }
      .bp3-tag.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.7); }
  .bp3-tag.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-tag.bp3-minimal > .bp3-icon, .bp3-tag.bp3-minimal .bp3-icon-standard, .bp3-tag.bp3-minimal .bp3-icon-large{
    fill:#5c7080; }
  .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
    background-color:rgba(138, 155, 168, 0.2);
    color:#182026; }
    .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
        background-color:rgba(92, 112, 128, 0.3); }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
        background-color:rgba(92, 112, 128, 0.4); }
    .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
      color:#f5f8fa; }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
          background-color:rgba(191, 204, 214, 0.3); }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
          background-color:rgba(191, 204, 214, 0.4); }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) > .bp3-icon, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-large{
        fill:#a7b6c2; }
  .bp3-tag.bp3-minimal.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15);
    color:#106ba3; }
    .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-primary > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-large{
      fill:#137cbd; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25);
      color:#48aff0; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
          background-color:rgba(19, 124, 189, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
          background-color:rgba(19, 124, 189, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15);
    color:#0d8050; }
    .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-success > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-large{
      fill:#0f9960; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25);
      color:#3dcc91; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
          background-color:rgba(15, 153, 96, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
          background-color:rgba(15, 153, 96, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15);
    color:#bf7326; }
    .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-warning > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-large{
      fill:#d9822b; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25);
      color:#ffb366; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
          background-color:rgba(217, 130, 43, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
          background-color:rgba(217, 130, 43, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15);
    color:#c23030; }
    .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-danger > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-large{
      fill:#db3737; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25);
      color:#ff7373; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
          background-color:rgba(219, 55, 55, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
          background-color:rgba(219, 55, 55, 0.45); }

.bp3-tag-remove{
  background:none;
  border:none;
  color:inherit;
  cursor:pointer;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  margin-bottom:-2px;
  margin-right:-6px !important;
  margin-top:-2px;
  opacity:0.5;
  padding:2px;
  padding-left:0; }
  .bp3-tag-remove:hover{
    background:none;
    opacity:0.8;
    text-decoration:none; }
  .bp3-tag-remove:active{
    opacity:1; }
  .bp3-tag-remove:empty::before{
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-style:normal;
    font-weight:400;
    line-height:1;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    content:""; }
  .bp3-large .bp3-tag-remove{
    margin-right:-10px !important;
    padding:0 5px 0 0; }
    .bp3-large .bp3-tag-remove:empty::before{
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-style:normal;
      font-weight:400;
      line-height:1; }
.bp3-tag-input{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  cursor:text;
  height:auto;
  line-height:inherit;
  min-height:30px;
  padding-left:5px;
  padding-right:0; }
  .bp3-tag-input > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag-input > .bp3-tag-input-values{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag-input .bp3-tag-input-icon{
    color:#5c7080;
    margin-left:2px;
    margin-right:7px;
    margin-top:7px; }
  .bp3-tag-input .bp3-tag-input-values{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    -ms-flex-item-align:stretch;
        align-self:stretch;
    -ms-flex-wrap:wrap;
        flex-wrap:wrap;
    margin-right:7px;
    margin-top:5px;
    min-width:0; }
    .bp3-tag-input .bp3-tag-input-values > *{
      -webkit-box-flex:0;
          -ms-flex-positive:0;
              flex-grow:0;
      -ms-flex-negative:0;
          flex-shrink:0; }
    .bp3-tag-input .bp3-tag-input-values > .bp3-fill{
      -webkit-box-flex:1;
          -ms-flex-positive:1;
              flex-grow:1;
      -ms-flex-negative:1;
          flex-shrink:1; }
    .bp3-tag-input .bp3-tag-input-values::before,
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-right:5px; }
    .bp3-tag-input .bp3-tag-input-values:empty::before,
    .bp3-tag-input .bp3-tag-input-values > :last-child{
      margin-right:0; }
    .bp3-tag-input .bp3-tag-input-values:first-child .bp3-input-ghost:first-child{
      padding-left:5px; }
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-bottom:5px; }
  .bp3-tag-input .bp3-tag{
    overflow-wrap:break-word; }
    .bp3-tag-input .bp3-tag.bp3-active{
      outline:rgba(19, 124, 189, 0.6) auto 2px;
      outline-offset:0;
      -moz-outline-radius:6px; }
  .bp3-tag-input .bp3-input-ghost{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    line-height:20px;
    width:80px; }
    .bp3-tag-input .bp3-input-ghost:disabled, .bp3-tag-input .bp3-input-ghost.bp3-disabled{
      cursor:not-allowed; }
  .bp3-tag-input .bp3-button,
  .bp3-tag-input .bp3-spinner{
    margin:3px;
    margin-left:0; }
  .bp3-tag-input .bp3-button{
    min-height:24px;
    min-width:24px;
    padding:0 7px; }
  .bp3-tag-input.bp3-large{
    height:auto;
    min-height:40px; }
    .bp3-tag-input.bp3-large::before,
    .bp3-tag-input.bp3-large > *{
      margin-right:10px; }
    .bp3-tag-input.bp3-large:empty::before,
    .bp3-tag-input.bp3-large > :last-child{
      margin-right:0; }
    .bp3-tag-input.bp3-large .bp3-tag-input-icon{
      margin-left:5px;
      margin-top:10px; }
    .bp3-tag-input.bp3-large .bp3-input-ghost{
      line-height:30px; }
    .bp3-tag-input.bp3-large .bp3-button{
      min-height:30px;
      min-width:30px;
      padding:5px 10px;
      margin:5px;
      margin-left:0; }
    .bp3-tag-input.bp3-large .bp3-spinner{
      margin:8px;
      margin-left:0; }
  .bp3-tag-input.bp3-active{
    background-color:#ffffff;
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-tag-input .bp3-tag-input-icon, .bp3-tag-input.bp3-dark .bp3-tag-input-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-tag-input .bp3-input-ghost, .bp3-tag-input.bp3-dark .bp3-input-ghost{
    color:#f5f8fa; }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-webkit-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-moz-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost:-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::placeholder{
      color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tag-input.bp3-active, .bp3-tag-input.bp3-dark.bp3-active{
    background-color:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-primary, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-success, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-warning, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-danger, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-input-ghost{
  background:none;
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0; }
  .bp3-input-ghost::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost:focus{
    outline:none !important; }
.bp3-toast{
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  background-color:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  margin:20px 0 0;
  max-width:500px;
  min-width:300px;
  pointer-events:all;
  position:relative !important; }
  .bp3-toast.bp3-toast-enter, .bp3-toast.bp3-toast-appear{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active, .bp3-toast.bp3-toast-appear-active{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-toast.bp3-toast-enter ~ .bp3-toast, .bp3-toast.bp3-toast-appear ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active ~ .bp3-toast, .bp3-toast.bp3-toast-appear-active ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-toast.bp3-toast-exit{
    opacity:1;
    -webkit-filter:blur(0);
            filter:blur(0); }
  .bp3-toast.bp3-toast-exit-active{
    opacity:0;
    -webkit-filter:blur(10px);
            filter:blur(10px);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:opacity, filter;
    transition-property:opacity, filter, -webkit-filter;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-toast.bp3-toast-exit ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0); }
  .bp3-toast.bp3-toast-exit-active ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px);
    -webkit-transition-delay:50ms;
            transition-delay:50ms;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-toast .bp3-button-group{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    padding:5px;
    padding-left:0; }
  .bp3-toast > .bp3-icon{
    color:#5c7080;
    margin:12px;
    margin-right:0; }
  .bp3-toast.bp3-dark,
  .bp3-dark .bp3-toast{
    background-color:#394b59;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-toast.bp3-dark > .bp3-icon,
    .bp3-dark .bp3-toast > .bp3-icon{
      color:#a7b6c2; }
  .bp3-toast[class*="bp3-intent-"] a{
    color:rgba(255, 255, 255, 0.7); }
    .bp3-toast[class*="bp3-intent-"] a:hover{
      color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] > .bp3-icon{
    color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button, .bp3-toast[class*="bp3-intent-"] .bp3-button::before,
  .bp3-toast[class*="bp3-intent-"] .bp3-button .bp3-icon, .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    color:rgba(255, 255, 255, 0.7) !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:focus{
    outline-color:rgba(255, 255, 255, 0.5); }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:hover{
    background-color:rgba(255, 255, 255, 0.15) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    background-color:rgba(255, 255, 255, 0.3) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button::after{
    background:rgba(255, 255, 255, 0.3) !important; }
  .bp3-toast.bp3-intent-primary{
    background-color:#137cbd;
    color:#ffffff; }
  .bp3-toast.bp3-intent-success{
    background-color:#0f9960;
    color:#ffffff; }
  .bp3-toast.bp3-intent-warning{
    background-color:#d9822b;
    color:#ffffff; }
  .bp3-toast.bp3-intent-danger{
    background-color:#db3737;
    color:#ffffff; }

.bp3-toast-message{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  padding:11px;
  word-break:break-word; }

.bp3-toast-container{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box !important;
  display:-ms-flexbox !important;
  display:flex !important;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  left:0;
  overflow:hidden;
  padding:0 20px 20px;
  pointer-events:none;
  right:0;
  z-index:40; }
  .bp3-toast-container.bp3-toast-container-in-portal{
    position:fixed; }
  .bp3-toast-container.bp3-toast-container-inline{
    position:absolute; }
  .bp3-toast-container.bp3-toast-container-top{
    top:0; }
  .bp3-toast-container.bp3-toast-container-bottom{
    bottom:0;
    -webkit-box-orient:vertical;
    -webkit-box-direction:reverse;
        -ms-flex-direction:column-reverse;
            flex-direction:column-reverse;
    top:auto; }
  .bp3-toast-container.bp3-toast-container-left{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
  .bp3-toast-container.bp3-toast-container-right{
    -webkit-box-align:end;
        -ms-flex-align:end;
            align-items:flex-end; }

.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active) ~ .bp3-toast, .bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active) ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-exit-active ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-leave-active ~ .bp3-toast{
  -webkit-transform:translateY(60px);
          transform:translateY(60px); }
.bp3-tooltip{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1); }
  .bp3-tooltip .bp3-popover-arrow{
    height:22px;
    position:absolute;
    width:22px; }
    .bp3-tooltip .bp3-popover-arrow::before{
      height:14px;
      margin:4px;
      width:14px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip{
    margin-bottom:11px;
    margin-top:-11px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
      bottom:-8px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip{
    margin-left:11px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
      left:-8px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip{
    margin-top:11px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
      top:-8px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip{
    margin-left:-11px;
    margin-right:11px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
      right:-8px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-tooltip > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-tooltip > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
    top:-0.22183px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
    right:-0.22183px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
    left:-0.22183px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
    bottom:-0.22183px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-tooltip .bp3-popover-content{
    background:#394b59;
    color:#f5f8fa; }
  .bp3-tooltip .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-tooltip .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-tooltip .bp3-popover-arrow-fill{
    fill:#394b59; }
  .bp3-popover-enter > .bp3-tooltip, .bp3-popover-appear > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8); }
  .bp3-popover-enter-active > .bp3-tooltip, .bp3-popover-appear-active > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-popover-exit > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tooltip .bp3-popover-content{
    padding:10px 12px; }
  .bp3-tooltip.bp3-dark,
  .bp3-dark .bp3-tooltip{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-tooltip .bp3-popover-content{
      background:#e1e8ed;
      color:#394b59; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-fill{
      fill:#e1e8ed; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-content{
    background:#137cbd;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-arrow-fill{
    fill:#137cbd; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-content{
    background:#0f9960;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-arrow-fill{
    fill:#0f9960; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-content{
    background:#d9822b;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-arrow-fill{
    fill:#d9822b; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-content{
    background:#db3737;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-arrow-fill{
    fill:#db3737; }

.bp3-tooltip-indicator{
  border-bottom:dotted 1px;
  cursor:help; }
.bp3-tree .bp3-icon, .bp3-tree .bp3-icon-standard, .bp3-tree .bp3-icon-large{
  color:#5c7080; }
  .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-tree .bp3-icon.bp3-intent-success, .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-tree-node-list{
  list-style:none;
  margin:0;
  padding-left:0; }

.bp3-tree-root{
  background-color:transparent;
  cursor:default;
  padding-left:0;
  position:relative; }

.bp3-tree-node-content-0{
  padding-left:0px; }

.bp3-tree-node-content-1{
  padding-left:23px; }

.bp3-tree-node-content-2{
  padding-left:46px; }

.bp3-tree-node-content-3{
  padding-left:69px; }

.bp3-tree-node-content-4{
  padding-left:92px; }

.bp3-tree-node-content-5{
  padding-left:115px; }

.bp3-tree-node-content-6{
  padding-left:138px; }

.bp3-tree-node-content-7{
  padding-left:161px; }

.bp3-tree-node-content-8{
  padding-left:184px; }

.bp3-tree-node-content-9{
  padding-left:207px; }

.bp3-tree-node-content-10{
  padding-left:230px; }

.bp3-tree-node-content-11{
  padding-left:253px; }

.bp3-tree-node-content-12{
  padding-left:276px; }

.bp3-tree-node-content-13{
  padding-left:299px; }

.bp3-tree-node-content-14{
  padding-left:322px; }

.bp3-tree-node-content-15{
  padding-left:345px; }

.bp3-tree-node-content-16{
  padding-left:368px; }

.bp3-tree-node-content-17{
  padding-left:391px; }

.bp3-tree-node-content-18{
  padding-left:414px; }

.bp3-tree-node-content-19{
  padding-left:437px; }

.bp3-tree-node-content-20{
  padding-left:460px; }

.bp3-tree-node-content{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  height:30px;
  padding-right:5px;
  width:100%; }
  .bp3-tree-node-content:hover{
    background-color:rgba(191, 204, 214, 0.4); }

.bp3-tree-node-caret,
.bp3-tree-node-caret-none{
  min-width:30px; }

.bp3-tree-node-caret{
  color:#5c7080;
  cursor:pointer;
  padding:7px;
  -webkit-transform:rotate(0deg);
          transform:rotate(0deg);
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tree-node-caret:hover{
    color:#182026; }
  .bp3-dark .bp3-tree-node-caret{
    color:#a7b6c2; }
    .bp3-dark .bp3-tree-node-caret:hover{
      color:#f5f8fa; }
  .bp3-tree-node-caret.bp3-tree-node-caret-open{
    -webkit-transform:rotate(90deg);
            transform:rotate(90deg); }
  .bp3-tree-node-caret.bp3-icon-standard::before{
    content:""; }

.bp3-tree-node-icon{
  margin-right:7px;
  position:relative; }

.bp3-tree-node-label{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  position:relative;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-label span{
    display:inline; }

.bp3-tree-node-secondary-label{
  padding:0 5px;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-secondary-label .bp3-popover-wrapper,
  .bp3-tree-node-secondary-label .bp3-popover-target{
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-content{
  background-color:inherit;
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-caret,
.bp3-tree-node.bp3-disabled .bp3-tree-node-icon{
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content,
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-standard, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-large{
    color:#ffffff; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret::before{
    color:rgba(255, 255, 255, 0.7); }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret:hover::before{
    color:#ffffff; }

.bp3-dark .bp3-tree-node-content:hover{
  background-color:rgba(92, 112, 128, 0.3); }

.bp3-dark .bp3-tree .bp3-icon, .bp3-dark .bp3-tree .bp3-icon-standard, .bp3-dark .bp3-tree .bp3-icon-large{
  color:#a7b6c2; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-dark .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
.bp3-omnibar{
  -webkit-filter:blur(0);
          filter:blur(0);
  opacity:1;
  background-color:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  left:calc(50% - 250px);
  top:20vh;
  width:500px;
  z-index:21; }
  .bp3-omnibar.bp3-overlay-enter, .bp3-omnibar.bp3-overlay-appear{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2; }
  .bp3-omnibar.bp3-overlay-enter-active, .bp3-omnibar.bp3-overlay-appear-active{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-omnibar.bp3-overlay-exit{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1; }
  .bp3-omnibar.bp3-overlay-exit-active{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-omnibar .bp3-input{
    background-color:transparent;
    border-radius:0; }
    .bp3-omnibar .bp3-input, .bp3-omnibar .bp3-input:focus{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-omnibar .bp3-menu{
    background-color:transparent;
    border-radius:0;
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
    max-height:calc(60vh - 40px);
    overflow:auto; }
    .bp3-omnibar .bp3-menu:empty{
      display:none; }
  .bp3-dark .bp3-omnibar, .bp3-omnibar.bp3-dark{
    background-color:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-omnibar-overlay .bp3-overlay-backdrop{
  background-color:rgba(16, 22, 26, 0.2); }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-height:300px;
  max-width:400px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }

.bp3-multi-select{
  min-width:150px; }

.bp3-multi-select-popover .bp3-menu{
  max-height:300px;
  max-width:400px;
  overflow:auto; }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-height:300px;
  max-width:400px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yMCA4aC0yLjgxYy0uNDUtLjc4LTEuMDctMS40NS0xLjgyLTEuOTZMMTcgNC40MSAxNS41OSAzbC0yLjE3IDIuMTdDMTIuOTYgNS4wNiAxMi40OSA1IDEyIDVjLS40OSAwLS45Ni4wNi0xLjQxLjE3TDguNDEgMyA3IDQuNDFsMS42MiAxLjYzQzcuODggNi41NSA3LjI2IDcuMjIgNi44MSA4SDR2MmgyLjA5Yy0uMDUuMzMtLjA5LjY2LS4wOSAxdjFINHYyaDJ2MWMwIC4zNC4wNC42Ny4wOSAxSDR2MmgyLjgxYzEuMDQgMS43OSAyLjk3IDMgNS4xOSAzczQuMTUtMS4yMSA1LjE5LTNIMjB2LTJoLTIuMDljLjA1LS4zMy4wOS0uNjYuMDktMXYtMWgydi0yaC0ydi0xYzAtLjM0LS4wNC0uNjctLjA5LTFIMjBWOHptLTYgOGgtNHYtMmg0djJ6bTAtNGgtNHYtMmg0djJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik05IDE2LjE3TDQuODMgMTJsLTEuNDIgMS40MUw5IDE5IDIxIDdsLTEuNDEtMS40MXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTExLjQgMTguNkw2LjggMTRMMTEuNCA5LjRMMTAgOEw0IDE0TDEwIDIwTDExLjQgMTguNlpNMTYuNiAxOC42TDIxLjIgMTRMMTYuNiA5LjRMMTggOEwyNCAxNEwxOCAyMEwxNi42IDE4LjZWMTguNloiLz4KCTwvZz4KPC9zdmc+Cg==);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1pY29uLWJyYW5kMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNmZmYiPgogICAgPHBhdGggZD0iTTEwNSAxMjcuM2g0MHYxMi44aC00MHpNNTEuMSA3N0w3NCA5OS45bC0yMy4zIDIzLjMgMTAuNSAxMC41IDIzLjMtMjMuM0w5NSA5OS45IDg0LjUgODkuNCA2MS42IDY2LjV6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copyright: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDI0IDI0IiBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCI+CiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0xMS44OCw5LjE0YzEuMjgsMC4wNiwxLjYxLDEuMTUsMS42MywxLjY2aDEuNzljLTAuMDgtMS45OC0xLjQ5LTMuMTktMy40NS0zLjE5QzkuNjQsNy42MSw4LDksOCwxMi4xNCBjMCwxLjk0LDAuOTMsNC4yNCwzLjg0LDQuMjRjMi4yMiwwLDMuNDEtMS42NSwzLjQ0LTIuOTVoLTEuNzljLTAuMDMsMC41OS0wLjQ1LDEuMzgtMS42MywxLjQ0QzEwLjU1LDE0LjgzLDEwLDEzLjgxLDEwLDEyLjE0IEMxMCw5LjI1LDExLjI4LDkuMTYsMTEuODgsOS4xNHogTTEyLDJDNi40OCwyLDIsNi40OCwyLDEyczQuNDgsMTAsMTAsMTBzMTAtNC40OCwxMC0xMFMxNy41MiwyLDEyLDJ6IE0xMiwyMGMtNC40MSwwLTgtMy41OS04LTggczMuNTktOCw4LThzOCwzLjU5LDgsOFMxNi40MSwyMCwxMiwyMHoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNGOUE4MjUiPgogICAgPHBhdGggZD0iTTIwLjIgMTEuOGMtMS42IDAtMS43LjUtMS43IDEgMCAuNC4xLjkuMSAxLjMuMS41LjEuOS4xIDEuMyAwIDEuNy0xLjQgMi4zLTMuNSAyLjNoLS45di0xLjloLjVjMS4xIDAgMS40IDAgMS40LS44IDAtLjMgMC0uNi0uMS0xIDAtLjQtLjEtLjgtLjEtMS4yIDAtMS4zIDAtMS44IDEuMy0yLTEuMy0uMi0xLjMtLjctMS4zLTIgMC0uNC4xLS44LjEtMS4yLjEtLjQuMS0uNy4xLTEgMC0uOC0uNC0uNy0xLjQtLjhoLS41VjQuMWguOWMyLjIgMCAzLjUuNyAzLjUgMi4zIDAgLjQtLjEuOS0uMSAxLjMtLjEuNS0uMS45LS4xIDEuMyAwIC41LjIgMSAxLjcgMXYxLjh6TTEuOCAxMC4xYzEuNiAwIDEuNy0uNSAxLjctMSAwLS40LS4xLS45LS4xLTEuMy0uMS0uNS0uMS0uOS0uMS0xLjMgMC0xLjYgMS40LTIuMyAzLjUtMi4zaC45djEuOWgtLjVjLTEgMC0xLjQgMC0xLjQuOCAwIC4zIDAgLjYuMSAxIDAgLjIuMS42LjEgMSAwIDEuMyAwIDEuOC0xLjMgMkM2IDExLjIgNiAxMS43IDYgMTNjMCAuNC0uMS44LS4xIDEuMi0uMS4zLS4xLjctLjEgMSAwIC44LjMuOCAxLjQuOGguNXYxLjloLS45Yy0yLjEgMC0zLjUtLjYtMy41LTIuMyAwLS40LjEtLjkuMS0xLjMuMS0uNS4xLS45LjEtMS4zIDAtLjUtLjItMS0xLjctMXYtMS45eiIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSIxMy44IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY3g9IjExIiBjeT0iOC4yIiByPSIyLjEiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-julia: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDMyNSAzMDAiPgogIDxnIGNsYXNzPSJqcC1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjY2IzYzMzIj4KICAgIDxwYXRoIGQ9Ik0gMTUwLjg5ODQzOCAyMjUgQyAxNTAuODk4NDM4IDI2Ni40MjE4NzUgMTE3LjMyMDMxMiAzMDAgNzUuODk4NDM4IDMwMCBDIDM0LjQ3NjU2MiAzMDAgMC44OTg0MzggMjY2LjQyMTg3NSAwLjg5ODQzOCAyMjUgQyAwLjg5ODQzOCAxODMuNTc4MTI1IDM0LjQ3NjU2MiAxNTAgNzUuODk4NDM4IDE1MCBDIDExNy4zMjAzMTIgMTUwIDE1MC44OTg0MzggMTgzLjU3ODEyNSAxNTAuODk4NDM4IDIyNSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzM4OTgyNiI+CiAgICA8cGF0aCBkPSJNIDIzNy41IDc1IEMgMjM3LjUgMTE2LjQyMTg3NSAyMDMuOTIxODc1IDE1MCAxNjIuNSAxNTAgQyAxMjEuMDc4MTI1IDE1MCA4Ny41IDExNi40MjE4NzUgODcuNSA3NSBDIDg3LjUgMzMuNTc4MTI1IDEyMS4wNzgxMjUgMCAxNjIuNSAwIEMgMjAzLjkyMTg3NSAwIDIzNy41IDMzLjU3ODEyNSAyMzcuNSA3NSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzk1NThiMiI+CiAgICA8cGF0aCBkPSJNIDMyNC4xMDE1NjIgMjI1IEMgMzI0LjEwMTU2MiAyNjYuNDIxODc1IDI5MC41MjM0MzggMzAwIDI0OS4xMDE1NjIgMzAwIEMgMjA3LjY3OTY4OCAzMDAgMTc0LjEwMTU2MiAyNjYuNDIxODc1IDE3NC4xMDE1NjIgMjI1IEMgMTc0LjEwMTU2MiAxODMuNTc4MTI1IDIwNy42Nzk2ODggMTUwIDI0OS4xMDE1NjIgMTUwIEMgMjkwLjUyMzQzOCAxNTAgMzI0LjEwMTU2MiAxODMuNTc4MTI1IDMyNC4xMDE1NjIgMjI1Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgPGcgY2xhc3M9ImpwLWljb24td2FybjAiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4=);
  --jp-icon-listings-info: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MC45NzggNTAuOTc4IiBzdHlsZT0iZW5hYmxlLWJhY2tncm91bmQ6bmV3IDAgMCA1MC45NzggNTAuOTc4OyIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSI+Cgk8Zz4KCQk8cGF0aCBzdHlsZT0iZmlsbDojMDEwMDAyOyIgZD0iTTQzLjUyLDcuNDU4QzM4LjcxMSwyLjY0OCwzMi4zMDcsMCwyNS40ODksMEMxOC42NywwLDEyLjI2NiwyLjY0OCw3LjQ1OCw3LjQ1OAoJCQljLTkuOTQzLDkuOTQxLTkuOTQzLDI2LjExOSwwLDM2LjA2MmM0LjgwOSw0LjgwOSwxMS4yMTIsNy40NTYsMTguMDMxLDcuNDU4YzAsMCwwLjAwMSwwLDAuMDAyLDAKCQkJYzYuODE2LDAsMTMuMjIxLTIuNjQ4LDE4LjAyOS03LjQ1OGM0LjgwOS00LjgwOSw3LjQ1Ny0xMS4yMTIsNy40NTctMTguMDNDNTAuOTc3LDE4LjY3LDQ4LjMyOCwxMi4yNjYsNDMuNTIsNy40NTh6CgkJCSBNNDIuMTA2LDQyLjEwNWMtNC40MzIsNC40MzEtMTAuMzMyLDYuODcyLTE2LjYxNSw2Ljg3MmgtMC4wMDJjLTYuMjg1LTAuMDAxLTEyLjE4Ny0yLjQ0MS0xNi42MTctNi44NzIKCQkJYy05LjE2Mi05LjE2My05LjE2Mi0yNC4wNzEsMC0zMy4yMzNDMTMuMzAzLDQuNDQsMTkuMjA0LDIsMjUuNDg5LDJjNi4yODQsMCwxMi4xODYsMi40NCwxNi42MTcsNi44NzIKCQkJYzQuNDMxLDQuNDMxLDYuODcxLDEwLjMzMiw2Ljg3MSwxNi42MTdDNDguOTc3LDMxLjc3Miw0Ni41MzYsMzcuNjc1LDQyLjEwNiw0Mi4xMDV6Ii8+CgkJPHBhdGggc3R5bGU9ImZpbGw6IzAxMDAwMjsiIGQ9Ik0yMy41NzgsMzIuMjE4Yy0wLjAyMy0xLjczNCwwLjE0My0zLjA1OSwwLjQ5Ni0zLjk3MmMwLjM1My0wLjkxMywxLjExLTEuOTk3LDIuMjcyLTMuMjUzCgkJCWMwLjQ2OC0wLjUzNiwwLjkyMy0xLjA2MiwxLjM2Ny0xLjU3NWMwLjYyNi0wLjc1MywxLjEwNC0xLjQ3OCwxLjQzNi0yLjE3NWMwLjMzMS0wLjcwNywwLjQ5NS0xLjU0MSwwLjQ5NS0yLjUKCQkJYzAtMS4wOTYtMC4yNi0yLjA4OC0wLjc3OS0yLjk3OWMtMC41NjUtMC44NzktMS41MDEtMS4zMzYtMi44MDYtMS4zNjljLTEuODAyLDAuMDU3LTIuOTg1LDAuNjY3LTMuNTUsMS44MzIKCQkJYy0wLjMwMSwwLjUzNS0wLjUwMywxLjE0MS0wLjYwNywxLjgxNGMtMC4xMzksMC43MDctMC4yMDcsMS40MzItMC4yMDcsMi4xNzRoLTIuOTM3Yy0wLjA5MS0yLjIwOCwwLjQwNy00LjExNCwxLjQ5My01LjcxOQoJCQljMS4wNjItMS42NCwyLjg1NS0yLjQ4MSw1LjM3OC0yLjUyN2MyLjE2LDAuMDIzLDMuODc0LDAuNjA4LDUuMTQxLDEuNzU4YzEuMjc4LDEuMTYsMS45MjksMi43NjQsMS45NSw0LjgxMQoJCQljMCwxLjE0Mi0wLjEzNywyLjExMS0wLjQxLDIuOTExYy0wLjMwOSwwLjg0NS0wLjczMSwxLjU5My0xLjI2OCwyLjI0M2MtMC40OTIsMC42NS0xLjA2OCwxLjMxOC0xLjczLDIuMDAyCgkJCWMtMC42NSwwLjY5Ny0xLjMxMywxLjQ3OS0xLjk4NywyLjM0NmMtMC4yMzksMC4zNzctMC40MjksMC43NzctMC41NjUsMS4xOTljLTAuMTYsMC45NTktMC4yMTcsMS45NTEtMC4xNzEsMi45NzkKCQkJQzI2LjU4OSwzMi4yMTgsMjMuNTc4LDMyLjIxOCwyMy41NzgsMzIuMjE4eiBNMjMuNTc4LDM4LjIydi0zLjQ4NGgzLjA3NnYzLjQ4NEgyMy41Nzh6Ii8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-numbering: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTQgMTlINlYxOS41SDVWMjAuNUg2VjIxSDRWMjJIN1YxOEg0VjE5Wk01IDEwSDZWNkg0VjdINVYxMFpNNCAxM0g1LjhMNCAxNS4xVjE2SDdWMTVINS4yTDcgMTIuOVYxMkg0VjEzWk05IDdWOUgyM1Y3SDlaTTkgMjFIMjNWMTlIOVYyMVpNOSAxNUgyM1YxM0g5VjE1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-offline-bolt: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDIuMDJjLTUuNTEgMC05Ljk4IDQuNDctOS45OCA5Ljk4czQuNDcgOS45OCA5Ljk4IDkuOTggOS45OC00LjQ3IDkuOTgtOS45OFMxNy41MSAyLjAyIDEyIDIuMDJ6TTExLjQ4IDIwdi02LjI2SDhMMTMgNHY2LjI2aDMuMzVMMTEuNDggMjB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-pdf: url(data:image/svg+xml;base64,PHN2ZwogICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyMiAyMiIgd2lkdGg9IjE2Ij4KICAgIDxwYXRoIHRyYW5zZm9ybT0icm90YXRlKDQ1KSIgY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0ZGMkEyQSIKICAgICAgIGQ9Im0gMjIuMzQ0MzY5LC0zLjAxNjM2NDIgaCA1LjYzODYwNCB2IDEuNTc5MjQzMyBoIC0zLjU0OTIyNyB2IDEuNTA4NjkyOTkgaCAzLjMzNzU3NiBWIDEuNjUwODE1NCBoIC0zLjMzNzU3NiB2IDMuNDM1MjYxMyBoIC0yLjA4OTM3NyB6IG0gLTcuMTM2NDQ0LDEuNTc5MjQzMyB2IDQuOTQzOTU0MyBoIDAuNzQ4OTIgcSAxLjI4MDc2MSwwIDEuOTUzNzAzLC0wLjYzNDk1MzUgMC42NzgzNjksLTAuNjM0OTUzNSAwLjY3ODM2OSwtMS44NDUxNjQxIDAsLTEuMjA0NzgzNTUgLTAuNjcyOTQyLC0xLjgzNDMxMDExIC0wLjY3Mjk0MiwtMC42Mjk1MjY1OSAtMS45NTkxMywtMC42Mjk1MjY1OSB6IG0gLTIuMDg5Mzc3LC0xLjU3OTI0MzMgaCAyLjIwMzM0MyBxIDEuODQ1MTY0LDAgMi43NDYwMzksMC4yNjU5MjA3IDAuOTA2MzAxLDAuMjYwNDkzNyAxLjU1MjEwOCwwLjg5MDAyMDMgMC41Njk4MywwLjU0ODEyMjMgMC44NDY2MDUsMS4yNjQ0ODAwNiAwLjI3Njc3NCwwLjcxNjM1NzgxIDAuMjc2Nzc0LDEuNjIyNjU4OTQgMCwwLjkxNzE1NTEgLTAuMjc2Nzc0LDEuNjM4OTM5OSAtMC4yNzY3NzUsMC43MTYzNTc4IC0wLjg0NjYwNSwxLjI2NDQ4IC0wLjY1MTIzNCwwLjYyOTUyNjYgLTEuNTYyOTYyLDAuODk1NDQ3MyAtMC45MTE3MjgsMC4yNjA0OTM3IC0yLjczNTE4NSwwLjI2MDQ5MzcgaCAtMi4yMDMzNDMgeiBtIC04LjE0NTg1NjUsMCBoIDMuNDY3ODIzIHEgMS41NDY2ODE2LDAgMi4zNzE1Nzg1LDAuNjg5MjIzIDAuODMwMzI0LDAuNjgzNzk2MSAwLjgzMDMyNCwxLjk1MzcwMzE0IDAsMS4yNzUzMzM5NyAtMC44MzAzMjQsMS45NjQ1NTcwNiBRIDkuOTg3MTk2MSwyLjI3NDkxNSA4LjQ0MDUxNDUsMi4yNzQ5MTUgSCA3LjA2MjA2ODQgViA1LjA4NjA3NjcgSCA0Ljk3MjY5MTUgWiBtIDIuMDg5Mzc2OSwxLjUxNDExOTkgdiAyLjI2MzAzOTQzIGggMS4xNTU5NDEgcSAwLjYwNzgxODgsMCAwLjkzODg2MjksLTAuMjkzMDU1NDcgMC4zMzEwNDQxLC0wLjI5ODQ4MjQxIDAuMzMxMDQ0MSwtMC44NDExNzc3MiAwLC0wLjU0MjY5NTMxIC0wLjMzMTA0NDEsLTAuODM1NzUwNzQgLTAuMzMxMDQ0MSwtMC4yOTMwNTU1IC0wLjkzODg2MjksLTAuMjkzMDU1NSB6IgovPgo8L3N2Zz4K);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMEQ0N0ExIj4KICAgIDxwYXRoIGQ9Ik0xMS4xIDYuOVY1LjhINi45YzAtLjUgMC0xLjMuMi0xLjYuNC0uNy44LTEuMSAxLjctMS40IDEuNy0uMyAyLjUtLjMgMy45LS4xIDEgLjEgMS45LjkgMS45IDEuOXY0LjJjMCAuNS0uOSAxLjYtMiAxLjZIOC44Yy0xLjUgMC0yLjQgMS40LTIuNCAyLjh2Mi4ySDQuN0MzLjUgMTUuMSAzIDE0IDMgMTMuMVY5Yy0uMS0xIC42LTIgMS44LTIgMS41LS4xIDYuMy0uMSA2LjMtLjF6Ii8+CiAgICA8cGF0aCBkPSJNMTAuOSAxNS4xdjEuMWg0LjJjMCAuNSAwIDEuMy0uMiAxLjYtLjQuNy0uOCAxLjEtMS43IDEuNC0xLjcuMy0yLjUuMy0zLjkuMS0xLS4xLTEuOS0uOS0xLjktMS45di00LjJjMC0uNS45LTEuNiAyLTEuNmgzLjhjMS41IDAgMi40LTEuNCAyLjQtMi44VjYuNmgxLjdDMTguNSA2LjkgMTkgOCAxOSA4LjlWMTNjMCAxLS43IDIuMS0xLjkgMi4xaC02LjJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-redo: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTE4LjQgMTAuNkMxNi41NSA4Ljk5IDE0LjE1IDggMTEuNSA4Yy00LjY1IDAtOC41OCAzLjAzLTkuOTYgNy4yMkwzLjkgMTZjMS4wNS0zLjE5IDQuMDUtNS41IDcuNi01LjUgMS45NSAwIDMuNzMuNzIgNS4xMiAxLjg4TDEzIDE2aDlWN2wtMy42IDMuNnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-table-rows: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMSw4SDNWNGgxOFY4eiBNMjEsMTBIM3Y0aDE4VjEweiBNMjEsMTZIM3Y0aDE4VjE2eiIvPgogICAgPC9nPgo8L3N2Zz4=);
  --jp-icon-tag: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjgiIGhlaWdodD0iMjgiIHZpZXdCb3g9IjAgMCA0MyAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTI4LjgzMzIgMTIuMzM0TDMyLjk5OTggMTYuNTAwN0wzNy4xNjY1IDEyLjMzNEgyOC44MzMyWiIvPgoJCTxwYXRoIGQ9Ik0xNi4yMDk1IDIxLjYxMDRDMTUuNjg3MyAyMi4xMjk5IDE0Ljg0NDMgMjIuMTI5OSAxNC4zMjQ4IDIxLjYxMDRMNi45ODI5IDE0LjcyNDVDNi41NzI0IDE0LjMzOTQgNi4wODMxMyAxMy42MDk4IDYuMDQ3ODYgMTMuMDQ4MkM1Ljk1MzQ3IDExLjUyODggNi4wMjAwMiA4LjYxOTQ0IDYuMDY2MjEgNy4wNzY5NUM2LjA4MjgxIDYuNTE0NzcgNi41NTU0OCA2LjA0MzQ3IDcuMTE4MDQgNi4wMzA1NUM5LjA4ODYzIDUuOTg0NzMgMTMuMjYzOCA1LjkzNTc5IDEzLjY1MTggNi4zMjQyNUwyMS43MzY5IDEzLjYzOUMyMi4yNTYgMTQuMTU4NSAyMS43ODUxIDE1LjQ3MjQgMjEuMjYyIDE1Ljk5NDZMMTYuMjA5NSAyMS42MTA0Wk05Ljc3NTg1IDguMjY1QzkuMzM1NTEgNy44MjU2NiA4LjYyMzUxIDcuODI1NjYgOC4xODI4IDguMjY1QzcuNzQzNDYgOC43MDU3MSA3Ljc0MzQ2IDkuNDE3MzMgOC4xODI4IDkuODU2NjdDOC42MjM4MiAxMC4yOTY0IDkuMzM1ODIgMTAuMjk2NCA5Ljc3NTg1IDkuODU2NjdDMTAuMjE1NiA5LjQxNzMzIDEwLjIxNTYgOC43MDUzMyA5Ljc3NTg1IDguMjY1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMikiIGZpbGw9IiMzMzMzMzMiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uLWFjY2VudDIganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGQ9Ik01LjA1NjY0IDguNzYxNzJDNS4wNTY2NCA4LjU5NzY2IDUuMDMxMjUgOC40NTMxMiA0Ljk4MDQ3IDguMzI4MTJDNC45MzM1OSA4LjE5OTIyIDQuODU1NDcgOC4wODIwMyA0Ljc0NjA5IDcuOTc2NTZDNC42NDA2MiA3Ljg3MTA5IDQuNSA3Ljc3NTM5IDQuMzI0MjIgNy42ODk0NUM0LjE1MjM0IDcuNTk5NjEgMy45NDMzNiA3LjUxMTcyIDMuNjk3MjcgNy40MjU3OEMzLjMwMjczIDcuMjg1MTYgMi45NDMzNiA3LjEzNjcyIDIuNjE5MTQgNi45ODA0N0MyLjI5NDkyIDYuODI0MjIgMi4wMTc1OCA2LjY0MjU4IDEuNzg3MTEgNi40MzU1NUMxLjU2MDU1IDYuMjI4NTIgMS4zODQ3NyA1Ljk4ODI4IDEuMjU5NzcgNS43MTQ4NEMxLjEzNDc3IDUuNDM3NSAxLjA3MjI3IDUuMTA5MzggMS4wNzIyNyA0LjczMDQ3QzEuMDcyMjcgNC4zOTg0NCAxLjEyODkxIDQuMDk1NyAxLjI0MjE5IDMuODIyMjdDMS4zNTU0NyAzLjU0NDkyIDEuNTE1NjIgMy4zMDQ2OSAxLjcyMjY2IDMuMTAxNTZDMS45Mjk2OSAyLjg5ODQ0IDIuMTc5NjkgMi43MzQzNyAyLjQ3MjY2IDIuNjA5MzhDMi43NjU2MiAyLjQ4NDM4IDMuMDkxOCAyLjQwNDMgMy40NTExNyAyLjM2OTE0VjEuMTA5MzhINC4zODg2N1YyLjM4MDg2QzQuNzQwMjMgMi40Mjc3MyA1LjA1NjY0IDIuNTIzNDQgNS4zMzc4OSAyLjY2Nzk3QzUuNjE5MTQgMi44MTI1IDUuODU3NDIgMy4wMDE5NSA2LjA1MjczIDMuMjM2MzNDNi4yNTE5NSAzLjQ2NjggNi40MDQzIDMuNzQwMjMgNi41MDk3NyA0LjA1NjY0QzYuNjE5MTQgNC4zNjkxNCA2LjY3MzgzIDQuNzIwNyA2LjY3MzgzIDUuMTExMzNINS4wNDQ5MkM1LjA0NDkyIDQuNjM4NjcgNC45Mzc1IDQuMjgxMjUgNC43MjI2NiA0LjAzOTA2QzQuNTA3ODEgMy43OTI5NyA0LjIxNjggMy42Njk5MiAzLjg0OTYxIDMuNjY5OTJDMy42NTAzOSAzLjY2OTkyIDMuNDc2NTYgMy42OTcyNyAzLjMyODEyIDMuNzUxOTVDMy4xODM1OSAzLjgwMjczIDMuMDY0NDUgMy44NzY5NSAyLjk3MDcgMy45NzQ2MUMyLjg3Njk1IDQuMDY4MzYgMi44MDY2NCA0LjE3OTY5IDIuNzU5NzcgNC4zMDg1OUMyLjcxNjggNC40Mzc1IDIuNjk1MzEgNC41NzgxMiAyLjY5NTMxIDQuNzMwNDdDMi42OTUzMSA0Ljg4MjgxIDIuNzE2OCA1LjAxOTUzIDIuNzU5NzcgNS4xNDA2MkMyLjgwNjY0IDUuMjU3ODEgMi44ODI4MSA1LjM2NzE5IDIuOTg4MjggNS40Njg3NUMzLjA5NzY2IDUuNTcwMzEgMy4yNDAyMyA1LjY2Nzk3IDMuNDE2MDIgNS43NjE3MkMzLjU5MTggNS44NTE1NiAzLjgxMDU1IDUuOTQzMzYgNC4wNzIyNyA2LjAzNzExQzQuNDY2OCA2LjE4NTU1IDQuODI0MjIgNi4zMzk4NCA1LjE0NDUzIDYuNUM1LjQ2NDg0IDYuNjU2MjUgNS43MzgyOCA2LjgzOTg0IDUuOTY0ODQgNy4wNTA3OEM2LjE5NTMxIDcuMjU3ODEgNi4zNzEwOSA3LjUgNi40OTIxOSA3Ljc3NzM0QzYuNjE3MTkgOC4wNTA3OCA2LjY3OTY5IDguMzc1IDYuNjc5NjkgOC43NUM2LjY3OTY5IDkuMDkzNzUgNi42MjMwNSA5LjQwNDMgNi41MDk3NyA5LjY4MTY0QzYuMzk2NDggOS45NTUwOCA2LjIzNDM4IDEwLjE5MTQgNi4wMjM0NCAxMC4zOTA2QzUuODEyNSAxMC41ODk4IDUuNTU4NTkgMTAuNzUgNS4yNjE3MiAxMC44NzExQzQuOTY0ODQgMTAuOTg4MyA0LjYzMjgxIDExLjA2NDUgNC4yNjU2MiAxMS4wOTk2VjEyLjI0OEgzLjMzMzk4VjExLjA5OTZDMy4wMDE5NSAxMS4wNjg0IDIuNjc5NjkgMTAuOTk2MSAyLjM2NzE5IDEwLjg4MjhDMi4wNTQ2OSAxMC43NjU2IDEuNzc3MzQgMTAuNTk3NyAxLjUzNTE2IDEwLjM3ODlDMS4yOTY4OCAxMC4xNjAyIDEuMTA1NDcgOS44ODQ3NyAwLjk2MDkzOCA5LjU1MjczQzAuODE2NDA2IDkuMjE2OCAwLjc0NDE0MSA4LjgxNDQ1IDAuNzQ0MTQxIDguMzQ1N0gyLjM3ODkxQzIuMzc4OTEgOC42MjY5NSAyLjQxOTkyIDguODYzMjggMi41MDE5NSA5LjA1NDY5QzIuNTgzOTggOS4yNDIxOSAyLjY4OTQ1IDkuMzkyNTggMi44MTgzNiA5LjUwNTg2QzIuOTUxMTcgOS42MTUyMyAzLjEwMTU2IDkuNjkzMzYgMy4yNjk1MyA5Ljc0MDIzQzMuNDM3NSA5Ljc4NzExIDMuNjA5MzggOS44MTA1NSAzLjc4NTE2IDkuODEwNTVDNC4yMDMxMiA5LjgxMDU1IDQuNTE5NTMgOS43MTI4OSA0LjczNDM4IDkuNTE3NThDNC45NDkyMiA5LjMyMjI3IDUuMDU2NjQgOS4wNzAzMSA1LjA1NjY0IDguNzYxNzJaTTEzLjQxOCAxMi4yNzE1SDguMDc0MjJWMTFIMTMuNDE4VjEyLjI3MTVaIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzLjk1MjY0IDYpIiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTUgMTVIM3YyaDEydi0yem0wLThIM3YyaDEyVjd6TTMgMTNoMTh2LTJIM3Yyem0wIDhoMTh2LTJIM3Yyek0zIDN2MmgxOFYzSDN6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-toc: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik03LDVIMjFWN0g3VjVNNywxM1YxMUgyMVYxM0g3TTQsNC41QTEuNSwxLjUgMCAwLDEgNS41LDZBMS41LDEuNSAwIDAsMSA0LDcuNUExLjUsMS41IDAgMCwxIDIuNSw2QTEuNSwxLjUgMCAwLDEgNCw0LjVNNCwxMC41QTEuNSwxLjUgMCAwLDEgNS41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMy41QTEuNSwxLjUgMCAwLDEgMi41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMC41TTcsMTlWMTdIMjFWMTlIN000LDE2LjVBMS41LDEuNSAwIDAsMSA1LjUsMThBMS41LDEuNSAwIDAsMSA0LDE5LjVBMS41LDEuNSAwIDAsMSAyLjUsMThBMS41LDEuNSAwIDAsMSA0LDE2LjVaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tree-view: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMiAxMVYzaC03djNIOVYzSDJ2OGg3VjhoMnYxMGg0djNoN3YtOGgtN3YzaC0yVjhoMnYzeiIvPgogICAgPC9nPgo8L3N2Zz4=);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}
.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}
.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}
.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}
.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}
.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}
.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}
.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}
.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}
.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}
.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}
.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}
.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}
.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}
.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}
.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}
.jp-CodeIcon {
  background-image: var(--jp-icon-code);
}
.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}
.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}
.jp-CopyrightIcon {
  background-image: var(--jp-icon-copyright);
}
.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}
.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}
.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}
.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}
.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}
.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}
.jp-FileIcon {
  background-image: var(--jp-icon-file);
}
.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}
.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}
.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}
.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}
.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}
.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}
.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}
.jp-JuliaIcon {
  background-image: var(--jp-icon-julia);
}
.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}
.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}
.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}
.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}
.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}
.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}
.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}
.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}
.jp-ListIcon {
  background-image: var(--jp-icon-list);
}
.jp-ListingsInfoIcon {
  background-image: var(--jp-icon-listings-info);
}
.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}
.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}
.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}
.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}
.jp-NumberingIcon {
  background-image: var(--jp-icon-numbering);
}
.jp-OfflineBoltIcon {
  background-image: var(--jp-icon-offline-bolt);
}
.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}
.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}
.jp-PdfIcon {
  background-image: var(--jp-icon-pdf);
}
.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}
.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}
.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}
.jp-RedoIcon {
  background-image: var(--jp-icon-redo);
}
.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}
.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}
.jp-RunIcon {
  background-image: var(--jp-icon-run);
}
.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}
.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}
.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}
.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}
.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}
.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}
.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}
.jp-TableRowsIcon {
  background-image: var(--jp-icon-table-rows);
}
.jp-TagIcon {
  background-image: var(--jp-icon-tag);
}
.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}
.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}
.jp-TocIcon {
  background-image: var(--jp-icon-toc);
}
.jp-TreeViewIcon {
  background-image: var(--jp-icon-tree-view);
}
.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}
.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}
.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}
.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}
/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}
/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}
/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}
.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}
.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}
.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}
.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}
.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}
.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}
.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}
.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}
/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}
.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}
.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}
.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}
.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}
.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}
.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}
/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

/* CSS for icons in selected items in the settings editor */
#setting-editor .jp-PluginList .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
#setting-editor
  .jp-PluginList
  .jp-mod-selected
  .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected tabs in the sidebar tab manager */
#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable[fill] {
  fill: #fff;
}

#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable[fill] {
  fill: var(--jp-brand-color1);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable-inverse[fill] {
  fill: #fff;
}

/**
 * TODO: come up with non css-hack solution for showing the busy icon on top
 *  of the close icon
 * CSS for complex behavior of close icon of tabs in the sidebar tab manager
 */
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-dirty.jp-mod-active
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: #fff;
}

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) svg {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-switch {
  display: flex;
  align-items: center;
  padding-left: 4px;
  padding-right: 4px;
  font-size: var(--jp-ui-font-size1);
  background-color: transparent;
  color: var(--jp-ui-font-color1);
  border: none;
  height: 20px;
}

.jp-switch:hover {
  background-color: var(--jp-layout-color2);
}

.jp-switch-label {
  margin-right: 5px;
}

.jp-switch-track {
  cursor: pointer;
  background-color: var(--jp-border-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 34px;
  height: 16px;
  width: 35px;
  position: relative;
}

.jp-switch-track::before {
  content: '';
  position: absolute;
  height: 10px;
  width: 10px;
  margin: 3px;
  left: 0px;
  background-color: var(--jp-ui-inverse-font-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 50%;
}

.jp-switch[aria-checked='true'] .jp-switch-track {
  background-color: var(--jp-warn-color0);
}

.jp-switch[aria-checked='true'] .jp-switch-track::before {
  /* track width (35) - margins (3 + 3) - thumb width (10) */
  left: 19px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

/* Override Blueprint's _reset.scss styles */
html {
  box-sizing: unset;
}

*,
*::before,
*::after {
  box-sizing: unset;
}

body {
  color: unset;
  font-family: var(--jp-ui-font-family);
}

p {
  margin-top: unset;
  margin-bottom: unset;
}

small {
  font-size: unset;
}

strong {
  font-weight: unset;
}

/* Override Blueprint's _typography.scss styles */
a {
  text-decoration: unset;
  color: unset;
}
a:hover {
  text-decoration: unset;
  color: unset;
}

/* Override Blueprint's _accessibility.scss styles */
:focus {
  outline: unset;
  outline-offset: unset;
  -moz-outline-radius: unset;
}

/* Styles for ui-components */
.jp-Button {
  border-radius: var(--jp-border-radius);
  padding: 0px 12px;
  font-size: var(--jp-ui-font-size1);
}

/* Use our own theme for hover styles */
button.jp-Button.bp3-button.bp3-minimal:hover {
  background-color: var(--jp-layout-color2);
}
.jp-Button.minimal {
  color: unset !important;
}

.jp-Button.jp-ToolbarButtonComponent {
  text-transform: none;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color3);
}

.jp-BPIcon {
  display: inline-block;
  vertical-align: middle;
  margin: auto;
}

/* Stop blueprint futzing with our icon fills */
.bp3-icon.jp-BPIcon > svg:not([fill]) {
  fill: var(--jp-inverse-layout-color3);
}

.jp-InputGroupAction {
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

/* Use our own theme for hover and option styles */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}
select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-top: 1px solid var(--jp-border-color2);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-Collapse-header {
  padding: 1px 12px;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size2);
}

.jp-Collapse-header:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Collapse-contents {
  padding: 0px 12px 0px 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0px;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Modal variant
|----------------------------------------------------------------------------*/

.jp-ModalCommandPalette {
  position: absolute;
  z-index: 10000;
  top: 38px;
  left: 30%;
  margin: 0;
  padding: 4px;
  width: 40%;
  box-shadow: var(--jp-elevation-z4);
  border-radius: 4px;
  background: var(--jp-layout-color0);
}

.jp-ModalCommandPalette .lm-CommandPalette {
  max-height: 40vh;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-close-icon::after {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-header {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-item {
  margin-left: 4px;
  margin-right: 4px;
}

.jp-ModalCommandPalette
  .lm-CommandPalette
  .lm-CommandPalette-item.lm-mod-disabled {
  display: none;
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0px 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-SearchIconGroup {
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  padding: 5px 5px 1px 5px;
}

.jp-SearchIconGroup svg {
  height: 20px;
  width: 20px;
}

.jp-SearchIconGroup .jp-icon3[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color2);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0px;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item.lm-mod-active {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active .jp-icon-selectable[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.6;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty:after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0px 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0px;
  left: 0px;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px;
  padding-bottom: 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
  resize: both;
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0px;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

button.jp-Dialog-close-button {
  padding: 0;
  height: 100%;
  min-width: unset;
  min-height: unset;
}

.jp-Dialog-header {
  display: flex;
  justify-content: space-between;
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0px 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

.jp-HoverBox.jp-mod-outofview {
  display: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

.jp-Input-Boolean-Dialog {
  flex-direction: row-reverse;
  align-items: end;
  width: 100%;
}

.jp-Input-Boolean-Dialog > label {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;

  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;

  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #aa00ff;

  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;

  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;

  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;

  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;

  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;

  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;

  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;

  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;

  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;

  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ffff00;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;

  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;

  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;

  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;

  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;

  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eeeeee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;

  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent:before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent:after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0px 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input[type='checkbox'].jp-mod-styled {
  appearance: checkbox;
  -webkit-appearance: checkbox;
  -moz-appearance: checkbox;
  height: auto;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-FileDialog-Checkbox {
  margin-top: 35px;
  display: flex;
  flex-direction: row;
  align-items: end;
  width: 100%;
}

.jp-FileDialog-Checkbox > label {
  flex: 1 1 auto;
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  height: 28px;
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  background-color: var(--jp-layout-color1);
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0px 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  height: 32px;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 1;
  overflow-x: auto;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px;
  margin: 0px;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px 6px;
  margin: 0px;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent span {
  padding: 0px;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar.jp-Toolbar-micro {
  padding: 0;
  min-height: 0;
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar {
  border: none;
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ body.p-mod-override-cursor *, /* </DEPRECATED> */
body.lm-mod-override-cursor * {
  cursor: inherit !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/* BASICS */

.CodeMirror {
  /* Set height, width, borders, and global font properties here */
  font-family: monospace;
  height: 300px;
  color: black;
  direction: ltr;
}

/* PADDING */

.CodeMirror-lines {
  padding: 4px 0; /* Vertical padding around content */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  padding: 0 4px; /* Horizontal padding of content */
}

.CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  background-color: white; /* The little square between H and V scrollbars */
}

/* GUTTER */

.CodeMirror-gutters {
  border-right: 1px solid #ddd;
  background-color: #f7f7f7;
  white-space: nowrap;
}
.CodeMirror-linenumbers {}
.CodeMirror-linenumber {
  padding: 0 3px 0 5px;
  min-width: 20px;
  text-align: right;
  color: #999;
  white-space: nowrap;
}

.CodeMirror-guttermarker { color: black; }
.CodeMirror-guttermarker-subtle { color: #999; }

/* CURSOR */

.CodeMirror-cursor {
  border-left: 1px solid black;
  border-right: none;
  width: 0;
}
/* Shown when moving in bi-directional text */
.CodeMirror div.CodeMirror-secondarycursor {
  border-left: 1px solid silver;
}
.cm-fat-cursor .CodeMirror-cursor {
  width: auto;
  border: 0 !important;
  background: #7e7;
}
.cm-fat-cursor div.CodeMirror-cursors {
  z-index: 1;
}
.cm-fat-cursor-mark {
  background-color: rgba(20, 255, 20, 0.5);
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
}
.cm-animate-fat-cursor {
  width: auto;
  border: 0;
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
  background-color: #7e7;
}
@-moz-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@-webkit-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}

/* Can style cursor different in overwrite (non-insert) mode */
.CodeMirror-overwrite .CodeMirror-cursor {}

.cm-tab { display: inline-block; text-decoration: inherit; }

.CodeMirror-rulers {
  position: absolute;
  left: 0; right: 0; top: -50px; bottom: 0;
  overflow: hidden;
}
.CodeMirror-ruler {
  border-left: 1px solid #ccc;
  top: 0; bottom: 0;
  position: absolute;
}

/* DEFAULT THEME */

.cm-s-default .cm-header {color: blue;}
.cm-s-default .cm-quote {color: #090;}
.cm-negative {color: #d44;}
.cm-positive {color: #292;}
.cm-header, .cm-strong {font-weight: bold;}
.cm-em {font-style: italic;}
.cm-link {text-decoration: underline;}
.cm-strikethrough {text-decoration: line-through;}

.cm-s-default .cm-keyword {color: #708;}
.cm-s-default .cm-atom {color: #219;}
.cm-s-default .cm-number {color: #164;}
.cm-s-default .cm-def {color: #00f;}
.cm-s-default .cm-variable,
.cm-s-default .cm-punctuation,
.cm-s-default .cm-property,
.cm-s-default .cm-operator {}
.cm-s-default .cm-variable-2 {color: #05a;}
.cm-s-default .cm-variable-3, .cm-s-default .cm-type {color: #085;}
.cm-s-default .cm-comment {color: #a50;}
.cm-s-default .cm-string {color: #a11;}
.cm-s-default .cm-string-2 {color: #f50;}
.cm-s-default .cm-meta {color: #555;}
.cm-s-default .cm-qualifier {color: #555;}
.cm-s-default .cm-builtin {color: #30a;}
.cm-s-default .cm-bracket {color: #997;}
.cm-s-default .cm-tag {color: #170;}
.cm-s-default .cm-attribute {color: #00c;}
.cm-s-default .cm-hr {color: #999;}
.cm-s-default .cm-link {color: #00c;}

.cm-s-default .cm-error {color: #f00;}
.cm-invalidchar {color: #f00;}

.CodeMirror-composing { border-bottom: 2px solid; }

/* Default styles for common addons */

div.CodeMirror span.CodeMirror-matchingbracket {color: #0b0;}
div.CodeMirror span.CodeMirror-nonmatchingbracket {color: #a22;}
.CodeMirror-matchingtag { background: rgba(255, 150, 0, .3); }
.CodeMirror-activeline-background {background: #e8f2ff;}

/* STOP */

/* The rest of this file contains styles related to the mechanics of
   the editor. You probably shouldn't touch them. */

.CodeMirror {
  position: relative;
  overflow: hidden;
  background: white;
}

.CodeMirror-scroll {
  overflow: scroll !important; /* Things will break if this is overridden */
  /* 50px is the magic margin used to hide the element's real scrollbars */
  /* See overflow: hidden in .CodeMirror */
  margin-bottom: -50px; margin-right: -50px;
  padding-bottom: 50px;
  height: 100%;
  outline: none; /* Prevent dragging from highlighting the element */
  position: relative;
}
.CodeMirror-sizer {
  position: relative;
  border-right: 50px solid transparent;
}

/* The fake, visible scrollbars. Used to force redraw during scrolling
   before actual scrolling happens, thus preventing shaking and
   flickering artifacts. */
.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  position: absolute;
  z-index: 6;
  display: none;
  outline: none;
}
.CodeMirror-vscrollbar {
  right: 0; top: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}
.CodeMirror-hscrollbar {
  bottom: 0; left: 0;
  overflow-y: hidden;
  overflow-x: scroll;
}
.CodeMirror-scrollbar-filler {
  right: 0; bottom: 0;
}
.CodeMirror-gutter-filler {
  left: 0; bottom: 0;
}

.CodeMirror-gutters {
  position: absolute; left: 0; top: 0;
  min-height: 100%;
  z-index: 3;
}
.CodeMirror-gutter {
  white-space: normal;
  height: 100%;
  display: inline-block;
  vertical-align: top;
  margin-bottom: -50px;
}
.CodeMirror-gutter-wrapper {
  position: absolute;
  z-index: 4;
  background: none !important;
  border: none !important;
}
.CodeMirror-gutter-background {
  position: absolute;
  top: 0; bottom: 0;
  z-index: 4;
}
.CodeMirror-gutter-elt {
  position: absolute;
  cursor: default;
  z-index: 4;
}
.CodeMirror-gutter-wrapper ::selection { background-color: transparent }
.CodeMirror-gutter-wrapper ::-moz-selection { background-color: transparent }

.CodeMirror-lines {
  cursor: text;
  min-height: 1px; /* prevents collapsing before first draw */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  /* Reset some styles that the rest of the page might have set */
  -moz-border-radius: 0; -webkit-border-radius: 0; border-radius: 0;
  border-width: 0;
  background: transparent;
  font-family: inherit;
  font-size: inherit;
  margin: 0;
  white-space: pre;
  word-wrap: normal;
  line-height: inherit;
  color: inherit;
  z-index: 2;
  position: relative;
  overflow: visible;
  -webkit-tap-highlight-color: transparent;
  -webkit-font-variant-ligatures: contextual;
  font-variant-ligatures: contextual;
}
.CodeMirror-wrap pre.CodeMirror-line,
.CodeMirror-wrap pre.CodeMirror-line-like {
  word-wrap: break-word;
  white-space: pre-wrap;
  word-break: normal;
}

.CodeMirror-linebackground {
  position: absolute;
  left: 0; right: 0; top: 0; bottom: 0;
  z-index: 0;
}

.CodeMirror-linewidget {
  position: relative;
  z-index: 2;
  padding: 0.1px; /* Force widget margins to stay inside of the container */
}

.CodeMirror-widget {}

.CodeMirror-rtl pre { direction: rtl; }

.CodeMirror-code {
  outline: none;
}

/* Force content-box sizing for the elements where we expect it */
.CodeMirror-scroll,
.CodeMirror-sizer,
.CodeMirror-gutter,
.CodeMirror-gutters,
.CodeMirror-linenumber {
  -moz-box-sizing: content-box;
  box-sizing: content-box;
}

.CodeMirror-measure {
  position: absolute;
  width: 100%;
  height: 0;
  overflow: hidden;
  visibility: hidden;
}

.CodeMirror-cursor {
  position: absolute;
  pointer-events: none;
}
.CodeMirror-measure pre { position: static; }

div.CodeMirror-cursors {
  visibility: hidden;
  position: relative;
  z-index: 3;
}
div.CodeMirror-dragcursors {
  visibility: visible;
}

.CodeMirror-focused div.CodeMirror-cursors {
  visibility: visible;
}

.CodeMirror-selected { background: #d9d9d9; }
.CodeMirror-focused .CodeMirror-selected { background: #d7d4f0; }
.CodeMirror-crosshair { cursor: crosshair; }
.CodeMirror-line::selection, .CodeMirror-line > span::selection, .CodeMirror-line > span > span::selection { background: #d7d4f0; }
.CodeMirror-line::-moz-selection, .CodeMirror-line > span::-moz-selection, .CodeMirror-line > span > span::-moz-selection { background: #d7d4f0; }

.cm-searching {
  background-color: #ffa;
  background-color: rgba(255, 255, 0, .4);
}

/* Used to force a border model for a node */
.cm-force-border { padding-right: .1px; }

@media print {
  /* Hide the cursor when printing */
  .CodeMirror div.CodeMirror-cursors {
    visibility: hidden;
  }
}

/* See issue #2901 */
.cm-tab-wrap-hack:after { content: ''; }

/* Help users use markselection to safely style text background */
span.CodeMirror-selectedtext { background: none; }

.CodeMirror-dialog {
  position: absolute;
  left: 0; right: 0;
  background: inherit;
  z-index: 15;
  padding: .1em .8em;
  overflow: hidden;
  color: inherit;
}

.CodeMirror-dialog-top {
  border-bottom: 1px solid #eee;
  top: 0;
}

.CodeMirror-dialog-bottom {
  border-top: 1px solid #eee;
  bottom: 0;
}

.CodeMirror-dialog input {
  border: none;
  outline: none;
  background: transparent;
  width: 20em;
  color: inherit;
  font-family: monospace;
}

.CodeMirror-dialog button {
  font-size: 70%;
}

.CodeMirror-foldmarker {
  color: blue;
  text-shadow: #b9f 1px 1px 2px, #b9f -1px -1px 2px, #b9f 1px -1px 2px, #b9f -1px 1px 2px;
  font-family: arial;
  line-height: .3;
  cursor: pointer;
}
.CodeMirror-foldgutter {
  width: .7em;
}
.CodeMirror-foldgutter-open,
.CodeMirror-foldgutter-folded {
  cursor: pointer;
}
.CodeMirror-foldgutter-open:after {
  content: "\25BE";
}
.CodeMirror-foldgutter-folded:after {
  content: "\25B8";
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.CodeMirror {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;
  /* Changed to auto to autogrow */
}

.CodeMirror pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* This causes https://github.com/jupyter/jupyterlab/issues/522 */
/* May not cause it not because we changed it! */
.CodeMirror-lines {
  padding: var(--jp-code-padding) 0;
}

.CodeMirror-linenumber {
  padding: 0 8px;
}

.jp-CodeMirrorEditor {
  cursor: text;
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.CodeMirror.jp-mod-readOnly .CodeMirror-cursor {
  display: none;
}

.CodeMirror-gutters {
  border-right: 1px solid var(--jp-border-color2);
  background-color: var(--jp-layout-color0);
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.CodeMirror-selectedtext.cm-searching {
  background-color: var(--jp-search-selected-match-background-color) !important;
  color: var(--jp-search-selected-match-color) !important;
}

.cm-searching {
  background-color: var(
    --jp-search-unselected-match-background-color
  ) !important;
  color: var(--jp-search-unselected-match-color) !important;
}

.CodeMirror-focused .CodeMirror-selected {
  background-color: var(--jp-editor-selected-focused-background);
}

.CodeMirror-selected {
  background-color: var(--jp-editor-selected-background);
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/**
 * Here is our jupyter theme for CodeMirror syntax highlighting
 * This is used in our marked.js syntax highlighting and CodeMirror itself
 * The string "jupyter" is set in ../codemirror/widget.DEFAULT_CODEMIRROR_THEME
 * This came from the classic notebook, which came form highlight.js/GitHub
 */

/**
 * CodeMirror themes are handling the background/color in this way. This works
 * fine for CodeMirror editors outside the notebook, but the notebook styles
 * these things differently.
 */
.CodeMirror.cm-s-jupyter {
  background: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* In the notebook, we want this styling to be handled by its container */
.jp-CodeConsole .CodeMirror.cm-s-jupyter,
.jp-Notebook .CodeMirror.cm-s-jupyter {
  background: transparent;
}

.cm-s-jupyter .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}
.cm-s-jupyter span.cm-keyword {
  color: var(--jp-mirror-editor-keyword-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-atom {
  color: var(--jp-mirror-editor-atom-color);
}
.cm-s-jupyter span.cm-number {
  color: var(--jp-mirror-editor-number-color);
}
.cm-s-jupyter span.cm-def {
  color: var(--jp-mirror-editor-def-color);
}
.cm-s-jupyter span.cm-variable {
  color: var(--jp-mirror-editor-variable-color);
}
.cm-s-jupyter span.cm-variable-2 {
  color: var(--jp-mirror-editor-variable-2-color);
}
.cm-s-jupyter span.cm-variable-3 {
  color: var(--jp-mirror-editor-variable-3-color);
}
.cm-s-jupyter span.cm-punctuation {
  color: var(--jp-mirror-editor-punctuation-color);
}
.cm-s-jupyter span.cm-property {
  color: var(--jp-mirror-editor-property-color);
}
.cm-s-jupyter span.cm-operator {
  color: var(--jp-mirror-editor-operator-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-comment {
  color: var(--jp-mirror-editor-comment-color);
  font-style: italic;
}
.cm-s-jupyter span.cm-string {
  color: var(--jp-mirror-editor-string-color);
}
.cm-s-jupyter span.cm-string-2 {
  color: var(--jp-mirror-editor-string-2-color);
}
.cm-s-jupyter span.cm-meta {
  color: var(--jp-mirror-editor-meta-color);
}
.cm-s-jupyter span.cm-qualifier {
  color: var(--jp-mirror-editor-qualifier-color);
}
.cm-s-jupyter span.cm-builtin {
  color: var(--jp-mirror-editor-builtin-color);
}
.cm-s-jupyter span.cm-bracket {
  color: var(--jp-mirror-editor-bracket-color);
}
.cm-s-jupyter span.cm-tag {
  color: var(--jp-mirror-editor-tag-color);
}
.cm-s-jupyter span.cm-attribute {
  color: var(--jp-mirror-editor-attribute-color);
}
.cm-s-jupyter span.cm-header {
  color: var(--jp-mirror-editor-header-color);
}
.cm-s-jupyter span.cm-quote {
  color: var(--jp-mirror-editor-quote-color);
}
.cm-s-jupyter span.cm-link {
  color: var(--jp-mirror-editor-link-color);
}
.cm-s-jupyter span.cm-error {
  color: var(--jp-mirror-editor-error-color);
}
.cm-s-jupyter span.cm-hr {
  color: #999;
}

.cm-s-jupyter span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}

.cm-s-jupyter .CodeMirror-activeline-background,
.cm-s-jupyter .CodeMirror-gutter {
  background-color: var(--jp-layout-color2);
}

/* Styles for shared cursors (remote cursor locations and selected ranges) */
.jp-CodeMirrorEditor .remote-caret {
  position: relative;
  border-left: 2px solid black;
  margin-left: -1px;
  margin-right: -1px;
  box-sizing: border-box;
}

.jp-CodeMirrorEditor .remote-caret > div {
  white-space: nowrap;
  position: absolute;
  top: -1.15em;
  padding-bottom: 0.05em;
  left: -2px;
  font-size: 0.95em;
  background-color: rgb(250, 129, 0);
  font-family: var(--jp-ui-font-family);
  font-weight: bold;
  line-height: normal;
  user-select: none;
  color: white;
  padding-left: 2px;
  padding-right: 2px;
  z-index: 3;
  transition: opacity 0.3s ease-in-out;
}

.jp-CodeMirrorEditor .remote-caret.hide-name > div {
  transition-delay: 0.7s;
  opacity: 0;
}

.jp-CodeMirrorEditor .remote-caret:hover > div {
  opacity: 1;
  transition-delay: 0s;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

:root {
  /* This is the padding value to fill the gaps between lines containing spans with background color. */
  --jp-private-code-span-padding: calc(
    (var(--jp-code-line-height) - 1) * var(--jp-code-font-size) / 2
  );
}

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0px;
  padding: 0px;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}
.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}
.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}
.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}
.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0em;
}

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: 12px;
  table-layout: fixed;
  margin-left: auto;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon table {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0px;
}

.jp-RenderedHTMLCommon p {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}
/* ...or leave it untouched if they don't */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-dark-background {
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-light-background {
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}
.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}
.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}
.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}
.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}
.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}
.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}
.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}
.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: 0.8em;
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser {
  display: flex;
  flex-direction: column;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  border-bottom: none;
  height: auto;
  margin: var(--jp-toolbar-header-margin);
  box-shadow: none;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 8px 12px 8px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0px 2px;
  padding: 0px 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0px;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar.jp-Toolbar {
  padding: 0px;
  margin: 8px 12px 0px 12px;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  justify-content: flex-start;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-Toolbar-item {
  flex: 0 0 auto;
  padding-left: 0px;
  padding-right: 2px;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-ToolbarButtonComponent {
  width: 40px;
}

.jp-FileBrowser-toolbar.jp-Toolbar
  .jp-Toolbar-item:first-child
  .jp-ToolbarButtonComponent {
  width: 72px;
  background: var(--jp-brand-color1);
}

.jp-FileBrowser-toolbar.jp-Toolbar
  .jp-Toolbar-item:first-child
  .jp-ToolbarButtonComponent:focus-visible {
  background-color: var(--jp-brand-color0);
}

.jp-FileBrowser-toolbar.jp-Toolbar
  .jp-Toolbar-item:first-child
  .jp-ToolbarButtonComponent
  .jp-icon3 {
  fill: white;
}

/*-----------------------------------------------------------------------------
| Other styles
|----------------------------------------------------------------------------*/

.jp-FileDialog.jp-mod-conflict input {
  color: var(--jp-error-color1);
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

.jp-LastModified-hidden {
  display: none;
}

.jp-FileBrowser-filterBox {
  padding: 0px;
  flex: 0 0 auto;
  margin: 8px 12px 0px 12px;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing:focus-visible {
  border: 1px solid var(--jp-brand-color1);
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px 12px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-id-narrow {
  display: none;
  flex: 0 0 5px;
  padding: 4px 4px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
  color: var(--jp-border-color2);
}

.jp-DirListing-narrow .jp-id-narrow {
  display: block;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-DirListing-content mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.jp-DirListing-content .jp-DirListing-item.jp-mod-selected mark {
  color: var(--jp-ui-inverse-font-color0);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-item[data-is-dot] {
  opacity: 75%;
}

.jp-DirListing-item.jp-mod-selected {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon:before {
  color: var(--jp-success-color1);
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.jp-mod-running.jp-mod-selected
  .jp-DirListing-itemIcon:before {
  color: var(--jp-ui-inverse-font-color1);
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0px;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-DirListing-deadSpace {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
}

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: flex;
  flex-direction: row;
}

body[data-format='mobile'] .jp-OutputArea-child {
  flex-direction: column;
}

.jp-OutputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

body[data-format='mobile'] .jp-OutputPrompt {
  flex: 0 0 auto;
  text-align: left;
}

.jp-OutputArea-output {
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea-child .jp-OutputArea-output {
  flex-grow: 1;
  flex-shrink: 1;
}

body[data-format='mobile'] .jp-OutputArea-child .jp-OutputArea-output {
  margin-left: var(--jp-notebook-padding);
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0px;
  padding: 0px;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0px;
  flex: 1 1 auto;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
  border-top: var(--jp-border-width) solid transparent;
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-OutputArea-stdin {
  line-height: var(--jp-code-line-height);
  padding-top: var(--jp-code-padding);
  display: flex;
}

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;
  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0px;
  bottom: 0px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0px;
  width: 100%;
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: flex;
  flex-direction: row;
  overflow: hidden;
}

body[data-format='mobile'] .jp-InputArea {
  flex-direction: column;
}

.jp-InputArea-editor {
  flex: 1 1 auto;
  overflow: hidden;
}

.jp-InputArea-editor {
  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0px;
  background: var(--jp-cell-editor-background);
}

body[data-format='mobile'] .jp-InputArea-editor {
  margin-left: var(--jp-notebook-padding);
}

.jp-InputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

body[data-format='mobile'] .jp-InputPrompt {
  flex: 0 0 auto;
  text-align: left;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: flex;
  flex-direction: row;
  flex: 1 1 auto;
}

.jp-Placeholder-prompt {
  box-sizing: border-box;
}

.jp-Placeholder-content {
  flex: 1 1 auto;
  border: none;
  background: transparent;
  height: 20px;
  box-sizing: border-box;
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0px;
  margin: 0px;
  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 200px;
  box-shadow: inset 0 0 6px 2px rgba(0, 0, 0, 0.3);
  margin-left: var(--jp-private-cell-scrolling-output-offset);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  flex: 0 0
    calc(
      var(--jp-cell-prompt-width) -
        var(--jp-private-cell-scrolling-output-offset)
    );
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  flex: 1 1 auto;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

.jp-showHiddenCellsButton {
  margin-left: calc(var(--jp-cell-prompt-width) + 2 * var(--jp-code-padding));
  margin-top: var(--jp-code-padding);
  border: 1px solid var(--jp-border-color2);
  background-color: var(--jp-border-color3) !important;
  color: var(--jp-content-font-color0) !important;
}

.jp-showHiddenCellsButton:hover {
  background-color: var(--jp-border-color2) !important;
}

.jp-collapseHeadingButton {
  display: none;
}

.jp-MarkdownCell:hover .jp-collapseHeadingButton {
  display: flex;
  min-height: var(--jp-cell-collapser-min-height);
  position: absolute;
  right: 0;
  top: 0;
  bottom: 0;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: 2px;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-MainAreaWidget-ContainStrict .jp-Notebook * {
  contain: strict;
}

.jp-Notebook-render * {
  contain: none !important;
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
  float: left;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* cell is dirty */
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt {
  color: var(--jp-warn-color1);
}
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt:before {
  color: var(--jp-warn-color1);
  content: '•';
}

.jp-Notebook .jp-Cell.jp-mod-active.jp-mod-dirty .jp-Collapser {
  background: var(--jp-warn-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: block;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0px;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-NotebookTools-tool {
  padding: 0px 12px 0 12px;
}

.jp-ActiveCellTool {
  padding: 12px;
  background-color: var(--jp-layout-color1);
  border-top: none !important;
}

.jp-ActiveCellTool .jp-InputArea-prompt {
  flex: 0 0 auto;
  padding-left: 0px;
}

.jp-ActiveCellTool .jp-InputArea-editor {
  flex: 1 1 auto;
  background: var(--jp-cell-editor-background);
  border-color: var(--jp-cell-editor-border-color);
}

.jp-ActiveCellTool .jp-InputArea-editor .CodeMirror {
  background: transparent;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0px 12px 0px;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label {
  line-height: 1.4;
}

.jp-NotebookTools .jp-select-wrapper {
  margin-top: 4px;
  margin-bottom: 0px;
}

.jp-NotebookTools .jp-Collapse {
  margin-top: 16px;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Cell-Placeholder {
  padding-left: 55px;
}

.jp-Cell-Placeholder-wrapper {
  background: #fff;
  border: 1px solid;
  border-color: #e5e6e9 #dfe0e4 #d0d1d5;
  border-radius: 4px;
  -webkit-border-radius: 4px;
  margin: 10px 15px;
}

.jp-Cell-Placeholder-wrapper-inner {
  padding: 15px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body {
  background-repeat: repeat;
  background-size: 50% auto;
}

.jp-Cell-Placeholder-wrapper-body div {
  background: #f6f7f8;
  background-image: -webkit-linear-gradient(
    left,
    #f6f7f8 0%,
    #edeef1 20%,
    #f6f7f8 40%,
    #f6f7f8 100%
  );
  background-repeat: no-repeat;
  background-size: 800px 104px;
  height: 104px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body div {
  position: absolute;
  right: 15px;
  left: 15px;
  top: 15px;
}

div.jp-Cell-Placeholder-h1 {
  top: 20px;
  height: 20px;
  left: 15px;
  width: 150px;
}

div.jp-Cell-Placeholder-h2 {
  left: 15px;
  top: 50px;
  height: 10px;
  width: 100px;
}

div.jp-Cell-Placeholder-content-1,
div.jp-Cell-Placeholder-content-2,
div.jp-Cell-Placeholder-content-3 {
  left: 15px;
  right: 15px;
  height: 10px;
}

div.jp-Cell-Placeholder-content-1 {
  top: 100px;
}

div.jp-Cell-Placeholder-content-2 {
  top: 120px;
}

div.jp-Cell-Placeholder-content-3 {
  top: 140px;
}

</style>

    <style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0px 2px 1px -1px var(--jp-shadow-umbra-color),
    0px 1px 1px 0px var(--jp-shadow-penumbra-color),
    0px 1px 3px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0px 3px 1px -2px var(--jp-shadow-umbra-color),
    0px 2px 2px 0px var(--jp-shadow-penumbra-color),
    0px 1px 5px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0px 2px 4px -1px var(--jp-shadow-umbra-color),
    0px 4px 5px 0px var(--jp-shadow-penumbra-color),
    0px 1px 10px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0px 3px 5px -1px var(--jp-shadow-umbra-color),
    0px 6px 10px 0px var(--jp-shadow-penumbra-color),
    0px 1px 18px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0px 5px 5px -3px var(--jp-shadow-umbra-color),
    0px 8px 10px 1px var(--jp-shadow-penumbra-color),
    0px 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0px 7px 8px -4px var(--jp-shadow-umbra-color),
    0px 12px 17px 2px var(--jp-shadow-penumbra-color),
    0px 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0px 8px 10px -5px var(--jp-shadow-umbra-color),
    0px 16px 24px 2px var(--jp-shadow-penumbra-color),
    0px 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0px 10px 13px -6px var(--jp-shadow-umbra-color),
    0px 20px 31px 3px var(--jp-shadow-penumbra-color),
    0px 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0px 11px 15px -7px var(--jp-shadow-umbra-color),
    0px 24px 38px 3px var(--jp-shadow-penumbra-color),
    0px 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;

  --jp-ui-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica,
    Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;

  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);

  --jp-content-link-color: var(--md-blue-700);

  --jp-content-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: Menlo, Consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-900);
  --jp-brand-color1: var(--md-blue-700);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);

  --jp-accent-color0: var(--md-green-900);
  --jp-accent-color1: var(--md-green-700);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-900);
  --jp-warn-color1: var(--md-orange-700);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);

  --jp-error-color0: var(--md-red-900);
  --jp-error-color1: var(--md-red-700);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);

  --jp-success-color0: var(--md-green-900);
  --jp-success-color1: var(--md-green-700);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);

  --jp-info-color0: var(--md-cyan-900);
  --jp-info-color1: var(--md-cyan-700);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;

  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;

  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);

  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: var(--jp-code-font-family-default);
  --jp-cell-prompt-letter-spacing: 0px;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);
  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;
  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0px 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Statusbar specific styles */

  --jp-statusbar-height: 24px;

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-border-color1);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: #05a;
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #aa22ff;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #aa22ff;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 250px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);
}
</style>

<style type="text/css">
/* Force rendering true colors when outputing to pdf */
* {
  -webkit-print-color-adjust: exact;
}

/* Misc */
a.anchor-link {
  display: none;
}

.highlight  {
  margin: 0.4em;
}

/* Input area styling */
.jp-InputArea {
  overflow: hidden;
}

.jp-InputArea-editor {
  overflow: hidden;
}

.CodeMirror pre {
  margin: 0;
  padding: 0;
}

/* Using table instead of flexbox so that we can use break-inside property */
/* CSS rules under this comment should not be required anymore after we move to the JupyterLab 4.0 CSS */


.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  min-width: calc(
    var(--jp-cell-prompt-width) - var(--jp-private-cell-scrolling-output-offset)
  );
}

.jp-OutputArea-child {
  display: table;
  width: 100%;
}

.jp-OutputPrompt {
  display: table-cell;
  vertical-align: top;
  min-width: var(--jp-cell-prompt-width);
}

body[data-format='mobile'] .jp-OutputPrompt {
  display: table-row;
}

.jp-OutputArea-output {
  display: table-cell;
  width: 100%;
}

body[data-format='mobile'] .jp-OutputArea-child .jp-OutputArea-output {
  display: table-row;
}

.jp-OutputArea-output.jp-OutputArea-executeResult {
  width: 100%;
}

/* Hiding the collapser by default */
.jp-Collapser {
  display: none;
}

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }

  .jp-OutputArea-child {
    break-inside: avoid-page;
  }
}
</style>

<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-AMS_CHTML-full,Safe"> </script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: {
                    automatic: true
                    }
                }
            });

            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
    <!-- End of mathjax configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">

<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Chapter-No-%23-7-Functions"><span style="color:green, font-family; times, serif; font-size:30pt; font-style:italic">Chapter No # 7 <u>Functions</u></span><a class="anchor-link" href="#Chapter-No-%23-7-Functions">&#182;</a></h1><ul>
<li>What is function</li>
<li>Syntax Of Function,</li>
<li>Writing And Calling Functions</li>
<li>One Parameter &amp; One Argument Function,</li>
<li>Two Parameter &amp; Two Argument Function,</li>
<li>Three Parameter &amp; Three Argument Function,</li>
<li>Four Parameter &amp; Four Argument Function,</li>
<li>Multiple Parameter &amp; Multiple Arguments,</li>
<li>**Args Functions,</li>
<li>**Kwargs Functions,</li>
<li>Local And Global Variable</li>
<li>Nested Functions,</li>
<li>Making Library With Functions,</li>
<li>Built-In Function,</li>
<li>Mudules,</li>
<li>Annonymous Function</li>
<li>Map, Filter &amp; Reduce Function</li>
<li>Decorators</li>
</ul>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="What-is-Functions"><li style="font-size:20pt;">What is Functions</li><a class="anchor-link" href="#What-is-Functions">&#182;</a></h1><p>Functions in Python provide organized, reusable and modular code to perform a set of specific actions. Functions
simplify the coding process, prevent redundant logic, and make the code easier to follow. This topic describes the
declaration and utilization of functions in Python.</p>
<p>Python has many built-in functions like <span style="color: orange;"><b>print()</b></span>.,<span style="color: green;"><b>input()</b></span>, <span style="color: blue;"><b>len()</b></span>. Besides built-ins you can also create your own
functions to do more specific jobs—these are called user-defined functions.</p>
<h1 id="Syntax-Of-Function"><li style="font-size:20pt;">Syntax Of Function</li><a class="anchor-link" href="#Syntax-Of-Function">&#182;</a></h1><pre>
def function_name(parameter):
    """doc string"""
    expression
    statement(s)

</pre>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Writing-And-Calling-Functions"><li style="font-size:20pt;">Writing And Calling Functions</li><a class="anchor-link" href="#Writing-And-Calling-Functions">&#182;</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[176]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">square</span><span class="p">():</span> <span class="c1">#function to find square of a number</span>
    <span class="sd">"""This function is used for only square"""</span>  <span class="c1"># """doc string"""</span>
    <span class="n">x</span> <span class="o">=</span> <span class="mi">2</span><span class="o">**</span><span class="mi">2</span>  <span class="c1"># epression</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>  <span class="c1"># statement</span>

<span class="n">square</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>4
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[177]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">myfunc</span><span class="p">():</span> <span class="c1"># function with no parameter</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"Hello, I'm from function"</span><span class="p">)</span> <span class="c1"># statement</span>
    
<span class="n">myfunc</span><span class="p">()</span> <span class="c1"># calling the function | function with no argument</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Hello, I&#39;m from function
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[178]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">greet</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"Hello"</span><span class="p">)</span>
    
<span class="n">greet</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Hello
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[179]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">greeting</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"This is the 1st program of function"</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"It is building block"</span><span class="p">)</span>
<span class="n">greeting</span><span class="p">()</span> <span class="c1"># Calling function</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>This is the 1st program of function
It is building block
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[180]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">myfunc</span><span class="p">():</span> <span class="c1"># function with no parameters</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"Hello Python programmers"</span><span class="p">)</span>
<span class="n">myfunc</span><span class="p">()</span> <span class="c1"># function with no arguments</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Hello Python programmers
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[181]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">myfunc</span><span class="p">():</span> <span class="c1"># function with no parameters</span>
    <span class="n">x</span> <span class="o">=</span> <span class="mi">5</span>
    <span class="n">y</span> <span class="o">=</span> <span class="mi">20</span>
    <span class="n">z</span> <span class="o">=</span> <span class="n">x</span> <span class="o">+</span> <span class="n">y</span> <span class="c1"># expression</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"Total of z is: "</span><span class="p">,</span><span class="n">z</span><span class="p">)</span>
<span class="n">myfunc</span><span class="p">()</span> <span class="c1"># function with no arguments</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Total of z is:  25
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[182]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">myfunc</span><span class="p">():</span> <span class="c1"># function with no parameters</span>
    <span class="n">name</span> <span class="o">=</span> <span class="s2">"Python"</span>
    <span class="n">call</span> <span class="o">=</span> <span class="s2">"Hello "</span><span class="o">+</span> <span class="n">name</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">call</span><span class="p">)</span>
<span class="n">myfunc</span><span class="p">()</span> <span class="c1"># function with no arguments</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Hello Python
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1><li style="font-size:20pt;">One Parameter & One Argument Function</li></h1>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[183]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">myfunc</span><span class="p">(</span><span class="n">fname</span><span class="p">):</span> <span class="c1"># function with one paramenter</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"First Name "</span><span class="o">+</span> <span class="n">fname</span><span class="p">)</span>

<span class="n">myfunc</span><span class="p">(</span><span class="s2">"Asad"</span><span class="p">)</span> <span class="c1"># function with one argument</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>First Name Asad
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[184]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">myfunc</span><span class="p">(</span><span class="n">fname</span><span class="p">):</span> <span class="c1"># function with one paramenter</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"First Name "</span><span class="o">+</span> <span class="n">fname</span><span class="p">)</span>

<span class="n">myfunc</span><span class="p">()</span> <span class="c1"># function with one argument</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>
<span class="ansi-red-intense-fg ansi-bold">---------------------------------------------------------------------------</span>
<span class="ansi-red-intense-fg ansi-bold">TypeError</span>                                 Traceback (most recent call last)
<span class="ansi-green-intense-fg ansi-bold">~\AppData\Local\Temp\ipykernel_11484\1021635956.py</span> in <span class="ansi-cyan-fg">&lt;module&gt;</span>
<span class="ansi-green-fg">      2</span>     print<span class="ansi-yellow-intense-fg ansi-bold">(</span><span class="ansi-blue-intense-fg ansi-bold">&#34;First Name &#34;</span><span class="ansi-yellow-intense-fg ansi-bold">+</span> fname<span class="ansi-yellow-intense-fg ansi-bold">)</span>
<span class="ansi-green-fg">      3</span> 
<span class="ansi-green-intense-fg ansi-bold">----&gt; 4</span><span class="ansi-yellow-intense-fg ansi-bold"> </span>myfunc<span class="ansi-yellow-intense-fg ansi-bold">(</span><span class="ansi-yellow-intense-fg ansi-bold">)</span> <span class="ansi-red-intense-fg ansi-bold"># function with one argument</span>

<span class="ansi-red-intense-fg ansi-bold">TypeError</span>: myfunc() missing 1 required positional argument: &#39;fname&#39;</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">square</span> <span class="p">(</span><span class="n">n</span><span class="p">):</span> <span class="c1">#function to find square of a number</span>
    <span class="sd">"""This function is used for only square"""</span>
    <span class="n">n</span><span class="o">=</span> <span class="n">n</span><span class="o">*</span><span class="n">n</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">n</span><span class="p">)</span>

<span class="n">square</span><span class="p">(</span><span class="mi">20</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">even_odd</span> <span class="p">(</span><span class="n">num</span><span class="p">):</span> <span class="c1">#Even odd test</span>
    <span class="sd">""" This function will check whether a number is even or odd"""</span>
    <span class="k">if</span> <span class="n">num</span> <span class="o">%</span> <span class="mi">2</span> <span class="o">==</span><span class="mi">0</span><span class="p">:</span>
        <span class="nb">print</span> <span class="p">(</span><span class="n">num</span><span class="p">,</span> <span class="s1">' is even number'</span><span class="p">)</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="nb">print</span> <span class="p">(</span><span class="n">num</span><span class="p">,</span> <span class="s1">' is odd number'</span><span class="p">)</span>
<span class="n">even_odd</span><span class="p">(</span><span class="mi">40</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">get</span><span class="p">(</span><span class="n">name</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"Name: "</span><span class="p">,</span><span class="n">name</span><span class="p">)</span>
    
<span class="n">a</span><span class="o">=</span><span class="nb">input</span><span class="p">(</span><span class="s2">"Enter Name: "</span><span class="p">)</span>

<span class="n">get</span><span class="p">(</span><span class="n">a</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">greet_two</span><span class="p">(</span><span class="n">greeting</span><span class="o">=</span><span class="s2">"Howdy"</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">greeting</span><span class="p">)</span>
<span class="n">greet_two</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">factorial</span><span class="p">(</span><span class="n">num</span><span class="p">):</span> <span class="c1"># Calculate factorial of a number using recursive function c 4x3x2x1=24</span>
    <span class="k">if</span> <span class="n">num</span> <span class="o">&lt;=</span><span class="mi">1</span> <span class="p">:</span>
        <span class="k">return</span> <span class="mi">1</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="k">return</span> <span class="n">num</span> <span class="o">*</span> <span class="n">factorial</span><span class="p">(</span><span class="n">num</span><span class="o">-</span><span class="mi">1</span><span class="p">)</span>

<span class="n">factorial</span><span class="p">(</span><span class="mi">4</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1><li style="font-size:20pt;">Two Parameter & Two Argument Function</li></h1>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">details</span><span class="p">(</span><span class="n">name</span><span class="p">,</span><span class="n">userid</span><span class="p">):</span> <span class="c1"># Function to print User details</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'Name :- '</span><span class="p">,</span> <span class="n">name</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">'User ID is :- '</span><span class="p">,</span> <span class="n">userid</span><span class="p">)</span>
    
<span class="n">details</span><span class="p">(</span><span class="s1">'Raheel'</span><span class="p">,</span><span class="mi">12312313123</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">addition</span><span class="p">(</span><span class="n">a</span><span class="p">,</span><span class="n">b</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The first value is: "</span><span class="p">,</span><span class="n">a</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The second value is: "</span><span class="p">,</span><span class="n">b</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The result is: "</span><span class="p">,</span><span class="n">a</span><span class="o">+</span><span class="n">b</span><span class="p">)</span>
<span class="n">addition</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">20</span><span class="p">)</span> <span class="c1"># Calling function</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">info</span><span class="p">(</span><span class="n">fname</span><span class="p">,</span> <span class="n">lname</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"First Name: "</span><span class="p">,</span><span class="n">fname</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"Last Name: "</span><span class="p">,</span><span class="n">lname</span><span class="p">)</span>
    
<span class="n">info</span><span class="p">(</span><span class="s2">"Raheel"</span><span class="p">,</span><span class="s2">"Naseem"</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[185]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">add_numbers</span><span class="p">(</span><span class="n">first_number</span><span class="p">,</span> <span class="n">second_number</span><span class="p">):</span>
    <span class="n">total</span> <span class="o">=</span> <span class="n">first_number</span> <span class="o">+</span> <span class="n">second_number</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">total</span><span class="p">)</span>
<span class="n">add_numbers</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span><span class="mi">8</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>10
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[186]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">AreaPerameter</span><span class="p">(</span><span class="n">a</span><span class="p">,</span><span class="n">b</span><span class="p">):</span>
    <span class="n">a</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">a</span><span class="p">)</span>
    <span class="n">b</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">b</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"Length is: "</span><span class="p">,</span><span class="n">a</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"Breadth is: "</span><span class="p">,</span><span class="n">b</span><span class="p">)</span>
    <span class="n">Area</span> <span class="o">=</span> <span class="n">a</span> <span class="o">*</span> <span class="n">b</span>
    <span class="n">Perameter</span> <span class="o">=</span> <span class="mi">2</span><span class="o">*</span><span class="n">a</span> <span class="o">+</span> <span class="mi">2</span><span class="o">*</span><span class="n">b</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The result of area is: "</span><span class="p">,</span><span class="n">Area</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The result of perameter is: "</span><span class="p">,</span><span class="n">Perameter</span><span class="p">)</span>
    <span class="k">return</span>

<span class="n">h</span> <span class="o">=</span> <span class="nb">input</span><span class="p">(</span><span class="s2">"Enter length "</span><span class="p">)</span>
<span class="n">w</span> <span class="o">=</span> <span class="nb">input</span><span class="p">(</span><span class="s2">"Enter width "</span><span class="p">)</span>
<span class="n">AreaPerameter</span><span class="p">(</span><span class="n">h</span><span class="p">,</span><span class="n">w</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Enter length 12
Enter width 8
Length is:  12
Breadth is:  8
The result of area is:  96
The result of perameter is:  40
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[187]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">"-----Addition-----"</span><span class="p">)</span>
<span class="k">def</span> <span class="nf">addition</span><span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The first value is: "</span><span class="p">,</span><span class="n">x</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The second value is: "</span><span class="p">,</span><span class="n">y</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The result is: "</span><span class="p">,</span><span class="n">x</span><span class="o">+</span><span class="n">y</span><span class="p">)</span>
<span class="n">addition</span><span class="p">(</span><span class="mi">100</span><span class="p">,</span><span class="mi">20</span><span class="p">)</span> <span class="c1"># Calling function</span>
<span class="nb">print</span><span class="p">()</span>
<span class="c1"># for subtraction</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"-----Subtraction-----"</span><span class="p">)</span>
<span class="k">def</span> <span class="nf">subtraction</span><span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The first value is: "</span><span class="p">,</span><span class="n">x</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The second value is: "</span><span class="p">,</span><span class="n">y</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The result is: "</span><span class="p">,</span><span class="n">x</span><span class="o">-</span><span class="n">y</span><span class="p">)</span>
<span class="n">subtraction</span><span class="p">(</span><span class="mi">50</span><span class="p">,</span><span class="mi">20</span><span class="p">)</span> <span class="c1"># Calling function</span>
<span class="nb">print</span><span class="p">()</span>
<span class="c1"># for multiplacation</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"-----Multiplacation-----"</span><span class="p">)</span>
<span class="k">def</span> <span class="nf">multiplacation</span><span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The first value is: "</span><span class="p">,</span><span class="n">x</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The second value is: "</span><span class="p">,</span><span class="n">y</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The result is: "</span><span class="p">,</span><span class="n">x</span><span class="o">*</span><span class="n">y</span><span class="p">)</span>
<span class="n">multiplacation</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span><span class="mi">10</span><span class="p">)</span> <span class="c1"># Calling function</span>
<span class="nb">print</span><span class="p">()</span>
<span class="c1"># for division</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"-----Division-----"</span><span class="p">)</span>
<span class="k">def</span> <span class="nf">division</span><span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The first value is: "</span><span class="p">,</span><span class="n">x</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The second value is: "</span><span class="p">,</span><span class="n">y</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The result is: "</span><span class="p">,</span><span class="n">x</span><span class="o">/</span><span class="n">y</span><span class="p">)</span>
<span class="n">division</span><span class="p">(</span><span class="mi">36</span><span class="p">,</span><span class="mi">4</span><span class="p">)</span> <span class="c1"># Calling function</span>
<span class="nb">print</span><span class="p">()</span>
<span class="c1"># for reminder</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"-----Reminder-----"</span><span class="p">)</span>
<span class="k">def</span> <span class="nf">reminder</span><span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The first value is: "</span><span class="p">,</span><span class="n">x</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The second value is: "</span><span class="p">,</span><span class="n">y</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The result is: "</span><span class="p">,</span><span class="n">x</span><span class="o">%</span><span class="k">y</span>)
<span class="n">reminder</span><span class="p">(</span><span class="mi">50</span><span class="p">,</span><span class="mi">20</span><span class="p">)</span> <span class="c1"># Calling function</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>-----Addition-----
The first value is:  100
The second value is:  20
The result is:  120

-----Subtraction-----
The first value is:  50
The second value is:  20
The result is:  30

-----Multiplacation-----
The first value is:  5
The second value is:  10
The result is:  50

-----Division-----
The first value is:  36
The second value is:  4
The result is:  9.0

-----Reminder-----
The first value is:  50
The second value is:  20
The result is:  10
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1><li style="font-size:20pt;">Three Parameter & Three Argument Function</li></h1>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[188]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">fullname</span> <span class="p">(</span><span class="n">firstname</span> <span class="p">,</span> <span class="n">middlename</span> <span class="p">,</span><span class="n">lastname</span><span class="p">):</span> <span class="c1">#Concatenate Strings</span>
    <span class="n">fullname</span> <span class="o">=</span> <span class="s2">"</span><span class="si">{}</span><span class="s2"> </span><span class="si">{}</span><span class="s2"> </span><span class="si">{}</span><span class="s2">"</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">firstname</span><span class="p">,</span><span class="n">middlename</span><span class="p">,</span><span class="n">lastname</span><span class="p">)</span>
    <span class="nb">print</span> <span class="p">(</span><span class="n">fullname</span><span class="p">)</span>
<span class="n">fullname</span><span class="p">(</span><span class="s1">'Muhammad'</span> <span class="p">,</span> <span class="s1">'Raheel'</span> <span class="p">,</span> <span class="s1">'Naseem'</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Muhammad Raheel Naseem
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[189]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">fullname</span> <span class="p">(</span><span class="n">firstname</span> <span class="p">,</span> <span class="n">middlename</span> <span class="p">,</span><span class="n">lastname</span><span class="p">):</span> <span class="c1">#Concatenate Strings</span>
    <span class="n">fullname</span> <span class="o">=</span> <span class="s2">"</span><span class="si">{}</span><span class="s2"> </span><span class="si">{}</span><span class="s2"> </span><span class="si">{}</span><span class="s2">"</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">firstname</span><span class="p">,</span><span class="n">middlename</span><span class="p">,</span><span class="n">lastname</span><span class="p">)</span>
    <span class="nb">print</span> <span class="p">(</span><span class="n">fullname</span><span class="p">)</span>
<span class="n">fullname</span><span class="p">(</span><span class="n">lastname</span> <span class="o">=</span> <span class="s1">'Bhat'</span> <span class="p">,</span> <span class="n">middlename</span><span class="o">=</span><span class="s1">'Ali'</span> <span class="p">,</span> <span class="n">firstname</span><span class="o">=</span><span class="s1">'Asif'</span><span class="p">)</span> 
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Asif Ali Bhat
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1><li style="font-size:20pt;">Multiple Parameter & Multiple Arguments Using "**args"</li></h1>
<p><code>**args</code></p>
<p><em>args allows us to pass a variable number of non-keyword arguments to a Python function. In the function, we should use an asterisk (</em>) before the parameter name to specify how many arguments we want to pass to the function.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[190]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">func1</span><span class="p">(</span><span class="o">*</span><span class="n">args</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">args</span><span class="p">)</span>
<span class="n">func1</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">3</span><span class="p">,</span><span class="mi">4</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">6</span><span class="p">,</span><span class="mi">7</span><span class="p">,</span><span class="mi">8</span><span class="p">,</span><span class="mi">9</span><span class="p">,</span><span class="mi">10</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[191]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">func1</span><span class="p">(</span><span class="o">*</span><span class="n">args</span><span class="p">):</span>
    <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">args</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<span class="n">func1</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">3</span><span class="p">,</span><span class="mi">4</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">6</span><span class="p">,</span><span class="mi">7</span><span class="p">,</span><span class="mi">8</span><span class="p">,</span><span class="mi">9</span><span class="p">,</span><span class="mi">10</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>1
2
3
4
5
6
7
8
9
10
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[192]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">UserDetails</span><span class="p">(</span><span class="o">*</span><span class="n">args</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">args</span><span class="p">)</span>  
    
<span class="n">UserDetails</span><span class="p">(</span><span class="s2">"Raheel"</span><span class="p">,</span><span class="mi">23424</span><span class="p">,</span><span class="s2">"sdfsdfsdf"</span><span class="p">,</span><span class="mi">123123</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>(&#39;Raheel&#39;, 23424, &#39;sdfsdfsdf&#39;, 123123)
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[193]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">my_function</span><span class="p">(</span><span class="o">*</span><span class="n">prog</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"The youngest programming is "</span> <span class="o">+</span> <span class="n">prog</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>

<span class="n">my_function</span><span class="p">(</span><span class="s2">"Typescript"</span><span class="p">,</span> <span class="s2">"C++"</span><span class="p">,</span> <span class="s2">"Java"</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>The youngest programming is Typescript
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[194]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">func</span><span class="p">(</span><span class="o">*</span><span class="n">args</span><span class="p">):</span>
    <span class="c1"># args will be a tuple containing all values that are passed in</span>
    <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">args</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<span class="n">func</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="mi">3</span><span class="p">)</span> <span class="c1"># Calling it with 3 arguments</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>1
2
3
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1><li style="font-size:20pt;">Multiple Parameter & Multiple Arguments Using "**kwargs"</li></h1>
<p>Python uses a special syntax called kwargs in function definitions. It is used to pass through a keyworded, variable-length argument list. The double star in the name allows us to pass any number of arguments, or keywords, through a function's definition.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[195]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">UserDetails</span><span class="p">(</span><span class="o">**</span><span class="n">kwargs</span><span class="p">):</span> <span class="c1"># **kwards use only dictionary</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">kwargs</span><span class="p">)</span>
        
<span class="n">UserDetails</span><span class="p">(</span><span class="n">Name</span><span class="o">=</span><span class="s1">'Raheel'</span> <span class="p">,</span> <span class="n">ID</span><span class="o">=</span><span class="mi">7412</span> <span class="p">,</span> <span class="n">Pincode</span><span class="o">=</span><span class="mi">41102</span> <span class="p">,</span> <span class="n">Age</span><span class="o">=</span> <span class="mi">33</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>{&#39;Name&#39;: &#39;Raheel&#39;, &#39;ID&#39;: 7412, &#39;Pincode&#39;: 41102, &#39;Age&#39;: 33}
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[196]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">UserDetails</span><span class="p">(</span><span class="o">**</span><span class="n">kwargs</span><span class="p">):</span>
    <span class="k">for</span> <span class="n">key</span><span class="p">,</span><span class="n">val</span> <span class="ow">in</span> <span class="n">kwargs</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"</span><span class="si">{}</span><span class="s2"> :- </span><span class="si">{}</span><span class="s2">"</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="n">val</span><span class="p">))</span>
<span class="n">UserDetails</span><span class="p">(</span><span class="n">Name</span><span class="o">=</span><span class="s1">'Raheel'</span> <span class="p">,</span> <span class="n">ID</span><span class="o">=</span><span class="mi">7412</span> <span class="p">,</span> <span class="n">Pincode</span><span class="o">=</span><span class="mi">41102</span> <span class="p">,</span> <span class="n">Age</span><span class="o">=</span> <span class="mi">300</span> <span class="p">,</span> <span class="n">Country</span><span class="o">=</span> <span class="s1">'Pakistan'</span><span class="p">,</span><span class="n">language</span><span class="o">=</span><span class="s1">'Urdu'</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Name :- Raheel
ID :- 7412
Pincode :- 41102
Age :- 300
Country :- Pakistan
language :- Urdu
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[197]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">mydict</span> <span class="o">=</span> <span class="p">{</span><span class="s1">'Name'</span><span class="p">:</span> <span class="s1">'Asif'</span><span class="p">,</span> <span class="s1">'ID'</span><span class="p">:</span> <span class="mi">7412</span><span class="p">,</span> <span class="s1">'Pincode'</span><span class="p">:</span> <span class="mi">41102</span><span class="p">,</span> <span class="s1">'Age'</span><span class="p">:</span> <span class="mi">33</span><span class="p">,</span> <span class="s1">'Country'</span><span class="p">:</span> <span class="s2">"Pakistan"</span><span class="p">,</span><span class="s2">"language"</span><span class="p">:</span><span class="s2">"Urdu"</span><span class="p">}</span>
<span class="n">UserDetails</span><span class="p">(</span><span class="o">**</span><span class="n">mydict</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Name :- Asif
ID :- 7412
Pincode :- 41102
Age :- 33
Country :- Pakistan
language :- Urdu
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[198]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">intro</span><span class="p">(</span><span class="o">**</span><span class="n">data</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"</span><span class="se">\n</span><span class="s2">Data type of argument:"</span><span class="p">,</span><span class="nb">type</span><span class="p">(</span><span class="n">data</span><span class="p">))</span>

    <span class="k">for</span> <span class="n">key</span><span class="p">,</span> <span class="n">value</span> <span class="ow">in</span> <span class="n">data</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"</span><span class="si">{}</span><span class="s2"> is </span><span class="si">{}</span><span class="s2">"</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="n">value</span><span class="p">))</span>

<span class="n">intro</span><span class="p">(</span><span class="n">Firstname</span><span class="o">=</span><span class="s2">"Ali"</span><span class="p">,</span> <span class="n">Lastname</span><span class="o">=</span><span class="s2">"Imran"</span><span class="p">,</span> <span class="n">Age</span><span class="o">=</span><span class="mi">22</span><span class="p">,</span> <span class="n">Phone</span><span class="o">=</span><span class="mi">1234567890</span><span class="p">)</span>
<span class="n">intro</span><span class="p">(</span><span class="n">Firstname</span><span class="o">=</span><span class="s2">"John"</span><span class="p">,</span> <span class="n">Lastname</span><span class="o">=</span><span class="s2">"Malton"</span><span class="p">,</span> <span class="n">Email</span><span class="o">=</span><span class="s2">"johnmalton@nomail.com"</span><span class="p">,</span> <span class="n">Country</span><span class="o">=</span><span class="s2">"Wakanda"</span><span class="p">,</span> <span class="n">Age</span><span class="o">=</span><span class="mi">25</span><span class="p">,</span> <span class="n">Phone</span><span class="o">=</span><span class="mi">9876543210</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>
Data type of argument: &lt;class &#39;dict&#39;&gt;
Firstname is Ali
Lastname is Imran
Age is 22
Phone is 1234567890

Data type of argument: &lt;class &#39;dict&#39;&gt;
Firstname is John
Lastname is Malton
Email is johnmalton@nomail.com
Country is Wakanda
Age is 25
Phone is 9876543210
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Local-And-Global-Variable"><li style="font-size:20pt;">Local And Global Variable</li><a class="anchor-link" href="#Local-And-Global-Variable">&#182;</a></h1><h2 id="Local-Variable"><code>Local Variable</code><a class="anchor-link" href="#Local-Variable">&#182;</a></h2><p>In Python or any other programming languages, the definition of local variables remains the same, which is "A variable declared inside the function is called local function". We can access a local variable inside but not outside the function.</p>
<h2 id="Global-Variable"><code>Global Variable</code><a class="anchor-link" href="#Global-Variable">&#182;</a></h2><p>Python allows you to access global variables in a program both inside and outside of a function. A global variable in Python is often declared as the top of the program, or the beginning of a program.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[199]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">f</span><span class="p">():</span>
    <span class="c1"># local variable</span>
    <span class="n">s</span> <span class="o">=</span> <span class="s2">"I love Python"</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">s</span><span class="p">)</span>

<span class="n">f</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>I love Python
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[200]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">add</span><span class="p">():</span>
    <span class="n">c</span> <span class="o">=</span> <span class="mi">2</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>
<span class="n">add</span><span class="p">()</span> 
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>2
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[201]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">calling</span><span class="p">():</span>
    <span class="n">y</span><span class="o">=</span><span class="s2">"Hello: "</span><span class="p">,</span><span class="s2">"Python"</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">y</span><span class="p">)</span>
<span class="n">calling</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>(&#39;Hello: &#39;, &#39;Python&#39;)
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[202]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">c</span> <span class="o">=</span> <span class="mi">1</span>
<span class="k">def</span> <span class="nf">add</span><span class="p">():</span>
    <span class="n">c</span><span class="o">=</span><span class="n">c</span><span class="o">+</span><span class="mi">2</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>
<span class="n">add</span><span class="p">()</span> <span class="c1"># Raise Error its global scop </span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>
<span class="ansi-red-intense-fg ansi-bold">---------------------------------------------------------------------------</span>
<span class="ansi-red-intense-fg ansi-bold">UnboundLocalError</span>                         Traceback (most recent call last)
<span class="ansi-green-intense-fg ansi-bold">~\AppData\Local\Temp\ipykernel_11484\3093420356.py</span> in <span class="ansi-cyan-fg">&lt;module&gt;</span>
<span class="ansi-green-fg">      3</span>     c<span class="ansi-yellow-intense-fg ansi-bold">=</span>c<span class="ansi-yellow-intense-fg ansi-bold">+</span><span class="ansi-cyan-intense-fg ansi-bold">2</span>
<span class="ansi-green-fg">      4</span>     print<span class="ansi-yellow-intense-fg ansi-bold">(</span>c<span class="ansi-yellow-intense-fg ansi-bold">)</span>
<span class="ansi-green-intense-fg ansi-bold">----&gt; 5</span><span class="ansi-yellow-intense-fg ansi-bold"> </span>add<span class="ansi-yellow-intense-fg ansi-bold">(</span><span class="ansi-yellow-intense-fg ansi-bold">)</span> <span class="ansi-red-intense-fg ansi-bold"># Raise Error its global scop</span>

<span class="ansi-green-intense-fg ansi-bold">~\AppData\Local\Temp\ipykernel_11484\3093420356.py</span> in <span class="ansi-cyan-fg">add</span><span class="ansi-blue-intense-fg ansi-bold">()</span>
<span class="ansi-green-fg">      1</span> c <span class="ansi-yellow-intense-fg ansi-bold">=</span> <span class="ansi-cyan-intense-fg ansi-bold">1</span>
<span class="ansi-green-fg">      2</span> <span class="ansi-green-intense-fg ansi-bold">def</span> add<span class="ansi-yellow-intense-fg ansi-bold">(</span><span class="ansi-yellow-intense-fg ansi-bold">)</span><span class="ansi-yellow-intense-fg ansi-bold">:</span>
<span class="ansi-green-intense-fg ansi-bold">----&gt; 3</span><span class="ansi-yellow-intense-fg ansi-bold">     </span>c<span class="ansi-yellow-intense-fg ansi-bold">=</span>c<span class="ansi-yellow-intense-fg ansi-bold">+</span><span class="ansi-cyan-intense-fg ansi-bold">2</span>
<span class="ansi-green-fg">      4</span>     print<span class="ansi-yellow-intense-fg ansi-bold">(</span>c<span class="ansi-yellow-intense-fg ansi-bold">)</span>
<span class="ansi-green-fg">      5</span> add<span class="ansi-yellow-intense-fg ansi-bold">(</span><span class="ansi-yellow-intense-fg ansi-bold">)</span> <span class="ansi-red-intense-fg ansi-bold"># Raise Error its global scop</span>

<span class="ansi-red-intense-fg ansi-bold">UnboundLocalError</span>: local variable &#39;c&#39; referenced before assignment</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[5]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">y</span> <span class="o">=</span> <span class="s2">"Python"</span>
<span class="k">def</span> <span class="nf">calling</span><span class="p">():</span>
    <span class="n">y</span><span class="o">=</span><span class="s2">"Hello: "</span><span class="p">,</span><span class="n">y</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">y</span><span class="p">)</span>
<span class="n">calling</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>
<span class="ansi-red-intense-fg ansi-bold">---------------------------------------------------------------------------</span>
<span class="ansi-red-intense-fg ansi-bold">UnboundLocalError</span>                         Traceback (most recent call last)
<span class="ansi-green-intense-fg ansi-bold">&lt;ipython-input-5-e7acc4035cce&gt;</span> in <span class="ansi-cyan-fg">&lt;module&gt;</span>
<span class="ansi-green-fg">      3</span>     y<span class="ansi-yellow-intense-fg ansi-bold">=</span><span class="ansi-blue-intense-fg ansi-bold">&#34;Hello: &#34;</span><span class="ansi-yellow-intense-fg ansi-bold">,</span>y
<span class="ansi-green-fg">      4</span>     print<span class="ansi-yellow-intense-fg ansi-bold">(</span>y<span class="ansi-yellow-intense-fg ansi-bold">)</span>
<span class="ansi-green-intense-fg ansi-bold">----&gt; 5</span><span class="ansi-yellow-intense-fg ansi-bold"> </span>calling<span class="ansi-yellow-intense-fg ansi-bold">(</span><span class="ansi-yellow-intense-fg ansi-bold">)</span>

<span class="ansi-green-intense-fg ansi-bold">&lt;ipython-input-5-e7acc4035cce&gt;</span> in <span class="ansi-cyan-fg">calling</span><span class="ansi-blue-intense-fg ansi-bold">()</span>
<span class="ansi-green-fg">      1</span> y <span class="ansi-yellow-intense-fg ansi-bold">=</span> <span class="ansi-blue-intense-fg ansi-bold">&#34;Python&#34;</span>
<span class="ansi-green-fg">      2</span> <span class="ansi-green-intense-fg ansi-bold">def</span> calling<span class="ansi-yellow-intense-fg ansi-bold">(</span><span class="ansi-yellow-intense-fg ansi-bold">)</span><span class="ansi-yellow-intense-fg ansi-bold">:</span>
<span class="ansi-green-intense-fg ansi-bold">----&gt; 3</span><span class="ansi-yellow-intense-fg ansi-bold">     </span>y<span class="ansi-yellow-intense-fg ansi-bold">=</span><span class="ansi-blue-intense-fg ansi-bold">&#34;Hello: &#34;</span><span class="ansi-yellow-intense-fg ansi-bold">,</span>y
<span class="ansi-green-fg">      4</span>     print<span class="ansi-yellow-intense-fg ansi-bold">(</span>y<span class="ansi-yellow-intense-fg ansi-bold">)</span>
<span class="ansi-green-fg">      5</span> calling<span class="ansi-yellow-intense-fg ansi-bold">(</span><span class="ansi-yellow-intense-fg ansi-bold">)</span>

<span class="ansi-red-intense-fg ansi-bold">UnboundLocalError</span>: local variable &#39;y&#39; referenced before assignment</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[6]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">foo</span><span class="p">():</span>
    <span class="n">z</span> <span class="o">=</span> <span class="s2">"local"</span>


<span class="n">foo</span><span class="p">()</span>
<span class="nb">print</span><span class="p">(</span><span class="n">z</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>
<span class="ansi-red-intense-fg ansi-bold">---------------------------------------------------------------------------</span>
<span class="ansi-red-intense-fg ansi-bold">NameError</span>                                 Traceback (most recent call last)
<span class="ansi-green-intense-fg ansi-bold">&lt;ipython-input-6-903d3f57d2bf&gt;</span> in <span class="ansi-cyan-fg">&lt;module&gt;</span>
<span class="ansi-green-fg">      4</span> 
<span class="ansi-green-fg">      5</span> foo<span class="ansi-yellow-intense-fg ansi-bold">(</span><span class="ansi-yellow-intense-fg ansi-bold">)</span>
<span class="ansi-green-intense-fg ansi-bold">----&gt; 6</span><span class="ansi-yellow-intense-fg ansi-bold"> </span>print<span class="ansi-yellow-intense-fg ansi-bold">(</span>z<span class="ansi-yellow-intense-fg ansi-bold">)</span>

<span class="ansi-red-intense-fg ansi-bold">NameError</span>: name &#39;z&#39; is not defined</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[7]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">c</span><span class="o">=</span><span class="mi">0</span>
<span class="k">def</span> <span class="nf">add</span><span class="p">():</span>
    <span class="k">global</span> <span class="n">c</span>
    <span class="n">c</span><span class="o">+=</span><span class="mi">10</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"Inside add function: "</span><span class="p">,</span><span class="n">c</span><span class="p">)</span>
<span class="n">add</span><span class="p">()</span>
<span class="c1"># print("Outside add function: ",c)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Inside add function:  10
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[8]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">x</span> <span class="o">=</span> <span class="s2">"global "</span>

<span class="k">def</span> <span class="nf">foo</span><span class="p">():</span>
    <span class="k">global</span> <span class="n">x</span>
    <span class="n">y</span> <span class="o">=</span> <span class="s2">"local"</span>
    <span class="n">x</span> <span class="o">=</span> <span class="n">x</span> <span class="o">*</span> <span class="mi">2</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">y</span><span class="p">)</span>

<span class="n">foo</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>global global 
local
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Nested-Functions"><li style="font-size:20pt;">Nested Functions</li><a class="anchor-link" href="#Nested-Functions">&#182;</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[9]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Python program to illustrate</span>
<span class="c1"># nested functions</span>
<span class="k">def</span> <span class="nf">outerFunction</span><span class="p">(</span><span class="n">text</span><span class="p">):</span>
    <span class="n">text</span> <span class="o">=</span> <span class="n">text</span>
    
    <span class="k">def</span> <span class="nf">innerFunction</span><span class="p">():</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">text</span><span class="p">)</span>

    <span class="n">innerFunction</span><span class="p">()</span>

<span class="n">outerFunction</span><span class="p">(</span><span class="s1">'Hey !'</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Hey !
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[10]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">function1</span><span class="p">():</span> <span class="c1"># outer function</span>
    <span class="nb">print</span> <span class="p">(</span><span class="s2">"Hello from outer function"</span><span class="p">)</span>
    <span class="k">def</span> <span class="nf">function2</span><span class="p">():</span> <span class="c1"># inner function</span>
        <span class="nb">print</span> <span class="p">(</span><span class="s2">"Hello from inner function"</span><span class="p">)</span>
    <span class="n">function2</span><span class="p">()</span>
    
<span class="n">function1</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Hello from outer function
Hello from inner function
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[11]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">num1</span><span class="p">(</span><span class="n">x</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">num2</span><span class="p">(</span><span class="n">y</span><span class="p">):</span>
        <span class="k">return</span> <span class="n">x</span> <span class="o">*</span> <span class="n">y</span>
    <span class="k">return</span> <span class="n">num2</span>

<span class="n">res</span> <span class="o">=</span> <span class="n">num1</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">res</span><span class="p">(</span><span class="mi">5</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>50
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[12]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">function1</span><span class="p">():</span> <span class="c1"># outer function</span>
    <span class="n">x</span> <span class="o">=</span> <span class="mi">2</span> <span class="c1"># A variable defined within the outer function</span>
    <span class="k">def</span> <span class="nf">function2</span><span class="p">(</span><span class="n">a</span><span class="p">):</span> <span class="c1"># inner function</span>
       <span class="c1"># Let's define a new variable within the inner function</span>
       <span class="c1"># rather than changing the value of x of the outer function</span>
        <span class="n">x</span> <span class="o">=</span> <span class="mi">6</span>
        <span class="nb">print</span> <span class="p">(</span><span class="n">a</span><span class="o">+</span><span class="n">x</span><span class="p">)</span>
    <span class="nb">print</span> <span class="p">(</span><span class="n">x</span><span class="p">)</span> <span class="c1"># to display the value of x of the outer function</span>
    <span class="n">function2</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>

<span class="n">function1</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>2
9
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[13]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">function1</span><span class="p">(</span><span class="n">name</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">function2</span><span class="p">():</span>
        <span class="nb">print</span><span class="p">(</span><span class="s1">'Hello '</span> <span class="o">+</span> <span class="n">name</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">function2</span>

<span class="n">func</span> <span class="o">=</span> <span class="n">function1</span><span class="p">(</span><span class="s1">'Nichola Tesla'</span><span class="p">)</span>
<span class="n">func</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Hello Nichola Tesla
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Making-Library-With-Functions"><li style="font-size:20pt;">Making Library With Functions</li><a class="anchor-link" href="#Making-Library-With-Functions">&#182;</a></h1><h3 id="Save-this-code-with-this-name">Save this code with this name<a class="anchor-link" href="#Save-this-code-with-this-name">&#182;</a></h3><h2 id="calculator.py"><code>calculator.py</code><a class="anchor-link" href="#calculator.py">&#182;</a></h2><pre>
# for addition
def addition(x,y):
    return x+y

# for subtraction
def subtraction(x,y):
    return x-y

# for multiplacation
def multiplacation(x,y):
    return x*y

# for division
def division(x,y):
    return x/y

# for reminder
def reminder(x,y):
    return x%y

</pre><h3 id="Then-import-like-blow-code">Then import like blow code<a class="anchor-link" href="#Then-import-like-blow-code">&#182;</a></h3>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[1]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">calculator</span>

<span class="n">calculator</span><span class="o">.</span><span class="n">addition</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span><span class="mi">25</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[1]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>27</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[2]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">calculator</span> <span class="kn">import</span> <span class="n">subtraction</span>

<span class="n">subtraction</span><span class="p">(</span><span class="mi">50</span><span class="p">,</span><span class="mi">6</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[2]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>44</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[3]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">calculator</span> <span class="kn">import</span> <span class="o">*</span>

<span class="n">division</span><span class="p">(</span><span class="mi">20</span><span class="p">,</span><span class="mi">2</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[3]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>10.0</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Built-In-Function"><li style="font-size:20pt;">Built-In Function</li><a class="anchor-link" href="#Built-In-Function">&#182;</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[14]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">number</span> <span class="o">=</span> <span class="mi">9</span>

<span class="c1"># eval performs the multiplication passed as argument</span>
<span class="n">square_number</span> <span class="o">=</span> <span class="nb">eval</span><span class="p">(</span><span class="s1">'number * number'</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">square_number</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>81
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[203]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">name</span> <span class="o">=</span> <span class="nb">input</span><span class="p">(</span><span class="s2">"Enter your name: "</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">name</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Enter your name: Raheel
Raheel
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[204]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">numbers</span> <span class="o">=</span> <span class="p">[</span><span class="mi">9</span><span class="p">,</span> <span class="mi">34</span><span class="p">,</span> <span class="mi">11</span><span class="p">,</span> <span class="o">-</span><span class="mi">4</span><span class="p">,</span> <span class="mi">27</span><span class="p">]</span>

<span class="c1"># find the smallest number</span>
<span class="n">min_number</span> <span class="o">=</span> <span class="nb">min</span><span class="p">(</span><span class="n">numbers</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">min_number</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>-4
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[205]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">seq_string</span> <span class="o">=</span> <span class="s1">'Python'</span>

<span class="c1"># reverse of a string</span>
<span class="nb">print</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="nb">reversed</span><span class="p">(</span><span class="n">seq_string</span><span class="p">)))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>[&#39;n&#39;, &#39;o&#39;, &#39;h&#39;, &#39;t&#39;, &#39;y&#39;, &#39;P&#39;]
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[206]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">numbers</span> <span class="o">=</span> <span class="p">[</span><span class="mi">4</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="mi">12</span><span class="p">,</span> <span class="mi">8</span><span class="p">]</span>

<span class="n">sorted_numbers</span> <span class="o">=</span> <span class="nb">sorted</span><span class="p">(</span><span class="n">numbers</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">sorted_numbers</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>[2, 4, 8, 12]
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[207]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">languages</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'Java'</span><span class="p">,</span> <span class="s1">'Python'</span><span class="p">,</span> <span class="s1">'JavaScript'</span><span class="p">]</span>
<span class="n">versions</span> <span class="o">=</span> <span class="p">[</span><span class="mi">14</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="mi">6</span><span class="p">]</span>

<span class="n">result</span> <span class="o">=</span> <span class="nb">zip</span><span class="p">(</span><span class="n">languages</span><span class="p">,</span> <span class="n">versions</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="nb">dict</span><span class="p">(</span><span class="n">result</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>{&#39;Java&#39;: 14, &#39;Python&#39;: 3, &#39;JavaScript&#39;: 6}
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[208]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">languages</span> <span class="o">=</span> <span class="p">[</span><span class="s1">'Java'</span><span class="p">,</span> <span class="s1">'Python'</span><span class="p">,</span> <span class="s1">'JavaScript'</span><span class="p">]</span>
<span class="n">versions</span> <span class="o">=</span> <span class="p">[</span><span class="mi">14</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="mi">6</span><span class="p">]</span>

<span class="n">result</span> <span class="o">=</span> <span class="nb">zip</span><span class="p">(</span><span class="n">languages</span><span class="p">,</span> <span class="n">versions</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="n">result</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>[(&#39;Java&#39;, 14), (&#39;Python&#39;, 3), (&#39;JavaScript&#39;, 6)]
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Annonymous-Function"><li style="font-size:20pt;">Annonymous Function</li><a class="anchor-link" href="#Annonymous-Function">&#182;</a></h1><p>Lambda functions are used when you need a function for a short period of time. This is commonly when you want to pass a function as an argument to higher-order functions. A Lambda function can take any number of arguments, but can only have one expression.</p>
<p>Lambda function is also a annonymous function (function without a name).
<img src="data:image/png;base64,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PPNMtV1lZSUOhwOn04lhGMrqq9Fofhha3Go0mu/N4cSu3W4nkUioQd4cMPbGG2/w3XffAdClSxeuvvpqLrnkEpWztqqqioyMjGriWIStvDSanxspqet0OsnIyKBnz55MmzaNYDBIJBLB6/USj8eJRqM0bdqUwsJCzjjjDJUj1+l0EggESCaTKuuHlOs1W4U1Gs33R4tbjUZzSI5GTMZiMeVWsGXLFubOncu7777LBx98QDwep3Hjxlx88cUMGTKELl26AKh8t5K/FvZXL0un0yoTgnZN0PzcSNCY+Vls3bq18jN3Op107dqVeDzOokWLWLduHV999RUdOnRQmT6kylk0Gq3mwpNKpXSZXo3mB6JbkEajOShHayV1u92UlZWxfPlyJk2axNSpUykrK8NisdC7d28GDx5M586dq1UYCwaDeDwe/H4/6XRaLdPWRDK7aDQ/J5IRQVYTcnNzadmyJQB//OMf6datG9u2bePBBx9kwYIFPP300wQCAS655BK1vcPhwGazqZUOmcBpNJofhh4hNBrNARxK1B5JusCvv/6a6dOnM3bsWFavXg3AKaecwsUXX8wNN9xAq1atgH0W3mg0it/vV5HisVgMl8tFOp2uVslJBn1t2dL8EpDsH+l0mlgsRvPmzbnxxhs555xzaNSoEX6/nyZNmvC73/2Ozz77jBUrVjBr1izOPfdcbDYb6XRaPeeyP70yodEcG3SeW43mBCSVSgH7l/1rtnmxRkmUtwzGsVgMp9OJzWZTfUU6nVbCc+/evSxbtoznn3+ejz/+mFAohN/vp2fPntx444307t27WkowjebXiLSf2pDiJDKmfvvtt9x///2MHz+eJk2acPvtt3P77berNpVOp1Wb0mg0xwY9wmg0JyAiZg82kU0kEjidTlwuF9FotJoPbDqdpqKigpycHBKJBNFoFKfTyZYtWxg7diyTJ09m69at2Gw2zjzzTK699lp69+5Nfn4+cPSuDhrNLwVpN7U9yxaLhUgkonxomzVrxjXXXMPy5ctZv349kyZNonfv3rRv3x6AiooKJWzj8bhOA6bRHANsDz300ENANeuLttxqNMc/sgRam9VWorYjkQiGYeDxeFR1MdjnUxsMBvF6vVitViZMmMADDzzA1KlTKSkpoX79+gwYMIDbbruNPn36kJeXB+xLfSSR4hrNrxVzMZODjZd2u51o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SmFhIU8++ST16tUjHA4rv3nze41GUzu2hx566CHYNxuUSEw9iGk0v2xEgFqtViVmYX+WBMlxK9bakSNHct999zFnzhyCwSC5ubkMGDCAv/71r1x88cX4/X5isZhKEVbbsqruFzSaY4N5vBVcLhd2u52ysjLWrl1LZWUljRo1omXLlvh8PpLJJMlkUrkFaTSag6N9bjWaXyCHCxqx2WzKUivLmrCvqEIymcTpdGK325k/fz4vvfQSc+fOpbS0lEAgQJs2bfj73/9O+/btVXov2cZisVSz3GpBq9Ece8S1oKZLUdu2bbn55ptZtGgR33zzDePGjaNNmzZ07doVgGAwSE5Ozs923hrNrwWdNE+j+RUiY6RLWgAAIABJREFU/rDBYFD536XTaex2O06nk8rKSv7yl79QWFjIlClTKCsro0GDBtxyyy288847XHLJJTRr1ox4PE4oFAL2BblIwEpNX0EtcjWaY4fNZqt1RcRisdCpUycGDRpERkYGH330EdOnTyccDmO32/F4PGqFRV4ajeZAtLjVaH6BmAev2l7BYBDDMFSgifjulZaW8t5779G/f38mTJjAzp07sVqt9O/fnzfeeINHHnmEZs2aEYvFiEQiwL70XZLloLZgFS1sNZpji7nKmM1mw+l0Kvcir9fLkCFDuPDCCwGYMGECM2fOBDhA3MLhV3k0mhMR7Zag0fwKycjIUH614kLwxRdfMH78eF566SUqKioAVM7awYMH43K5CIVC+Hw+XC6XyoJgxjCMWv0BNRrNsUUKrJgLNEj2kRYtWtCvXz+WLFnCt99+y4QJE2jZsiWdOnWqljkBULlv9SRUo9mPFrcazS+Qw1ljotEoqVQKn89HaWkpkyZN4sUXX2TdunU4nU7y8vK45ppruOmmmzj55JOJx+O4XC58Ph/l5eVkZGRgtVqrWWm1oNVofjpEyNZMpyece+65DBgwgKeffpoPPviAFi1a0LRpU+rUqUMymaxW0EELW42mOno002h+hTgcDtxuN0uXLuWWW25h+PDhrFu3Dp/Px2mnncZLL73En/70J0455RScTider5dkMkkikVDCtqaYFbcEjUbz42O323E4HKpACuy3wobDYfLy8ujbty+nn346kUiEd999l88//1xtr90RNJqDo/PcajQ/A1IfXgSl+OCJFScWi6mUP5FIhGAwSJ06ddTS5a5d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" alt="image.png">
<img src="data:image/png;base64,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" alt="image-2.png"></p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[209]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">addition</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">a</span> <span class="p">:</span> <span class="n">a</span> <span class="o">+</span> <span class="mi">10</span> <span class="c1"># This lambda function adds value 10 to an argument</span>
<span class="nb">print</span><span class="p">(</span><span class="n">addition</span><span class="p">(</span><span class="mi">50</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>60
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[210]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">product</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">a</span><span class="p">,</span> <span class="n">b</span> <span class="p">:</span> <span class="n">a</span> <span class="o">*</span> <span class="n">b</span> <span class="c1">#This lambda function takes two arguments (a,b) and</span>
<span class="nb">print</span><span class="p">(</span><span class="n">product</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span> <span class="mi">56</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>280
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[211]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">addition</span> <span class="o">=</span> <span class="k">lambda</span> <span class="n">a</span><span class="p">,</span> <span class="n">b</span><span class="p">,</span> <span class="n">c</span> <span class="p">:</span> <span class="n">a</span> <span class="o">+</span> <span class="n">b</span> <span class="o">+</span> <span class="n">c</span> <span class="c1">#This lambda function takes three argument</span>
<span class="nb">print</span><span class="p">(</span><span class="n">addition</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span> <span class="mi">6</span><span class="p">,</span> <span class="mi">2</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>13
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[212]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">res</span> <span class="o">=</span> <span class="p">(</span><span class="k">lambda</span> <span class="o">*</span><span class="n">args</span><span class="p">:</span> <span class="nb">sum</span><span class="p">(</span><span class="n">args</span><span class="p">))</span>
<span class="c1"># res(10,20)</span>
<span class="c1"># res(10,20,30,40)</span>
<span class="n">res</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">20</span><span class="p">,</span><span class="mi">30</span><span class="p">,</span><span class="mi">40</span><span class="p">,</span><span class="mi">50</span><span class="p">,</span><span class="mi">60</span><span class="p">,</span><span class="mi">70</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[212]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>280</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[213]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">res1</span> <span class="o">=</span> <span class="p">(</span><span class="k">lambda</span> <span class="o">**</span><span class="n">kwargs</span><span class="p">:</span> <span class="nb">sum</span><span class="p">(</span><span class="n">kwargs</span><span class="o">.</span><span class="n">values</span><span class="p">()))</span> <span class="c1"># This lambda function can take an</span>
<span class="n">res1</span><span class="p">(</span><span class="n">a</span> <span class="o">=</span> <span class="mi">10</span> <span class="p">,</span> <span class="n">b</span><span class="o">=</span> <span class="mi">20</span> <span class="p">,</span> <span class="n">c</span> <span class="o">=</span> <span class="mi">30</span><span class="p">)</span>

<span class="c1"># res1(a = 10 , b= 20 , c = 30, d = 40)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[213]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>60</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[214]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dic</span> <span class="o">=</span> <span class="p">(</span><span class="k">lambda</span> <span class="o">**</span><span class="n">kwargs</span><span class="p">:</span> <span class="n">kwargs</span><span class="p">)</span>
<span class="n">dic</span><span class="p">(</span><span class="n">Name</span><span class="o">=</span><span class="s2">"raheel"</span><span class="p">,</span><span class="n">ID</span><span class="o">=</span><span class="mi">65456</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[214]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>{&#39;Name&#39;: &#39;raheel&#39;, &#39;ID&#39;: 65456}</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1><li style="font-size:20pt;">Map, Filter & Reduce Function</li></h1>
<p>Three new functions have been introduced in the latest version of Python that provide a more elegant and short-hand approach to some problems. The map() and filter() and reduce() functions bring a bit of functional programming to Python. All three of these are convenience functions that can be replaced with List Comprehensions or loops, but provide a cleaner way of working with data.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="The-map()-Function">The map() Function<a class="anchor-link" href="#The-map()-Function">&#182;</a></h2><p>The map() function iterates through all items in the given iterable and executes the function we passed as an argument on each of them.</p>
<p>The syntax is:</p>
<p>map(function, iterable(s))</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[215]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Without using lambdas</span>
<span class="k">def</span> <span class="nf">starts_with_A</span><span class="p">(</span><span class="n">s</span><span class="p">):</span>
    <span class="k">return</span> <span class="n">s</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">==</span> <span class="s2">"A"</span>

<span class="n">fruit</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"Apple"</span><span class="p">,</span> <span class="s2">"Banana"</span><span class="p">,</span> <span class="s2">"Pear"</span><span class="p">,</span> <span class="s2">"Apricot"</span><span class="p">,</span> <span class="s2">"Orange"</span><span class="p">]</span>
<span class="n">map_object</span> <span class="o">=</span> <span class="nb">map</span><span class="p">(</span><span class="n">starts_with_A</span><span class="p">,</span> <span class="n">fruit</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="n">map_object</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>[True, False, False, True, False]
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[216]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">fruit</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"Apple"</span><span class="p">,</span> <span class="s2">"Banana"</span><span class="p">,</span> <span class="s2">"Pear"</span><span class="p">,</span> <span class="s2">"Apricot"</span><span class="p">,</span> <span class="s2">"Orange"</span><span class="p">]</span>
<span class="n">map_object</span> <span class="o">=</span> <span class="nb">map</span><span class="p">(</span><span class="k">lambda</span> <span class="n">s</span><span class="p">:</span> <span class="n">s</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">==</span> <span class="s2">"A"</span><span class="p">,</span> <span class="n">fruit</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="n">map_object</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>[True, False, False, True, False]
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="The-filter()-Function">The filter() Function<a class="anchor-link" href="#The-filter()-Function">&#182;</a></h2><p>Similar to map(), filter() takes a function object and an iterable and creates a new list.</p>
<p>As the name suggests, filter() forms a new list that contains only elements that satisfy a certain condition, i.e. the function we passed returns True.</p>
<p>The syntax is:</p>
<p>filter(function, iterable(s))</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[217]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">starts_with_A</span><span class="p">(</span><span class="n">s</span><span class="p">):</span>
    <span class="k">return</span> <span class="n">s</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">==</span> <span class="s2">"A"</span>

<span class="n">fruit</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"Apple"</span><span class="p">,</span> <span class="s2">"Banana"</span><span class="p">,</span> <span class="s2">"Pear"</span><span class="p">,</span> <span class="s2">"Apricot"</span><span class="p">,</span> <span class="s2">"Orange"</span><span class="p">]</span>
<span class="n">filter_object</span> <span class="o">=</span> <span class="nb">filter</span><span class="p">(</span><span class="n">starts_with_A</span><span class="p">,</span> <span class="n">fruit</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="n">filter_object</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>[&#39;Apple&#39;, &#39;Apricot&#39;]
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[218]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">fruit</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"Apple"</span><span class="p">,</span> <span class="s2">"Banana"</span><span class="p">,</span> <span class="s2">"Pear"</span><span class="p">,</span> <span class="s2">"Apricot"</span><span class="p">,</span> <span class="s2">"Orange"</span><span class="p">]</span>
<span class="n">filter_object</span> <span class="o">=</span> <span class="nb">filter</span><span class="p">(</span><span class="k">lambda</span> <span class="n">s</span><span class="p">:</span> <span class="n">s</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">==</span> <span class="s2">"A"</span><span class="p">,</span> <span class="n">fruit</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="n">filter_object</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>[&#39;Apple&#39;, &#39;Apricot&#39;]
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="The-reduce()-Function">The reduce() Function<a class="anchor-link" href="#The-reduce()-Function">&#182;</a></h2><p>reduce() works differently than map() and filter(). It does not return a new list based on the function and iterable we've passed. Instead, it returns a single value.</p>
<p>Also, in Python 3 reduce() isn't a built-in function anymore, and it can be found in the functools module.</p>
<p>The syntax is:</p>
<p>reduce(function, sequence[, initial])</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[219]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">functools</span> <span class="kn">import</span> <span class="n">reduce</span>

<span class="k">def</span> <span class="nf">add</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">y</span><span class="p">):</span>
    <span class="k">return</span> <span class="n">x</span> <span class="o">+</span> <span class="n">y</span>

<span class="nb">list</span> <span class="o">=</span> <span class="p">[</span><span class="mi">2</span><span class="p">,</span> <span class="mi">4</span><span class="p">,</span> <span class="mi">7</span><span class="p">,</span> <span class="mi">3</span><span class="p">]</span>
<span class="nb">print</span><span class="p">(</span><span class="n">reduce</span><span class="p">(</span><span class="n">add</span><span class="p">,</span> <span class="nb">list</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>16
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[220]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">functools</span> <span class="kn">import</span> <span class="n">reduce</span>

<span class="nb">list</span> <span class="o">=</span> <span class="p">[</span><span class="mi">2</span><span class="p">,</span> <span class="mi">4</span><span class="p">,</span> <span class="mi">7</span><span class="p">,</span> <span class="mi">3</span><span class="p">]</span>
<span class="nb">print</span><span class="p">(</span><span class="n">reduce</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">,</span> <span class="n">y</span><span class="p">:</span> <span class="n">x</span> <span class="o">+</span> <span class="n">y</span><span class="p">,</span> <span class="nb">list</span><span class="p">))</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"With an initial value: "</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">reduce</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">,</span> <span class="n">y</span><span class="p">:</span> <span class="n">x</span> <span class="o">+</span> <span class="n">y</span><span class="p">,</span> <span class="nb">list</span><span class="p">,</span> <span class="mi">10</span><span class="p">)))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>16
With an initial value: 26
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Decorators"><li style="font-size:20pt;">Decorators</li><a class="anchor-link" href="#Decorators">&#182;</a></h1><p>Decorators are a design pattern in Python that allows a user to add new functionality to an existing object without modifying its structure. A few good examples are when you want to add logging, test performance, perform caching, verify permissions, and so on. You can also use one when you need to run the same code on multiple functions.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[221]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">decorator</span><span class="p">(</span><span class="n">func</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">inner_deco</span><span class="p">():</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"I'm inside decorator function"</span><span class="p">)</span>
        <span class="n">func</span><span class="p">()</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"I'm inner_deco function"</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">inner_deco</span>

<span class="k">def</span> <span class="nf">num</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">()</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"We will us this 'num' function"</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"I'll use as the decorator!"</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">()</span>
    
<span class="n">new</span> <span class="o">=</span> <span class="n">decorator</span><span class="p">(</span><span class="n">num</span><span class="p">)</span>
<span class="n">new</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>I&#39;m inside decorator function

We will us this &#39;num&#39; function
I&#39;ll use as the decorator!

I&#39;m inner_deco function
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[222]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">decorator</span><span class="p">(</span><span class="n">func</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">inner_deco</span><span class="p">():</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"I'm inside decorator function"</span><span class="p">)</span>
        <span class="n">func</span><span class="p">()</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"I'm inner_deco function"</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">inner_deco</span>

<span class="k">def</span> <span class="nf">num</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">()</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"We will us this 'num' function"</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"I'll use as the decorator!"</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">()</span>
    
<span class="n">new</span> <span class="o">=</span> <span class="n">decorator</span><span class="p">(</span><span class="n">num</span><span class="p">)</span>
<span class="n">new</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>I&#39;m inside decorator function

We will us this &#39;num&#39; function
I&#39;ll use as the decorator!

I&#39;m inner_deco function
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[223]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">decorator</span><span class="p">(</span><span class="n">num</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">inner_deco</span><span class="p">():</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"I'm inside decorator function"</span><span class="p">)</span>
        <span class="n">num</span><span class="p">()</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"I'm inner_deco function"</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">inner_deco</span>

<span class="nd">@decorator</span>
<span class="k">def</span> <span class="nf">num</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">()</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"We will us this 'num' function"</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"I'll use as the decorator!"</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">()</span>
    
<span class="n">num</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>I&#39;m inside decorator function

We will us this &#39;num&#39; function
I&#39;ll use as the decorator!

I&#39;m inner_deco function
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[224]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">decorat</span><span class="p">(</span><span class="n">fun</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">inner</span><span class="p">():</span>
        <span class="n">a</span> <span class="o">=</span> <span class="n">fun</span><span class="p">()</span>
        <span class="n">add</span> <span class="o">=</span> <span class="n">a</span> <span class="o">+</span> <span class="mi">10</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">add</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">inner</span>

<span class="k">def</span> <span class="nf">num</span><span class="p">():</span>
    <span class="k">return</span> <span class="mi">10</span>

<span class="n">main</span> <span class="o">=</span> <span class="n">decorat</span><span class="p">(</span><span class="n">num</span><span class="p">)</span>
<span class="n">main</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>20
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[225]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">decorat</span><span class="p">(</span><span class="n">num</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">inner</span><span class="p">():</span>
        <span class="n">a</span> <span class="o">=</span> <span class="n">num</span><span class="p">()</span>
        <span class="n">add</span> <span class="o">=</span> <span class="n">a</span> <span class="o">+</span> <span class="n">a</span>
        <span class="k">return</span> <span class="n">add</span>
    <span class="k">return</span> <span class="n">inner</span>

<span class="nd">@decorat</span>
<span class="k">def</span> <span class="nf">num</span><span class="p">():</span>
    <span class="k">return</span> <span class="mi">10</span>

<span class="n">num</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[225]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>20</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[226]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">hello_decorator</span><span class="p">(</span><span class="n">func</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">inner1</span><span class="p">():</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"Hello, this is before function execution"</span><span class="p">)</span>
        <span class="n">func</span><span class="p">()</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"This is after function execution"</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">inner1</span>

<span class="k">def</span> <span class="nf">function_to_be_used</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"This is inside the function !!"</span><span class="p">)</span>

<span class="n">function_to_be_used</span> <span class="o">=</span> <span class="n">hello_decorator</span><span class="p">(</span><span class="n">function_to_be_used</span><span class="p">)</span>
<span class="n">function_to_be_used</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Hello, this is before function execution
This is inside the function !!
This is after function execution
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[227]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">hello_decorator</span><span class="p">(</span><span class="n">func</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">inner1</span><span class="p">():</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"Hello, this is before function execution"</span><span class="p">)</span>
        <span class="n">func</span><span class="p">()</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"This is after function execution"</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">inner1</span>
<span class="nd">@hello_decorator</span>
<span class="k">def</span> <span class="nf">function_to_be_used</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"This is inside the function !!"</span><span class="p">)</span>

<span class="n">function_to_be_used</span><span class="p">()</span>
<span class="c1"># function_to_be_used = hello_decorator(function_to_be_used)</span>
<span class="c1"># function_to_be_used()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Hello, this is before function execution
This is inside the function !!
This is after function execution
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[228]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">smart_divide</span><span class="p">(</span><span class="n">func</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">"func parameter: "</span><span class="p">,</span><span class="n">func</span><span class="p">)</span>
    <span class="k">def</span> <span class="nf">inner</span><span class="p">(</span><span class="n">a</span><span class="p">,</span> <span class="n">b</span><span class="p">):</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"inner "</span><span class="p">,</span><span class="n">a</span><span class="p">,</span><span class="s2">"</span><span class="se">\n</span><span class="s2"> Inner "</span><span class="p">,</span><span class="n">b</span><span class="p">)</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">"I am going to divide"</span><span class="p">,</span> <span class="n">a</span><span class="p">,</span> <span class="s2">"and"</span><span class="p">,</span> <span class="n">b</span><span class="p">)</span>
        <span class="k">if</span> <span class="n">b</span> <span class="o">==</span> <span class="mi">0</span><span class="p">:</span>
            <span class="nb">print</span><span class="p">(</span><span class="s2">"Whoops! cannot divide"</span><span class="p">)</span>
            <span class="k">return</span>
        <span class="k">return</span> <span class="n">func</span><span class="p">(</span><span class="n">a</span><span class="p">,</span> <span class="n">b</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">inner</span>

<span class="nd">@smart_divide</span>
<span class="k">def</span> <span class="nf">divide</span><span class="p">(</span><span class="n">a</span><span class="p">,</span> <span class="n">b</span><span class="p">):</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">a</span><span class="o">/</span><span class="n">b</span><span class="p">)</span>
    
<span class="n">divide</span><span class="p">(</span><span class="mi">8</span><span class="p">,</span><span class="mi">0</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>func parameter:  &lt;function divide at 0x000001C771062708&gt;
inner  8 
 Inner  0
I am going to divide 8 and 0
Whoops! cannot divide
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<hr>

</div>
</div>
</div>
</div>
</body>







</html>
