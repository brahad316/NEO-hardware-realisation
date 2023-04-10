# NEO-hardware-realisation
<br>
A study of NEO (Non-linear Energy Operator) and it's popular application in spike detection for neural signals, ECG signals, etc. And hardware realisation of the same.

The implementation can be looked at in these major stages:
```
        |_ Block design of NEO with operators involved 
        |_ Building subcircuits for operators
        |_ Building the complete circuit using these subcircuits
        |_ Verification and testing: providing different input signals and analysing the outputs
```     

## Block design

The final implementation would look something like this:
<br>
<p align = "center">
<img src = "https://user-images.githubusercontent.com/94699627/230158598-6b008fff-e858-4c7f-ba47-46273134c185.jpg">
</p>

## rough logs

### differentiator block succeeded by inverter
![image](https://user-images.githubusercontent.com/94699627/230831451-1d918f86-24fa-4e5a-bbeb-3f52bcaaa068.png)

- The differentiator gives inverted output, being corrected by cascading an active inverter.

### double differentiator
![image](https://user-images.githubusercontent.com/94699627/230831511-6e8e4771-2d05-40df-9666-1b74ea0cfce5.png)
- made by cascading two differentiators.

### multiplier
![image](https://user-images.githubusercontent.com/94699627/230831649-dd998096-bda9-4e2f-962a-30b93339a646.png)

- using AD633 IC.

## Outputs of blocks

### differentiator

input (square wave)        |  output 
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/94699627/230908579-9bcff140-90fc-4813-b82f-43208d96df50.png) | ![image](https://user-images.githubusercontent.com/94699627/230908428-91520685-4134-41f5-a752-7d0c16ae6bc7.png)



`... work in progress`
