模型训练
获取数据
本实验先从较小的数据集开始训练，当然越多的数据，模型精度更高。
image_path = tf.keras.utils.get_file(
      'flower_photos.tgz',
      'https://storage.googleapis.com/download.tensorflow.org/example_images/flower_photos.tgz',
      extract=True)
image_path = os.path.join(os.path.dirname(image_path), 'flower_photos')
1
2
3
4
5
这里从storage.googleapis.com中下载了本实验所需要的数据集。image_path可以定制，默认是在用户目录的.keras\datasets中。
运行示例
一共需4步完成。
第一步：加载数据集，并将数据集分为训练数据和测试数据。
第二步：训练Tensorflow模型
第三步：评估模型
第四步，导出Tensorflow Lite模型