# Medical Image Tumor Segmentation

SMP package에서 제공하는 DeepLabV3+를 이용한 2D tumor segmentation project  
Estimated 2D test Score (Dice score x .4 + Haudorff Distance x .6) : ~ 87%  

Optimization Algorithm : RAdam  
Learning Rate Schedule : Cosine Anealing Warm-up Schedule with max 0.001 as maximum learning rate, each interval size 150 epochs
Scheduler Reference https://gaussian37.github.io/dl-pytorch-lr_scheduler/  
Loss Function :  
* tversky for FN weight control (too many negative overrides positives and needs to reduce loss to prevent this)  
* BCE loss
* Lovasz Loss for continuous mapping of Discrete Jaccard loss Domain
* Hausdorff Loss to reduce HD (Reference: )

## Performance

### Ground Truth
![image](https://user-images.githubusercontent.com/32697109/206634874-708cf49d-53fa-4e1a-8fcb-4b2d86c4986b.png)

### Prediction
![image](https://user-images.githubusercontent.com/32697109/206634901-c3378f84-4c99-4eed-b9c3-cfc94a41783d.png)
