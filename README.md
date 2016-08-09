# webpack-plugin-structure
## webpack runtime  webpack-plugin arguments[webpackPlugin运行时的参数变量]
|- webpack + webpack.config
|- compilation  
|-----|-- chunks[Array]  
|-----|-- modules[Array] 
  
#### compilation top-level key/value  [compilation对象主要键值对]
- chunks[Array]     
> An array of chunks (build outputs) in the compilation.  
> Each chunk manages the composition of a final rendered assets     

 
- modules[Array]  
> An array of modules (built inputs) in the compilation.   
> Each module manages the build of a raw file from your source library.  

- assets[Object]
> 最终导出的key/value哈希表
 
#### compilation.modules  [compilation.modules对象主要键值对]

- fileDependencies

> An array of source file paths included into a module.   
> This includes the source JavaScript file itself (ex: index.js)   
> and all dependency asset files (stylesheets, images, etc) that it has required.   
> Reviewing dependencies is useful for seeing what source files belong to a module  

#### compilation.chunks  [compilation.chunks对象主要键值对]

- modules [Array] 

> An array of modules that are included into a chunk.   
> By extension, you may look through each module's dependencies to see what raw source files fed into a chunk.

- files [Array]  

> An array of output ```filenames``` generated by the chunk.  
> You may access these asset sources from the ```compilation.assets``` table.

## Lifecycle [webpackPlugin的生命周期]

> ---when loaders has resolved all modules[整个plugin编译的起始点] 

- instantiate[实例化]
> 执行实例的```apply```方法  

- getting the compilation object[获取compilation对象]

> compiler.plugin("compilation",(compilation)=>{})

- async compilation[异步处理,emit]
> ```compiler.plugin("emit", (compilation, callback)=>{})```

### demoCode[示例代码]
```bash
    # basic structure[基本结构]
    npm run  basic
    # compile demo [编译结构]
    npm run compile
    # asnyc demo [异步处理]
    npm run async 
    # sample demo [完整的展示]
    npm run sample
    
```

 
 

