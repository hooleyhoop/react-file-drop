# react-file-drop

Zero dependency React component for Gmail or Facebook -like drag and drop file uploader. Drag files anywhere onto the window (or user defined 'frame' prop)! Very extensible, provides many hooks so you can use it to develop any custom behavior that you desire.

### V3 is out! See the [changelog](https://github.com/sarink/react-file-drop/blob/master/CHANGELOG.md)

## Demo

https://sarink.github.io/react-file-drop - A very simple live demo with example code and sample CSS

## Dependencies

None! (well, just `prop-types`, but that should already be removed from your prod bundle anyway)

## Browser support

✅ Chrome <br/>
✅ Firefox <br/>
✅ Safari <br/>
✅ IE 11 <br/>
✅ IE Edge <br/>

## Why?

I wanted that behavior that facebook, gmail, etc. have where a part of the page highlights immediately when you start dragging a file anywhere on the window. I couldn't find any React component that already did this, so, I made one!

## Installation

`npm install --save react-file-drop`

## Usage

`import { FileDrop } from 'react-file-drop`

## How it works

First, you define the `frame` prop (default is the `document`), whenever the user begins dragging file(s) anywhere over this frame, the `<div class="file-drop-target">` will be inserted into the DOM.  
Next, define an `onDrop` prop, whenever a user drops their files onto the target, this callback will be triggered.  
Lastly, you'll need to style it.

## Styling

By default, the component comes with no styles. You can grab the [demo CSS](https://raw.githubusercontent.com/sarink/react-file-drop/master/src/Demo/Demo.css) to get you started.

For custom class names (if you're using something like JSS) you can use the following props:

- `className`
- `targetClassName`
- `draggingOverFrameClassName`
- `draggingOverTargetClassName`

## Props

##### onDrop - function(files, event)

Callback when the user drops files onto the target

##### onDragOver - function(event)

Callback when the user is dragging over the target. Also adds the `file-drop-dragging-over-target` class to the `file-drop-target`

##### onDragLeave - function(event)

Callback when the user leaves the target. Removes the `file-drop-dragging-over-target` class from the `file-drop-target`

##### dropEffect - String "copy" || "move" || "link" || "none" (default: "copy")

Learn more about [HTML5 dropEffects](https://developer.mozilla.org/en-US/docs/Web/API/DataTransfer#dropEffect.28.29). Not available in IE :(

##### frame - document || HTMLElement (default: document)

This is the "scope" or frame that the user must drag some file(s) over to kick things off.

##### onFrameDragEnter - function(event)

Callback when the user begins dragging over the `frame`

##### onFrameDragLeave - function(event)

Callback when the user stops dragging over the `frame`

##### onFrameDrop - function(event)

Callback when the user drops files _anywhere_ over the `frame`

##### className - string (default: file-drop)

Class given to the outer container div.

##### targetClassName - string (default: file-drop-target)

Class given to the target div.

##### draggingOverFrameClassName - string (default: file-drop-dragging-over-frame)

Class given to the target div when file is being dragged over frame.

##### draggingOverTargetClassName - string (default: file-drop-dragging-over-target)

Class given to the target div when file is being dragged over target.

##### .file-drop

The outer container element

##### .file-drop > .file-drop-target

This is the target the user has to drag their files to. It will be inserted into the DOM whenever the user starts dragging over the frame.

##### .file-drop > .file-drop-target.file-drop-dragging-over-frame

The `file-drop-dragging-over-frame` class will be added to the `file-drop-target` whenever the user begins dragging a file over the `frame`, and it will be removed when they leave

##### .file-drop > .file-drop-target.file-drop-dragging-over-target

The `file-drop-dragging-over-target` class will be added to the `file-drop-target` whenever the user begins dragging a file over the `file-drop-target` div, and it will be removed when they leave

## Contributing

Your PRs are welcome! To run the app locally:

```
nvm use # Probably optional, but it can't hurt

cd file-drop
npm install
npm start

cd demo
npm install
npm start
```

Now both the apps are running in watch mode. If you make a change to the file-drop code, you should see the demo code automatically rebuild and update in your browser.
