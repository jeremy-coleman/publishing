```javascript
var less gulpless
sass = gulp-sass

gulp.task('build/admin', function() {

    var lessStream = gulp.src([...])
        .pipe(less())
        .pipe(concat('less-files.less'))
    ;

    var scssStream = gulp.src([...])
        .pipe(sass())
        .pipe(concat('scss-files.scss'))
    ;
    
    var cssStream = gulp.src([...])
        .pipe(concat('css-files.css'))
    ;

    var mergedStream = merge(lessStream, scssStream, cssStream)
        .pipe(concat('styles.css'))
        .pipe(minify())
        .pipe(gulp.dest('web/css'));

    return mergedStream;
});
```
