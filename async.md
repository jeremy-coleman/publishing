
const isCollisionAsync = async (a, b) => {
    let x  = Promise.all([
        Promise.resolve(Object.is((a), false)),
        Promise.resolve(Object.is((a), false)),
        Promise.resolve(Object.is((a), false)),
        Promise.resolve(Object.is((b), true))
        ])
    
    return [...new Set(await x)]

};

isCollisionAsync(true, true).then(v => console.log(v))

//let uniqueArray = [...new Set([xy])];
