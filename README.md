# epubjs-brightwing
### Changes made to epub.js https://github.com/futurepress/epub.js/
The epub.js system was modified to serve the needs of a special fixed-layout ebook for Brightwing Books (brightwing.ca).

#### epub.js
Altered the pagination system to skip cfi calculations of `nextPage()` and `prePage()` 
so that the "next" and "prev" arrow buttons load a new chapter, i.e. call `nextChapter()` or `prevChapter()`,
which loads a new xhtml document from the spine. This was done in order to circumvent a bug that 
had the arrow button click traversing the cfi character offset as if it were a `nextPage()` call.

#### hooks.js
Added support for swipe gestures with hammer.js

#### reader.js
Added download, share, and home controllers. Implemented the TODO item in the original epub.js reader 
to load the chapter name as the bookmark name instead of it's cfi location. This was done with a simple regex
to mach the chapter name in the cfi, `[chaptername]`.
