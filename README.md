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

















