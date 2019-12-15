# cartographer代码阅读与补充

## 基本框架

位于workspace/src/cartographer/cartographer中

```
├── cloud
├── common          
├── ground_truth    似乎不重要
├── io                         输出建图结果的相关配置
├── mapping            包含2d和3d部分 定义了 local 和 global SLAM过程
├── metrics             
├── sensor                传感器数据与 fix frame  
└── transform          位姿变换相关代码
```

#### 12.15:

```
Sensor
├── collator_interface.h
├── compressed_point_cloud.cc
├── compressed_point_cloud.h
├── compressed_point_cloud_test.cc
├── data.h
├── fixed_frame_pose_data.cc
├── fixed_frame_pose_data.h
├── imu_data.cc
├── imu_data.h
├── internal
├── landmark_data.cc
├── landmark_data.h
├── landmark_data_test.cc
├── map_by_time.h
├── map_by_time_test.cc
├── odometry_data.cc
├── odometry_data.h
├── point_cloud.cc
├── point_cloud.h
├── point_cloud_test.cc
├── proto
├── range_data.cc
├── range_data.h
├── range_data_test.cc
├── timed_point_cloud_data.cc
└── timed_point_cloud_data.h
```

对sensor中imu定义文件和pointcloud文件进行了阅读,找到了frameID部分

## Eigen库_一个c++运算库

Vector为列向量, 3代表个数 d 为数据类型

```
const Eigen::Vector3d& imu_linear_acceleration); 3x1 double 列向量
```

