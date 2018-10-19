```js
const gulp = require('gulp');

const ts = require('gulp-typescript');
const ts_import = require('gulp-typescript-path-resolver');
const tsProject = ts.createProject('./tsconfig.json');

var replace = require('gulp-batch-replace');

//consistent way of writing \ .. even String.raw`\` fucks up when only using 1 character
let wtf = String.fromCharCode(0x5c)

var replacements = [
	[ wtf, '/' ]
]

gulp.task('build', () => {
    return tsProject.src()
        .pipe(tsProject())
        .pipe(ts_import.tsPathResolver(tsProject.config.compilerOptions, {
            // You can Overwrite the path
            "paths": {
                "@coglite": ["@coglite"]
            }
        }))
        .pipe(replace(replacements))
        .pipe(gulp.dest(tsProject.config.compilerOptions.outDir))
});


```
