# Human-Motion-Detection-using-CNN-LSTM
The proposed system for human motion detection in videos includes two key components:
pixel improvement for foggy conditions and overlapping human detection using deep learning.
To address the issue of foggy conditions, the system incorporates pixel improvement techniques to enhance the visibility of human figures in low visibility environments. This involves analysing the video frames and using algorithms to improve the quality of the pixels, resulting in clearer and more visible human figures.
The second component of the system is overlapping human detection using deep learning. This involves training deep learning algorithms on large datasets of video footage to detect and track overlapping human figures, even when they are partially occluded or obstructed by other objects in the scene. By using deep learning techniques which includes CNN, LSTM, LRCN, the system can learn to identify and distinguish between different body parts and movements, even in complex and cluttered environments.

![image](https://github.com/Pavan5527/Human-Motion-Detection-using-CNN-LSTM/assets/85097031/d5babad3-3b8b-4b8b-bcf9-1fb139b974b6)
 <br/>
 
 
Trained Data
Model: "Sequential Outputs"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 conv_lstm2d (ConvLSTM2D)    (None, 20, 62, 62, 4)     1024      
                                                                 
 max_pooling3d (MaxPooling3D  (None, 20, 31, 31, 4)    0         
 )                                                               
                                                                 
 time_distributed (TimeDistr  (None, 20, 31, 31, 4)    0         
 ibuted)                                                         
                                                                 
 conv_lstm2d_1 (ConvLSTM2D)  (None, 20, 29, 29, 8)     3488      
                                                                 
 max_pooling3d_1 (MaxPooling  (None, 20, 15, 15, 8)    0         
 3D)                                                             
                                                                 
 time_distributed_1 (TimeDis  (None, 20, 15, 15, 8)    0         
 tributed)                                                       
                                                                 
 conv_lstm2d_2 (ConvLSTM2D)  (None, 20, 13, 13, 14)    11144     
                                                                 
 max_pooling3d_2 (MaxPooling  (None, 20, 7, 7, 14)     0         
 3D)                                                             
                                                                 
...
Trainable params: 44,524
Non-trainable params: 0
_________________________________________________________________
Model Created Successfully!


Model: "sequential_1"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 time_distributed_3 (TimeDis  (None, 20, 64, 64, 16)   448       
 tributed)                                                       
                                                                 
 time_distributed_4 (TimeDis  (None, 20, 16, 16, 16)   0         
 tributed)                                                       
                                                                 
 time_distributed_5 (TimeDis  (None, 20, 16, 16, 16)   0         
 tributed)                                                       
                                                                 
 time_distributed_6 (TimeDis  (None, 20, 16, 16, 32)   4640      
 tributed)                                                       
                                                                 
 time_distributed_7 (TimeDis  (None, 20, 4, 4, 32)     0         
 tributed)                                                       
                                                                 
 time_distributed_8 (TimeDis  (None, 20, 4, 4, 32)     0         
 tributed)                                                       
                                                                 
 time_distributed_9 (TimeDis  (None, 20, 4, 4, 64)     18496     
 tributed)                                                       
                                                                 
...
Trainable params: 73,060
Non-trainable params: 0
_________________________________________________________________
Model Created Successfully!


Steps to be followed for the execution:<br/>
input_video_file_path = f'test_videos/swinging.mp4' <br/>
predict_single_action(input_video_file_path, SEQUENCE_LENGTH) <br/>
VideoFileClip(input_video_file_path, audio=False, target_resolution=(500,200)).ipython_display()

