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
<img src = "https://user-images.githubusercontent.com/94699627/230831451-1d918f86-24fa-4e5a-bbeb-3f52bcaaa068.png">
</p>

- The differentiator gives inverted output, being corrected by cascading an active inverter.

### double differentiator
<p align = "center">
<img src = "https://user-images.githubusercontent.com/94699627/230831511-6e8e4771-2d05-40df-9666-1b74ea0cfce5.png">
</p>

- made by cascading two differentiators.

### multiplier
<p align = "center">
<img src = "https://user-images.githubusercontent.com/94699627/230831649-dd998096-bda9-4e2f-962a-30b93339a646.png">
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
<img src = "https://user-images.githubusercontent.com/94699627/230910563-63c64e86-b0a9-40f4-9c2a-eec9ddd5fc0d.png">
</p>

## Output of v3 (latest) circuit:
<p align = "center">
<img src = "https://user-images.githubusercontent.com/94699627/230988708-e9d3f767-67c9-4734-bfdb-9c560a62fb03.png">
</p>

`Input is a triangular wave superimposed with thermal noise`

## Hardware progress

So far I'm done with implementing the differentiator and double differentiator blocks on breadboard using UA741 op-amp. 

differentiator   |  double differentiator 
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/94699627/231481374-328587b3-a481-49eb-88b4-74c6dcfff375.png) | ![image](https://user-images.githubusercontent.com/94699627/232885079-14713c40-a9fb-4c03-af8e-8230e13a1415.png)

### Circuit in Multisim
This is the schematic that is being used for testing in simulation. 
<p align = "center">
<img src="https://user-images.githubusercontent.com/94699627/232205608-607d4f46-d497-4cee-ae5c-579dc68195fd.png">
</p>


`Differentiator block cascaded with inverter works`
`sine becomes cosine`
<p align = "center">
<img width="549" alt="image" src="https://user-images.githubusercontent.com/94699627/232988632-c9772f79-937c-48b7-97e6-281175895366.png">
</p>

`The multiplier works too. sine gets squared (notice how the freq is doubled).`
<p align = "center">
<img width="590" alt="image" src="https://user-images.githubusercontent.com/94699627/232989270-83c10b27-54ae-4454-be50-54308715387e.png">
</p>

`... work in progress`
