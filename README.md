# BozzPrintf
An example on how function interposition can be done.

## Step 1
Compile the shared library first.
```
gcc -Wall -fPIC -shared -o BozzPrintf.so BozzPrintf.c -ldl
```

## Step 2
Run this with your own C program using the `printf`/`puts` function with `Shao Wei` in it.
```
# For macos:
DYLD_INSERT_LIBRARIES=BozzPrintf.so DYLD_FORCE_FLAT_NAMESPACE=y ./main

# For Linux:
LD_PRELOAD=BozzPrintf.so ./main
```
