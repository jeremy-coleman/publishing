
##TLDR
SCSS: You can import css files in .scss file 
plugins: [[SassPlugin({importer : true}), CSSPlugin()] -> @import '~bootstrap/dist/css/bootstrap.css'; (~=node_modules)  

CSS:  
.css files: @import 'node_modules/bootstrap/.../file.css'  
.ts files: import 'bootstrap.../file.css'  

NOTE: CSSResourcePlugin fucks things up. 
1) it doesnt work.  
2) even when you get it to work, you get errors from acorn saying it cant resolve @  
3) if you use it with the CSS or Sass plugin, it fucks them up too.  
    IE: [SassPlugin({importer : true}), CSSPlugin()]  <-GOOD,  
    [SassPlugin({importer : true}), CSSResourcePlugin(), CSSPlugin()]  <-SADFACE
    [SassPlugin(), CSSResourcePlugin(), CSSPlugin()]  <-SADFACE
    [SassPlugin(), CSSResourcePlugin({dist: 'dist/assets'}), CSSPlugin()]  <-SADFACE

example plugin config
```javascript
  plugins: [
                [SassPlugin({importer : true}), CSSPlugin()],
                CSSPlugin(),
                SVGPlugin(),
                WebIndexPlugin({template : "src/app/index.html"}),
                this.isProduction && QuantumPlugin({
                    bakeApiIntoBundle: "app",
                    uglify: true,
                    css : true <----adding this writes CSS to the prod build folder
                })
            ]
```
##Explanation  

##Enabling outside imports
such as:  

in app.scss 
```css
@import '~bootstrap/dist/css/bootstrap.css';

.App {
    text-align: center;
}
```

fusebox gives u 3 macros as default  
$homeDir = home directory
$appRoot = app root
~ = node_modules

EX:  
@import '$homeDir/test2.scss';  
@import '$appRoot/src/test.scss';  
@import '~bootstrap/dist/bootstrap.css';  

example override:  
plugins: [  
    [ SassPlugin({ importer : true, macros: { "$homeDir": "custom/dir/" }}), CSSPlugin() ]  
]  





