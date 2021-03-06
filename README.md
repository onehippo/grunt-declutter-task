# declutter

> A Grunt module that checks if you explicitly defined which files from a folder you want to use.

## Getting Started
This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install declutter --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('declutter');
```

## The "declutter" task

### Overview
In your project's Gruntfile, add a section named `declutter` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  declutter: {
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

#### options.rules
Type: `Object`
Default value: `{}`

An object containing the rules to be used by the task.

### Usage Examples

#### Default Options
In this example, the directories `plugins` and `vendors` are both tested according to the specified rules.
If there is a folder named `another-plugin` inside the `plugins` of `vendors` folder, the validation will fail because there are no rules defined for this folder.


```js
grunt.initConfig({
  declutter: {
    options: {
        rules: {
          'angular': [
            'angular.min.js'
          ],

          'targeting-plugin': [
            'images/*',
            'plugin.js'
          ]
        }
    },
    files: {
      'plugins/*',
      'vendors/*'
    },
  },
})
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History
 * v0.1.0
