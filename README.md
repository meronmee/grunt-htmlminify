# grunt-htmlminify

Minifies HTML with any CSS & JS using [html-minify](https://github.com/yize/html-minify).


## Getting Started
This plugin requires Grunt `~0.4.0`.

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-htmlminify--save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-htmlminify');
```




## Htmlminify task
_Run this task with the `grunt htmlminify` command._


### Options

See the [html-minifier docs](http://perfectionkills.com/experimenting-with-html-minifier/#options) for more in-depth explanation of the options and caveats.

#### removeComments

Type: `Boolean`  
Default: `false`

Strip HTML comments.

#### removeCommentsFromCDATA

Type: `Boolean`  
Default: `false`

Remove HTML comments from inside `<script>` and `<style>`.

#### removeCDATASectionsFromCDATA

Type: `Boolean`  
Default: `false`

Remove CDATA sections from inside `<script>` and `<style>`.

#### collapseWhitespace

Type: `Boolean`  
Default: `false`

Collapse white space that contributes to text nodes in a document tree.

It doesn't affect significant white space; e.g. in contents of elements like SCRIPT, STYLE, PRE or TEXTAREA.

`<div> <p>    foo </p>    </div>` => `<div><p>foo</p></div>`

#### collapseBooleanAttributes

Type: `Boolean`  
Default: `false`

Collapse boolean attributes.

`<input disabled="disabled">` => `<input disabled>`

#### removeAttributeQuotes

Type: `Boolean`  
Default: `false`

Remove attribute quotes when it's safe to do so.

`<p id="foo">` => `<p id=foo>`

#### removeRedundantAttributes

Type: `Boolean`  
Default: `false`

Remove redundant attributes like `type="text/javascript"`.

#### useShortDoctype

Type: `Boolean`  
Default: `false`

Replace doctype with the short HTML5 version `<!DOCTYPE html>`.

#### removeEmptyAttributes

Type: `Boolean`  
Default: `false`

Remove empty (or blank) attributes.

#### removeOptionalTags

Type: `Boolean`  
Default: `false`

Some elements are allowed to have their tags omitted, like `</td>`.

#### removeEmptyElements

Type: `Boolean`  
Default: `false`

Remove empty elements.

*Experimental*

#### Example config

```javascript
grunt.initConfig({
  htmlminify: {                                  // Task
    dist: {                                      // Target
      options: {                                 // Target options
        removeComments: true,
        collapseWhitespace: true
      },
      files: {                                   // Dictionary of files
        'dist/index.html': 'src/index.html',     // 'destination': 'source'
        'dist/contact.html': 'src/contact.html'
      }
    },
    dev: {                                       // Another target
      files: {
        'dist/index.html': 'src/index.html',
        'dist/contact.html': 'src/contact.html'
      }
    }
  }
});

grunt.loadNpmTasks('grunt-htmlminify');

grunt.registerTask('default', ['htmlminify']);
```

