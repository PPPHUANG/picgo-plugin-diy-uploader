# picgo-plugin-diy-uploader

plugin for [PicGo](https://github.com/Molunerfinn/PicGo)

- Diy Web图床上传

## 使用

### 图床配置

- url: 图床上传API地址
- paramName: POST文件参数名
- jsonPath: 图片URL所在返回值的JsonPath(eg:data.url)
- customHeader: 自定义请求头 标准JSON(eg: {"key":"value"}
- customBody: 自定义Body 标准JSON(eg: {"key":"value"})


### 自定义

如果上传接口直接返回了完整的图片路径，可以通过`jsonPath`直接获取到，无需自定义。

如果需要根据接口的返回值拼凑图片路径，可以修改index.js中的示例代码。
```ts
body = JSON.parse(body)
let imgUrl = body
let host = imgUrl.host
let id = imgUrl.id
// TODO 根据自己的接口返回构造图片路径 eg: imgUrl = 'http://img.img.com/display/' + host + id
imgUrl = 'http://img.img.com/display/' + host + id
```

修改完之后直接在PicGo 插件设置中导入包即可。
