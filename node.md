requires/module resolution 5 steps
1.resolve the path
2 load in memory
3 wrap in iife
4 eval
5 cache

require.resolve checks for existance

default tries .js, .json and .node
will automatically create a pojo from json
can just compile c++ to a .node without usage of js

cp.spawn does not use shell and uses streams

exec uses shell and buffers the entire output.

process.on('uncaughtExcepion', (err) => {
  //handlers must be sync
  fs.writeSync(1, `caught exception " ${err} \n`);
  //have to call exit, otherwise node will keep running
  process.exit(1)
})

buffer.alloc resets memory before it gives it to you
buffer.unsafeAlloc will have values

console.dir(global, {depth: 0})

