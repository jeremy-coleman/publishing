const rxPaths = require('rxjs/_esm5/path-mapping');

    resolve: {
      extensions: ['.webpack.js', '.web.js', '.ts', '.tsx', '.js', '.json'],
      alias: rxPaths()
    },
