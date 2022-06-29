# Project3

## 1.导入项目

选择TFLClassify/build.gradle生成整个项目。项目包含两个module：finish 和 start，finish模块是已经完成的项目，start则是本项目实践的模块。
第一次编译项目时，弹出“Gradle Sync”，将下载相应的gradle wrapper 。

## 2.寻找TODO并添加代码

``` kotlin
 // TODO 1: Add class variable TensorFlow Lite Model
        // Initializing the flowerModel by lazy so that it runs in the same thread when the process
        // method is called.

        private val flowerModel = FlowerModel.newInstance(ctx) // 使用参数为ctx的构造方法构造FlowerModel对象
```

``` kotlin
// TODO 2: Convert Image to Bitmap then to TensorImage
            val tfImage = TensorImage.fromBitmap(toBitmap(imageProxy))
	// 转换图片为Bitmap再转换为TensorImage
```

``` kotlin
// TODO 3: Process the image using the trained model, sort and pick out the top results
            val outputs = flowerModel.process(tfImage)
                .probabilityAsCategoryList.apply {
                    sortByDescending { it.score }
                }.take(MAX_RESULT_DISPLAY) // 获取相似度ouputs，并按照降序排序，取相似度最高的为结果
```

``` kotlin
// TODO 4: Converting the top probability items into a list of recognitions
            for(output in outputs) {
                items.add(Recognition(output.label, output.score))
            } // 输出相似度最高的三个的标签和相似度
```

![image-12](photo/12.jpg)

![image-13](photo/13.png)
