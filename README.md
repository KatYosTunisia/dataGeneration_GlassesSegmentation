## Generate Dataset
---
-add entry point glasses models to your blender project (make sure that each model contain tow component(body,lenses))  
-copy blender BlenderScript_DataGeneration.txt code and add it to blender python script file .  
## Glasses images segmentation
---
-make sure yoy have at minimum 4 cuda gpu vram ,if you dont have you can can simply use the jupyter notebook.  
-add your dataset to data folder with mask and image folders (maeke sure image and its correspond mask have the smae id )  
-install requirements.txt (use python 3.8)  
-create a wandb account and create an project, then change wandb connection in train.py file (or in train section if you use jupyter notebook)   
<pre>

$python3 -m venv yourenv
$./yourenv/bin/activate
$pip install -r requirements.txt

</pre>
-if you use juputer notebook just install wandb
<pre>
  !pip install wandb
</pre>
-to train on locally just run
<pre>
  $python3 train.py
</pre>
-you can check your artifacts and train metrics on wandb ui
## 2Dto3D
---




