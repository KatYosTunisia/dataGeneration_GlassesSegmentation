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
-if you use jupyter notebook just install wandb
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
-make sure yoy have at minimum 8 cuda gpu vram ,if you dont have you can can simply use the jupyter notebook.   
-clone the repo and move to 2dto3d dir:   
<pre>
  !git clone https://github.com/KatYosTunisia/dataGeneration_GlassesSegmentation.git   
  %cd dataGeneration_GlassesSegmentation/2Dto3D 

</pre>
-install the requirements    
<pre>
  !pip install -r requirements.txt
</pre>
-install the ShapeNet datasets:
<pre>
!mkdir Datasets
!mkdir Datasets/ShapNet
!mkdir Datasets/Pix3D
!unzip pix3d.zip -d Datasets/Pix3D
!tar -zxvf ShapeNetVox32.tgz -C Datasets/ShapNet
!tar -zxvf ShapeNetRendering.tgz -C Datasets/ShapNet
</pre>
- change training parameters in the config file
- change paths according to your envirement
- <pre>
  '''python
  __C.DATASETS                                = edict()
__C.DATASETS.SHAPENET                       = edict()
__C.DATASETS.SHAPENET.TAXONOMY_FILE_PATH    = '2Dto3D/datasets/ShapeNet.json'
# __C.DATASETS.SHAPENET.TAXONOMY_FILE_PATH  = '2Dto3D/datasets/PascalShapeNet.json'
__C.DATASETS.SHAPENET.RENDERING_PATH        = 'Datasets/ShapeNet/ShapeNetRendering/%s/%s/rendering/%02d.png'
# __C.DATASETS.SHAPENET.RENDERING_PATH      = 'Datasets/ShapeNet/PascalShapeNetRendering/%s/%s/render_%04d.jpg'
__C.DATASETS.SHAPENET.VOXEL_PATH            = 'Datasets/ShapeNet/ShapeNetVox32/%s/%s/model.binvox'
__C.DATASETS.PASCAL3D                       = edict()
__C.DATASETS.PASCAL3D.TAXONOMY_FILE_PATH    = '2Dto3D/datasets/Pascal3D.json'
__C.DATASETS.PASCAL3D.ANNOTATION_PATH       = 'Datasets/PASCAL3D/Annotations/%s_imagenet/%s.mat'
__C.DATASETS.PASCAL3D.RENDERING_PATH        = 'Datasets/PASCAL3D/Images/%s_imagenet/%s.JPEG'
__C.DATASETS.PASCAL3D.VOXEL_PATH            = 'Datasets/PASCAL3D/CAD/%s/%02d.binvox'
__C.DATASETS.PIX3D                          = edict()
__C.DATASETS.PIX3D.TAXONOMY_FILE_PATH       = '2Dto3D/datasets/Pix3D.json'
__C.DATASETS.PIX3D.ANNOTATION_PATH          = 'Datasets/Pix3D/pix3d.json'
__C.DATASETS.PIX3D.RENDERING_PATH           = 'Datasets/Pix3D/img/%s/%s.%s'
__C.DATASETS.PIX3D.VOXEL_PATH               = 'Datasets/Pix3D/model/%s/%s/%s.binvox'
  '''
</pre>  





