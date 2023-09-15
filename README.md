### Link to Dataset
1. [Mixamo - Human Bodies](https://drive.google.com/drive/folders/14SRpLT0X7yQPKJV7YDiZXEGJVnw1SkHN?usp=sharing) &emsp;


# Sythentic Human Bodies Dataset Creation

To create the Synthetic Bodies Dataset we followed the work from Irene et al in "Temporal Interpolation of Dynamic Point Clouds using Convolutional Neural Networks" 
In case of any doubt, you will find a different code to achive similar data creation at https://github.com/jelmr/pc_temporal_interpolation

### 1. Download the FBX files from Mixamo.

### 2. We recommend to organize the FBXs files with the following tree structure
```
Datasets
|-FBX
  |-Astra
    |- Arial_Evade.fbx
    |- Butterfly_Twirl.fbx
    |- (...)
  |-Brian
    |- Chicken_Dance.fbx
    |- Hit_to_Body.fbx
  (...)
```

### 3. To convert the FBX file to point cloud run the following Python:
You will need to edit the script to correct paths to the directories in your computer.

    `python create_dataset_color_full_body.py`

The Python script will  convert.FBX -> OBJ -> PLY. In the final step, the PLY are converted to NPY. For each point cloud, there will an npy file for the points and npy file for the color.

After the script you should have:
```
Datasets
|-FBX
  |-Astra
    |- Arial_Evade.fbx
|-OBJ_Bodys
  |-Astra
    |- Arial_Evade
      |- frame_000001.mtl
      |- frame_000001.obj
|-PLY_Bodys
  |-800000
    |-Astra
      |- Arial_Evade
        |- frame_000001.ply
        |- frame_000002.ply
|-NPY_Bodys
  |-800000
    |-Astra
      |- Arial_Evade
        |- frame_000001.npy
        |- frame_000002.npy
|-NPY_Bodys_Color
  |-800000
    |-Astra
      |- Arial_Evade
        |- frame_000001.npy
        |- frame_000002.npy
  ```


