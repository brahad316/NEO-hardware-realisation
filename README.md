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
<p align = "center">
![image](https://user-images.githubusercontent.com/94699627/230831451-1d918f86-24fa-4e5a-bbeb-3f52bcaaa068.png)
</p>

- The differentiator gives inverted output, being corrected by cascading an active inverter.

### double differentiator
<p align = "center">
![image](https://user-images.githubusercontent.com/94699627/230831511-6e8e4771-2d05-40df-9666-1b74ea0cfce5.png)
</p>

- made by cascading two differentiators.

### multiplier
<p align = "center">
![image](https://user-images.githubusercontent.com/94699627/230831649-dd998096-bda9-4e2f-962a-30b93339a646.png)
</p>

- using AD633 IC.

## Outputs of blocks

### Differentiator

input (square wave)        |  output 
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/94699627/230908579-9bcff140-90fc-4813-b82f-43208d96df50.png) | ![image](https://user-images.githubusercontent.com/94699627/230908428-91520685-4134-41f5-a752-7d0c16ae6bc7.png)

### Multiplier
```
inputs: red and blue
outputs: green
```
<p align = "center">
![image](https://user-images.githubusercontent.com/94699627/230910563-63c64e86-b0a9-40f4-9c2a-eec9ddd5fc0d.png) 
</p>

## Output of v3 (latest) circuit:
<p align = "center">
![image](https://user-images.githubusercontent.com/94699627/230988708-e9d3f767-67c9-4734-bfdb-9c560a62fb03.png)
</p>

`Input is a triangular wave superimposed with thermal noise`

`... work in progress`
