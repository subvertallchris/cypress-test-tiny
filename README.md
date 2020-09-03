# cypress-test-tiny - subvertallchris fork

## Purpose

This demonstrates network errors encountered when a blob is used as a MediaSource reference.

## Details

Per a comment [here](https://github.com/video-dev/hls.js/issues/2544#issuecomment-594964306), "hls.js creates a MediaSource in the browser, which the <video> element references by the Object URL. Tis is the blob URL that you see in the source element." The behavior is defined in the W3C File Api spec. See https://www.w3.org/TR/FileAPI/#url.

## Usage

* Clone this repo
* `npm i` to install Cypress dependency
* `npm run cypress:open`
* Run the test
* Immediately open the Chrome Inspector and watch the network tab. You'll see attempts to load the blob URL fail.

Oddly enough, the video still plays. I don't know why this is, maybe hls.js has some fallback?
