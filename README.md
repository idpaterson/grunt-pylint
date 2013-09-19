# grunt-pylint

> Validate python code with pylint.

## Getting Started
This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-pylint --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-pylint');
```

## The "pylint" task

### Overview
In your project's Gruntfile, add a section named `pylint` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  pylint: {
    options: {
      // Task-specific options go here.
    },
    your_target: {
      // Target-specific file lists and/or options go here.
    },
  },
})
```

### Options

#### disable
Type: `String` or `Array`  

Messages to disable, either by category (like `C` for convention), by ID (like `C0103`) or by symbolic name (like `invalid-name`).

#### enable
Type: `String` or `Array`  

Messages to enable, either by category or by ID.

#### errorsOnly
Type: `Boolean`  
Default: `false`

Only report on error messages.

#### force
Type: `Boolean`  
Default: `false`

Never fail the task.

#### ignore
Type: `String` or `Array`  

Files or directories to ignore. Must be basenames, not paths.

#### outputFile
Type: `String`  
Default: `null`

A file to save the output to.

#### outputFormat
Type: `String`  
Alternatives: `text|colorized|html`
Default: `"colorized"`

What format the output will be in.

#### rcfile
Type: `String`  
Default: `null`

A path to a rcfile to use. Messages to enable or disable given in `options.enable` and `options.disable` will override anything given in the rcfile.

#### report
Type: `Boolean`  
Default: `true`

Whether to include a full report or just the messages.

#### symbolicIds
Type: `Boolean`  
Default: `false`

Whether to include a symbolic name of each message in the output.

### Usage Examples

#### Default Options
In the simplest case, use all the default pylint options:

```js
grunt.initConfig({
  pylint: {
    dist: {
      src: 'mypackage',
    }
  }
})
```

#### Custom Options
In this example, use a rcfile to specify checks to enable and disable, with overrides for one package.

```js
grunt.initConfig({
  pylint: {
    options: {
      rcfile: '.pylintrc',
    },
    src_package: {
      src: 'mypackage',
    },
    tests: {
      src: 'test',
      options: {
        disable: 'C0111', # missing docstring
      }
    }
  },
})
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Lint and test your code using [Grunt](http://gruntjs.com/). To get the pylint library, run `npm run-script prepublish`. This requires that you have pip installed.

## Release History
_(Nothing yet)_
