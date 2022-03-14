
## Rendering and lifting keypoints to 3D
This documentation explains how to obtain 3D body keypoints for SMPL registration.

The scripts are located in ```utils/keypoints_3d_estimation```

**Contents**
1. [Multi-view rendering](#multi-view-rendering)
2. [2D pose prediction](#2d-pose-prediction)
3. [Lifting 2D pose to 3D](#lifting-2d-pose-to-3d)

### Multi-view rendering
Script: ```utils/keypoints_3d_estimation/01_render_multiview.py```

Sample command: ```python utils/keypoints_3d_estimation/01_render_multiview.py ../data/scan.obj -t ../data/scan_tex.jpg -r ../data/```

Script supports both meshes and point clouds

### 2D pose prediction
Script: ```utils/keypoints_3d_estimation/02_predict_2d_pose.py```

Sample command: ```python utils/keypoints_3d_estimation/02_predict_2d_pose.py ../data/scan_renders/ -r ../data/ -v```

Optionally hand and face joints can be predicted. 

### Lifting 2D pose to 3D
Script: ```utils/keypoints_3d_estimation/03_lift_kepoints.py```

Sample command: ```python utils/keypoints_3d_estimation/03_lift_keypoints.py ../data/scan.obj -k2 ../data/2D_pose.json -r ../data/3D_pose.json -cam ../data/scan_renders/p3d_render_data.pkl -c ./config.yml```