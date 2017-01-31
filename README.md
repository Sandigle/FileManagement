# FileManagement
该软件是一款集合了同人志文件名标准化、图像压制和文件替换功能的便于批量整理同人志的软件。

## 封面
![](https://github.com/Sandigle/FileManagement/raw/master/image/1.jpg) 

## 简介
该软件是一款集合了同人志文件名标准化、图像压制和文件替换功能的便于批量整理同人志的软件。

由于国内的二次创作领域存在诸多“吃力不讨好”的现象，同人志在分享时存在名称中乱加标签的问题，加之专用名词的不统一，不规范的问题，给同人志的整理和收藏带来了不小的困难。此外，部分同人志的图片质量过好体积巨大，不利于整理，故经常需要进行压制。但图片的分享存在编码和质量不统一的问题，在压制后需要对体积压缩结果进行对比，费时费力。对此，为了能更方便的整理同人志，需要一款软件来解决上述问题。

软件基于Java编写，所以运行必须要有Java运行库，需要“Java Version 8 Update 101”或在此之后的版本。有运行库后使用javaw.exe打开“同人志文件处理器_v2.4.jar”即可。

以下将按照“文件名标准化”、“图像压制”和“文件替换”的顺序介绍该软件。

如果想了解该软件的更多信息，或者报告Bug，可以联系编者。

邮箱：492302909@qq.com

## 文件名标准化
### 内容介绍
- 要解释什么是文件名标准化，就要先解释什么是“标准”。目前市面上存在两种命名标准，一是：“(时间) [制作方名 (作者名)] 作品名 (原作名) [汉化组名]”，在外国使用广泛；二是：“[汉化组名] (时间) [制作方名 (作者名)] 作品名 (原作名)”，在国内使用广泛。而个人的命名标准则是：“[制作方名 (作者名)] 作品名 (原作名) [汉化组名]”。
- 前两种标准经常在同人志分享网站出现，其初衷是相同的：一个同人志文件名应当包括参与制作的各方人员的署名，并且添加时间信息以便搜索。而国内之所以有不同的标准，笔者猜测是因为国内汉化盗窃现象严重，为了维护汉化者的尊严和利益，才将“汉化组名”提前。
- 这两种标准本身并无问题，但一旦混合出现，就难免造成麻烦。笔者提倡使用第一种，因为汉化工作一定是在同人志发布之后才会进行，位于同人志的制作流程末端，所以放在最后。此外，就像现代图书馆一样，在整理文件时，没有人会以汉化者为顺序排列文件，所以第二个标准显然不适合整理文件。至于“时间”一项，其初衷也是好的，便于搜索和记录作者的制作时间。但在实际中却存在多套体系，比如“C88”，“僕らのラブライブ! 10”等。全部使用一套体系还好，但混合使用则达不到按照时间排列的效果。所以个人的标准去掉了“时间”一项。这样一来文件以作者为顺序进行排列，达到了理想的效果。
### 处理细则
- 每一项内容之间严格保持一个半角空格的间隔。
- 去掉“[DL版]”、“[Digital]”和“[無修正]”的标识。
- 将“【】”、“（）”、“、”、“(Various)”和“(オリジナル)”转化为对应的“[]”、“()”、“, ”、“(よろず)”和“(Original)”
- 去掉“[中国翻訳]”和“[Chinese]”的标识，在不包含“汉化组名”的情况下，与文件名开头标注“★”。
- “原作名”全部以原作发布时的官方名称为标准，比如“東方”转化为“東方Project”。若官方名称全部由片假名构成，则转化为对应的英文，比如“ラブライブ”转化为“Love Live!”。具体转化可以自定义，转化对信息位于软件根目录下的“changeInfo.txt”中。
- 该功能只能处理在上述3个标准下的同人志。所以请不要使用该软件处理同人声音、动画的名称。
### 使用方法
- 1、指定“源头目录路径”
 - ![slide](https://github.com/Sandigle/FileManagement/raw/master/image/2.jpg) 
- 该目录下应该存放多个文件夹，其名称需要符合上述3个标准下的同人志。
- 2、指定“目标处理格式”
 - ![slide](https://github.com/Sandigle/FileManagement/raw/master/image/3.jpg) 
- 3、点击“名称标准化”
 - ![slide](https://github.com/Sandigle/FileManagement/raw/master/image/4.jpg) 
- 处理进度位于“名称标准化”按钮右侧，处理结果实时显示于下方文字区。
- 品红色表示处理成功；黑色表示文件名已经标准，不用处理；橙色表示处理失败，失败信息将显示于下方；蓝色是处理开始于结束的标记，最下方将显示处理成功文件的个数。
- 如果对处理结果不满意，可以点击“名称标准化”按钮右侧的“撤销”按钮。

## 图像压制
### 内容介绍
- 部分同人志的图片质量过好体积巨大，不利于整理，故经常需要进行压制。	软件内实际并没有压制图像的功能，由于市面上压制图像的软件很多，所以笔者觉得没有必要单独编写压制的程序，故此部分将调用外部软件进行处理，一般用户忽略该单元即可。

## 文件替换
### 内容介绍
- 同人志图片的分享存在编码和质量不统一的问题，在采用特定压制算法后体积并不一定会缩小。为了获得实际缩小的图片，需要对体积压缩结果进行对比。然后用符合标准图片替换原始图片，以达到压缩整体文件的目的。
### 注意事项
- 该单元操作无法撤销，如果担心意外损失，请自行备份源文件，或不要使用该功能。
- 请保证每个同人志文件夹内只有图片文件，为了便于处理，程序会自动删除带有".torrent", "Thumbs.db", ".xehdone", ".url"的文件。为了避免意外损失，程序会在文件数量不一致时停止。
### 使用方法
- 1、必须先经过“文件名标准化”和“图像处理”处理。
- 2、指定“目标目录路径”
 - ![](https://github.com/Sandigle/FileManagement/raw/master/image/5.jpg) 
- “目标目录路径”为“图像压制”后图像存放的目录，该路径下内文件格式应当与源头目录路径下文件格式完全相同。
- 3、设置“%阈值”
 - ![](https://github.com/Sandigle/FileManagement/raw/master/image/6.jpg) 
- 当压制后的图片大小缩小了3%以上时，才认为“图像压制”的结果足够好，可以用于“文件替换”。
- 4、点击“文件替换”
 - ![](https://github.com/Sandigle/FileManagement/raw/master/image/7.jpg) 
- 处理进度位于“文件替换”按钮右侧，第一栏是总体文件处理进度，第二栏是单一文件夹内处理进度；处理结果实时显示于下方文字区。
- 品红色表示处理成功；并在下方显示处理成功文件数和减少的体积；蓝色是处理开始于结束的标记，最下方将显示总处理成功文件的个数和减少的总体积。
- “重开”按钮用于开启下一轮文件处理。
