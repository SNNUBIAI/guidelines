# guidelines
实验室工作指南

## 必须学会的skill
- Git [教程](https://geeeeeeeeek.github.io/git-recipes/)  最新可能遇到的access token问题请参考[access token](https://blog.csdn.net/yjw123456/article/details/119696726)

## 代码提交规范
- 变量命名，尽可能全，不要缩写，可参考下划线命名法如`load_data`或者驼峰命名法如`loadData`。不要`ld`这样的缩写。
- 数据不要放到项目的目录下，应当放到工作站的`/home/public/`目录下，方便实验室所有人直接运行你的代码，参与你的工作。
- 不要将代码全部写到一个文件里面，尽可能的拆分功能模块，修改代码也会更加方便。
- 同一个函数写的不要太长，超过30行的代码实现理应思考是否能够拆分功能模块。

## 工作流程
- 参与一个新的项目应当首先在组织内新建一个私有的仓库（private），在开发过程中私有，待到开发完成视情况是否开源，若是开源则转为public的仓库。
- 寻找组内的合作者，建立一个team去完成项目。
