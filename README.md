## Generate Dataset
---
-add entry point glasses models to your blender project (make sure that each model contain tow component(body,lenses))  
-copy blender BlenderScript_DataGeneration.txt code and add it to blender python script file .  
## Glasses images segmentation
---
-make sure yoy have at minimum 4 cuda gpu vram ,if you dont have you can can simply use the jupyter notebook.  
-add your dataset to data folder with mask and image folders (maeke sure image and its correspond mask have the smae id )  
-install.txt (use python 3.8)   
<pre>
  '''bash
  $python3 -m venv yourenv
  $./yourenv/bin/activate
  $pip install -r requirements.txt
  '''
</pre>




