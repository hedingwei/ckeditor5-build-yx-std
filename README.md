
CKEditor 5 的自定义build，支持imageUpload（简单版本）
========================================

## 安装
```bash
npm install https://github.com/hedingwei/ckeditor5-build-yx-std.git
```

##图片上传功能

```javascript
<script>
	ClassicEditor.create( document.querySelector( '#editor' ), {
        simpleUpload: {
				uploadUrl: 'http://120.76.121.210:10010/pmsapi/common/simple-upload',
			}
    } )
		.then( editor => {
			window.editor = editor;
		} )
		.catch( err => {
			console.error( err.stack );
		} );
</script>
```
## 服务端规则

上传服务器的url接收一个名为uploadfile参数作为文件名，并且应该返回图片的URL。 

* 成功返回：
```json
{
    "uploaded": true,
    "url": "http://127.0.0.1/uploaded-image.jpeg"
}
```
* 失败返回：

```json
{
    "uploaded": false,
    "error": {
        "message": "could not upload this image"
    }
}
```

其余部分使用参考标准的CKEditor 5 classic build


CKEditor 5 classic editor build
========================================

[![Join the chat at https://gitter.im/ckeditor/ckeditor5](https://badges.gitter.im/ckeditor/ckeditor5.svg)](https://gitter.im/ckeditor/ckeditor5?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![npm version](https://badge.fury.io/js/%40ckeditor%2Fckeditor5-build-classic.svg)](https://www.npmjs.com/package/@ckeditor/ckeditor5-build-classic)
[![Dependency Status](https://david-dm.org/ckeditor/ckeditor5-build-classic/status.svg)](https://david-dm.org/ckeditor/ckeditor5-build-classic)
[![devDependency Status](https://david-dm.org/ckeditor/ckeditor5-build-classic/dev-status.svg)](https://david-dm.org/ckeditor/ckeditor5-build-classic?type=dev)

The classic editor build for CKEditor 5. Read more about the [classic editor build](https://docs.ckeditor.com/ckeditor5/latest/builds/guides/overview.html#classic-editor) and see the [demo](https://docs.ckeditor.com/ckeditor5/latest/examples/builds/classic-editor.html).

## Documentation

See:

* [Installation](https://docs.ckeditor.com/ckeditor5/latest/builds/guides/integration/installation.html) for how to install this package and what it contains.
* [Basic API](https://docs.ckeditor.com/ckeditor5/latest/builds/guides/integration/basic-api.html) for how to create an editor and interact with it.
* [Configuration](https://docs.ckeditor.com/ckeditor5/latest/builds/guides/integration/configuration.html) for how to configure the editor.
* [Creating custom builds](https://docs.ckeditor.com/ckeditor5/latest/builds/guides/development/custom-builds.html) for how to customize the build (configure and rebuild the editor bundle).

## Quick start

First, install the build from npm:

```bash
npm install --save @ckeditor/ckeditor5-build-classic
```

And use it in your website:

```html
<div id="editor">
	<p>This is the editor content.</p>
</div>
<script src="./node_modules/@ckeditor/ckeditor5-build-classic/build/ckeditor.js"></script>
<script>
	ClassicEditor
		.create( document.querySelector( '#editor' ) )
		.then( editor => {
			window.editor = editor;
		} )
		.catch( err => {
			console.error( err.stack );
		} );
</script>
```

Or in your JavaScript application:

```js
import ClassicEditor from '@ckeditor/ckeditor5-build-classic';

// Or using the CommonJS version:
// const ClassicEditor = require( '@ckeditor/ckeditor5-build-classic' );

ClassicEditor
	.create( document.querySelector( '#editor' ) )
	.then( editor => {
		window.editor = editor;
	} )
	.catch( err => {
		console.error( err.stack );
	} );
```

**Note:** If you are planning to integrate CKEditor 5 deep into your application, it is actually more convenient and recommended to install and import the source modules directly (like it happens in `ckeditor.js`). Read more in the [Advanced setup guide](https://docs.ckeditor.com/ckeditor5/latest/builds/guides/integration/advanced-setup.html).

## License

Licensed under the terms of [GNU General Public License Version 2 or later](http://www.gnu.org/licenses/gpl.html). For full details about the license, please check the `LICENSE.md` file.
