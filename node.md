## Que1: What is REPL?
## Ans: REPL is reffered to
    R=> Read
    E=> Evaluate
    P=> Print
    L=> Loop

# Eg: 
    >3+5     //Read and evaluate
    >8      //print
    >       //Looping for next until not exited

## Que2: Type of modules in node js
## Ans: There are three types of node module

1. ```Core modules:``` It is a inbuilt module provide by node while installing
some of the inbuilt core module are: assert,fs,os,path,child_process,util

2. ```Local modules:``` It is a module created by developer itself.
eg: module.exports ={user}

3. ```Third party modules:``` It is provided by third party
eg: mongoose,shortid,express,bcrypt,dotenv etc

## Que3: What is difference between setTimeout(),setImmediate() and process.nextTick()?
## Ans: 

```
function multiply(a,b){     
   console.log(a*b);
};
```

# Both setTimeout()and setImmediate() is part of event loop

# Queue name:Timer queue
```
setTimeout(()=>{    
    console.log("setTimeout");
    multiply(2,3);
});
```

# It is executed just after the current process has finished
# Queue name:Check handler queue
```
setImmediate(()=>{   
    console.log("setImmediate");
    multiply(5,4);
});
```

# Is is executed just after the current prcess and before event loop
# Queue name: next tick queue
```
process.nextTick(()=>{    
    console.log("nextTick")
    multiply(6,4)
});
```

```
console.log("Hello");
```

# Output:
```
        Hello
        nextTick
        24
        setTimeout
        6
        setImmediate
        20
```
