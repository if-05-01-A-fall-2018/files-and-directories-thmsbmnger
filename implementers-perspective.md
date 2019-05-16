# File systems (implementers perspective)



## Exercise 1
    DiskSize = 250GB = 2.684*10^11B
    BlockSize = 1kB = 1024B
### a.
    
    N = DiskSize / BlockSize = 262144000 blocks

### b.
    Entries = N

### c.
    EntrySize = log2(N) = 27.966b ~ 28b (32b)

### d.
    FATSize = EntrySize * N / 8 = 1048576000B = 1000MB ~ 1GB

## Exercise 2
### a.
The block is somewhere deep in the triple indirect block :´(

### b.
    107834590 / 1024 ~ 105308
Skip to block 105308

## Exercise 3
    PointerSize = 32b = 4B
### 1kB block size
    BlockSize = 1kB = 1024B
    PointersPerBlock = 1024B / 4B = 256 = N
    Direct = 10 * BlockSize = 10240
    Single = N * BlockSize = 262144B
    Double = N^2 * BlockSize = 67108864B
    Triple = N^3 * BlockSize = 1.718*10^10B
    MaxSize = Direct 
            + Single
            + Double 
            + Triple 
            = 1.725*10^10B ~ 16GB
### 4kB block size
    BlockSize = 4kB = 4096B
    PointersPerBlock = 4096B / 4B = 1024 = N
    Direct = 10 * BlockSize = 40960B
    Single = N * BlockSize = 4194304B
    Double = N^2 * BlockSize = 4294967296B
    Triple = N^3 * BlockSize = 4.398*10^12B
    MaxSize = Direct 
            + Single
            + Double 
            + Triple 
            = 4.402*10^12 ~ 4TB
The max file size with a 4kB block size is about __64 times__ bigger than with a 1kB block size.

## Exercise 4
    BlockSize = 512B
    PointerSize = 4B
    PointersPerBlock = 512B / 4B = 128 = N
    EstMax = 5GB = 
### a.
    Direct = 10 * BlockSize = 5120B
    Single = N * BlockSize = 65536B
    Double = N^2 * BlockSize = 8388608B
    Triple = N^2 + BlockSize = 1073741824B
    MaxSize = Direct 
            + Single
            + Double 
            + Triple 
            = 1082201088B ~ 1GB
We would have to upgrade to 1024B block size.
### b.
Calculation for 1024B block size at **_Exercise 3.1._**
The max file size with a 1024B block size is ~ __16GB__.