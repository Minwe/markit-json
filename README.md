# gulp-marked-json

[![NPM version](https://img.shields.io/npm/v/gulp-marked-json.svg?style=flat-square)](https://www.npmjs.com/package/gulp-marked-json)
[![Build Status](https://img.shields.io/travis/minwe/gulp-marked-json.svg?style=flat-square)](https://travis-ci.org/minwe/gulp-marked-json)
[![Dependency Status](https://img.shields.io/david/minwe/gulp-marked-json.svg?style=flat-square)](https://david-dm.org/minwe/gulp-marked-json)
[![devDependency Status](https://img.shields.io/david/dev/minwe/gulp-marked-json.svg?style=flat-square)](https://david-dm.org/minwe/gulp-marked-json#info=devDependencies)

- Parse YAML front matter and Markdown body content with [front-matter][front-matter]
- Compile Markdown to HTML with [marked][marked]

### Install

```bash
$ npm install gulp-marked-json --save-dev
```

### Usage

Like any self-respecting gulp plugin, transformed source files will flow onward to the destination of your choice with directory structure preserved. Tinker with [marked’s config][marked-config] by passing an object.

**`gulpfile.js`**

```javascript
var gulp = require('gulp');
var markdown = require('gulp-marked-json');

gulp.task('markdown', function(){
  gulp.src('./content/**/*.md')
    .pipe(markdown({
        pedantic: true,
        smartypants: true
    }))
    .pipe(gulp.dest('.'));
});
```

**`/blog/posts/bushwick-artisan.md`**

    slug: bushwick-artisan
    title: Wes Anderson pop-up Bushwick artisan
    layout: centered
    ---

    ## YOLO
    Chia quinoa meh, you probably haven't heard of them sartorial Holowaychuk pickled post-ironic. Plaid ugh vegan, Sixpoint 8-bit sartorial artisan semiotics put a bird on it Mission bicycle rights Club-Mate vinyl.

**`/blog/posts/bushwick-artisan.json`**

```json
{
  "slug": "bushwick-artisan",
  "title": "Wes Anderson pop-up Bushwick artisan",
  "layout": "centered",
  "body": "<h2 id="yolo">YOLO</h2>\n<p>Chia quinoa meh, you probably haven't heard of them sartorial Holowaychuk pickled post-ironic. Plaid ugh vegan, Sixpoint 8-bit sartorial artisan semiotics put a bird on it Mission bicycle rights Club-Mate vinyl.</p>"
}
```

----
**[MIT](LICENSE) LICENSE** <br>
copyright &copy; 2014 sparkart group, inc.

[gulp-util]: https://github.com/gulpjs/gulp-util#buffercb
[front-matter]: https://github.com/jxson/front-matter
[marked]: https://github.com/chjj/marked
[marked-config]: https://github.com/lepture/markit#usage
[handlebars]: https://github.com/wycats/handlebars.js
[circleci]: https://circleci.com/gh/SparkartGroupInc/gulp-markdown-to-json.png?style=shield&circle-token=8bf33da398b8ab296fe670c81b3fecbae1471e25
