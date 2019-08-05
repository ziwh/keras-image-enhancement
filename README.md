# keras-image-enhancement
The image enhancement by keras.

keras_preprocessing.image model

1.图像的读写，保存操作
  list_pictures(directory, ext='jpg|jpeg|bmp|png...') : 此方法会将一个文件夹下所有的图片名称以一个列表形式返回（绝对路径），第一个参数为目录名，第二个参数为图片相关扩展名。
  
  load_img(path, grayscale=False, color_mode='rgb', target_size=None, interpolation='nearest'): 读取一张图片的方式，返回PIL.Image类的一个实例，具备Image类相关方法和属性
  
  save_img(path, img, data_format='channels_last', file_format=None, scale=True) : 将numpy数组保存为图片
  
  img_to_array(img, data_format='channels_last', dtype='float32'): 将PIL.Image图像对象转化为numpy数组
  
  array_to_img(x, data_format='channels_last', scale=True, dtype='float32') : 将一个3-D的numpy数组转化为一个 PIL.Image对象
  
2.图像的裁剪，旋转等预处理操作

row_axis: 
col_axis: 
channel_axis: 
            如果是（channel，row，col）的格式，则分别取值1,2,0，这也是默认情况）
            如果是（row，col，channel）的格式，则分别取值0,1,2，这也是默认情况）

  random_rotation(x, rg, row_axis=1, col_axis=2, channel_axis=0, fill_mode='nearest', cval=0.): 随机旋转一个图像, X为图片数组，rg为随机旋转角度最大值
  
  random_shift(x, wrg, hrg, row_axis=1, col_axis=2, channel_axis=0, fill_mode='nearest', cval=0.): 对一张图片进行随机的空间平移.  wrg, hrg: 宽度方向的移动范围.注意这里的取值虽然没有范围，但是一般约束在【0,1】之间，因为他指的是平移的像素占宽度的比值，如果太大，图像完全移动到了看不见的位置。
  
  random_shear(x, intensity, row_axis=1, col_axis=2, channel_axis=0, fill_mode='nearest', cval=0.): 随机剪切. intensity : shear角度
  
  random_zoom(x, zoom_range, row_axis=1, col_axis=2, channel_axis=0, fill_mode='nearest', cval=0.): 随机缩放 zoom_range: Tuple of floats; zoom range for width and height.即（width，height）大小为【0, 1】之间
