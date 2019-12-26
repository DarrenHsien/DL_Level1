# DL_Level1

## 模組應用區塊
	
### 1.tensorflow.keras.preprocessing.image
	
	-load_img : 讀取影像
	
	-img_to_array : 轉np.array
	
	-ImageDataGenerator : 數據集增強
		-rotation_range : 旋轉角度
		-width_shift_range : 水平平移幅度
		-height_shift_range : 垂直平移幅度
		-shear_range : 以弧度逆时针方向剪切角度
		-zoom_range : 隨機縮放比例
		-horizontal_flip : 水平映射
		-fill_mode : 超出邊界處理
		IDG.flow(image,batch_size= 1 ,save_to_dir=outputPath,save_prefix=prefix,save_format= 'jpg' ) 

### 2.tensorflow.keras.layers
	
	-Conv2D : 二維卷基層(卷積層)
		
		-filter : 輸出過濾器的數目
		-kerbel_size : 卷積核大小
		-strides : 卷積核移動步伐
		-padding : 是否填補0於外圍(valid or same)
		-input_shape : (height , width , depth)
	
	-MaxPooling2D : 最大值精簡矩陣(池化層)
		
		-pool_size : (vertical, horizontal)
		-strides : 移動步伐(默認pool_size)
		-padding : 是否填補0於外圍(valid or same)
		
	-Flatten : 圖像的格式從二維數組（28 x 28像素）轉換為一維數組（28 * 28 = 784像素）該層沒有學習參數。它只會重新格式化數據。
		
		-input_shape : (H , W)
		-data_format : 須給定數據為 channels_last channels_first(默認channels_last)
	
	-Dense : 緊密連接或完全連接的神經層
		
		-units : 輸出空間維度
		-activation : 要使用的激活功能。如果您未指定任何內容，則不會應用任何激活
	
	-Activation : 激活函數
	
	-BatchNormalization : 針對每批上層之激活函數輸出值標準化(中心0標準差1)
		
		-axis : 需歸一化的特徵軸(需參考channels_first(axis = 1) or channels_last(axis = 0))
		
	-Dropout : 


### 3.tensorflow.keras.optimizer 
	
	-SGD
	-Adagrad
	-RMSprop
	-Adam
	-schedules : 自定義訓練最佳化程序(用於搭配上述幾種最佳化方法)
		tf.keras.optimizers.schedules.InverseTimeDecay(  0.001,
								  decay_steps=STEPS_PER_EPOCH*1000,
								  decay_rate=1,
		
### 4.tensorflow metric select

	-迴歸時採用評估函式
		-mae
		
	-分類時採用評估函式
		-accuracy

### 5.tensorflow model loss func select

	-迴歸時採用損失函式
		-mse
		
	-分類時採用損失函式
		-sparse_categorical_crossentropy

### 6.tensorflow.keras.callbacks

	-EarlyStopping : 當監視的項目停止改善時，停止訓練。
		
		-monitor : 要監視的項目
		-patience : 沒有改善的時期數，之後訓練將停止。
