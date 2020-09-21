# Gulp

A gulpfile is a file in your project directory titled `gulpfile.js` (or capitalized as `Gulpfile.js`, like Makefile), that automatically loads when you run the `gulp` command. Within this file, you'll often see gulp APIs, like `src()`, `dest()`, `series()`, or `parallel()` but any vanilla JavaScript or Node modules can be used. Any exported functions will be registered into gulp's task system.



#### start

- create a file named gulpfile.js in your project root 
- require the modules, gulp is compulsory, the others you need to install via npm, such as gulp sass

```javascript
var gulp        = require('gulp');
var browserSync = require('browser-sync').create();
var sass        = require('gulp-sass');
var uglify      = require('gulp-uglify');
```



#### creating a task

in Gulp you can chain multiple tasks together using the `pipe()` method. Gulp makes use of streams. There are readable and writeable streams.

```js
gulp.src(config.jsSrc)
    .pipe(uglify())
    .pipe(gulp.dest(config.dest + '/js'))
    .pipe(size());
```

`gulp.src(...)` turns the path at `config.jsSrc` into a readable stream of data that we are then piping to the `gulp-uglify` module. The uglify task returns a stream that we then pipe to our destination and so on...

`gulp.dest()`creates a stram for writing objects into the file system, essentially where the resulting file of the operations is going to be saved.

example in atomic:

```javascript
gulp.task('sass', function() {
    return gulp.src(["sass/*.scss", "_molecules/**/*.scss", "_organisms/**/*.scss", "!sass/amp.scss"])
        .pipe(plumber({
            errorHandler: function (err) {
                console.log('SASS '+err.name+' on Line '+err.line+':'+err.column+': \n'+err.formatted );
                this.emit('end');
            }
        }))
        .pipe(sass({
			outputStyle: 'compressed'
		}))
		.pipe(autoprefixer({ browsers: ['last 20 versions'] }))
        .pipe(gulp.dest("css"))
        .pipe(browserSync.stream());
        //.pipe(notify({ message: 'Sass update complete', onLast: true }));
});
```



#### Watching files

`gulp.watch()` arguments are the files that he has to watch

```javascript
gulp.task('serve', ['sass', 'ampSass', 'scriptsJs', 'atomsJs', 'moleculesJs', 'organismsJs', 'vendorsJs', 'sd'], function() {

    var files = [
					'**/*.php',
					'**/*.{png,jpg,gif}'
				];

    browserSync.init(files, {
        open: "external",
        port: "9090",
        proxy: {
            target: "atomic.site"
        }
    });

    gulp.watch([
			'sass/**/*.scss',
			'_atoms/**/*.scss',
			'_molecules/**/*.scss',
			'_organisms/**/*.scss'
		], ['sass', 'ampSass']);
    gulp.watch('js/**/*.js', ['scriptsJs', browserSync.reload]);
	gulp.watch('styleguide/style.scss', ['sass', 'sd']);
    gulp.watch('_atoms/**/*.js', ['atomsJs', browserSync.reload]);
	gulp.watch('_molecules/**/*.js', ['moleculesJs', browserSync.reload]);
	gulp.watch('_organisms/**/*.js', ['organismsJs', browserSync.reload]);
    gulp.watch('js/vendors/**/*.js', ['vendorsJs', browserSync.reload]);
});
```



to watch usually you would use browswesync to reload the browser

```javascript
gulp.task('browser-sync', function() {
    browserSync.init({
        proxy: "yourlocal.dev"
    });
});
```



and use `browserSync.reload`after the name of the task.



and if you have Sass, in the sass task you would add

` .pipe(browserSync.stream());`

Streams are supported in Browsersync, so you can call reload at specific points during your tasks and all browsers will be informed of the changes. Because Browsersync only cares about your CSS when it's *finished* compiling - make sure you call `.stream()` *after* `gulp.dest`



##### streams

Streaming involves breaking a resource that you want to receive over a network down into small chunks, then processing it bit by bit. This is something browsers do anyway when receiving assets to be shown on webpages — videos buffer and more is gradually available to play, and sometimes you'll see images display gradually as more is loaded.

But this has never been available to JavaScript before. Previously, if we wanted to process a resource of some kind (be it a video, or a text file, etc.), we'd have to download the entire file, wait for it to be deserialized into a suitable format, then process the whole lot after it is fully received.

With Streams being available to JavaScript, this all changes — you can now start processing raw data with JavaScript bit by bit as soon as it is available on the client-side, without needing to generate a buffer, string, or blob.



#### running commands

Running the commands at once, commands are in the square brackets

` gulp.task('default', ['serve']);`

to run this you simply type: `gulp`