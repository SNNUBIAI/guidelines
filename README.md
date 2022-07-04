# guidelines
实验室工作指南
- SNNUBIAI Lab: Shaanxi Normal University Brain Inspired Artificial Intelligence Lab
## 实用技能
- Git [教程](https://geeeeeeeeek.github.io/git-recipes/)  最新可能遇到的access token问题请参考[access token](https://blog.csdn.net/yjw123456/article/details/119696726)
- remote ssh，是vscode的一个插件，可以远程连接实验室的工作站，可参考[remote development](https://blog.csdn.net/qq_38120851/article/details/107696066)配置。

## 代码提交规范
- 变量命名，尽可能全，不要缩写，可参考下划线命名法如`load_data`或者驼峰命名法如`loadData`。不要`ld`这样的缩写。
- 数据不要放到项目的目录下，应当放到工作站的`/home/public/`目录下，方便实验室所有人直接运行你的代码，参与你的工作。
- 不要将代码全部写到一个文件里面，尽可能的拆分功能模块，修改代码也会更加方便。
- 同一个函数写的不要太长，超过30行的代码实现理应思考是否能够拆分功能模块。
- 提交的代码只包含代码部分，不要带任何数据和模型文件，比如为了防止训练完成后把模型push到仓库中，在建仓库的时候就应该写好`.gitignore`文件，把你存放模型的目录添加进入`.gitignore`文件，不要把模型之类的大文件push上来，大模型上传和下载都十分的不方便，需要模型和数据的组内工作站直接相互拷贝即可。

## 工作流程
- 参与一个新的项目应当首先在组织内新建一个私有的仓库（private），在开发过程中私有，待到开发完成视情况是否开源，若是开源则转为public的仓库。
- 寻找组内的合作者，建立一个team去完成项目。
