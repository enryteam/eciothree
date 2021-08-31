# ECIOTHREE

#### 介绍
ECIOTHREE 是基于threejs封装的一个适用于可视化物联网开发webgl库。
因为专注久了所以更专业，可视化|三维|3D|数字|智慧|智能|物联网|集成|网关|边缘|采控|unity|ue4|thingjs|threejs|webgl|大屏|仿真|虚拟|VR|大数据|云平台|iot|开发|app|小程序|软件|展厅|弱电|中台|农业|安全生产|园区|bim|建筑 等这些是都是能快速...

#### 使用文档
ECIOTHREE 帮助文档
ECIOTHREE V3.0.131
1.开始
1.1.文档版本
1.2.库资源引入
1.3.实例化对象
2.基础对象
2.1.渲染器
2.2.场景
2.3.相机
3.基础方法
3.1.渲染
3.2.销毁
3.3.轨道控制
3.4.窗口缩放
4.事件与动画
4.1.getIntersectObject
4.2.getClickPoint
4.3.createTween
4.4.flyTo
4.5.createBezierSection
4.6.singleTransitionScene
4.7.sceneTransition
4.8.createBreakGroup
4.9.createTransparentState
4.10.createWireFrameState
5.坐标与计算
5.1.objectToScreenCoords
5.2.geographicToPlaneCoords
5.3.geographicToVector3
5.4.getSphereHeightPoints
5.5.getTriangleArea
5.6.getMeshArea
5.7.getMeshVolume
5.8.getCenterPosition
5.9.getCirclePoints
5.10.findParentsByName
6.自定义物体
6.1.createSpriteText
6.2.createAnimateLine
6.3.cssRenderer
6.4.createHtmlCanvas
7.数据与模型
7.1.readSceneConfig
7.2.load
7.3.iterateLoad
7.4.exportModel
7.5.modelToBufferGeometry
7.6.imageToBufferGeometry
7.7.readGeoJson
8.着色与渲染
8.1.composer
8.2.changeColorShader
8.3.changeTextureShader
8.4.modelShader
8.5.textureColorTransitionShader
8.6.changeSceneShader
8.7.extendObjectShaderMaterial
1.开始
ECIOTHREE 是基于threejs封装的一个适用于可视化物联网开发webgl库。

1.1.文档版本
当前版本： V3.0.131

1.2.库资源引入
我们提供的库方法都应该基于如下引入访问：

CDN加速 <script src = "https://eciot.oss-cn-shanghai.aliyuncs.com/attms/eciothree.min.js"></script>
本地资源 <script src = "eciothree.min.js"></script>
1.3.实例化对象
初始化库操作

const ele = document.getElementById('eciothree')
const app = new ECIOTHREE(ele, {
axes: true, // 坐标辅助 默认false
gridHelper: false, // 网格辅助 默认false
updateTween: true, // 自动更新Tween 默认false
sortObjects: true, // 渲染排序 默认false
clearColor: '#040b2c', // 画布颜色 默认#000
autoRender: true, // 默认 false 自动渲染
autoResize: true // 默认 true
})

2.基础对象
渲染器
实例化对象 , renderer就是该对象的属性之一

场景
实例化对象 , scene就是该对象的属性之一

相机
实例化对象 , camera就是该对象的属性之一

const scene = app.scene
const renderer = app.renderer
const camera = app.camera
const _3d = app._3d
const clock = new _3d.Clock()
2.基础方法
渲染
这是使用requestAnimationFrame定义的渲染，可传入回调函数，重复渲染

app.render(() => {
...
})
销毁
销毁掉render，requestAnimationFrame，forceContextLoss等

app.destroy()

轨道控制
初始化OrbitControls，并绑定到app示例对象上，如果使用其他控制器，则自行引入。入参 dom元素，默认是renderer.domElement

const controls = app.OrbitControls(dom)

窗口缩放
调整大小, 默认窗口缩放 会 resize, 可以设置 autoResize = false 来取消

app.resize()

继续访问需要开发者权限！

本文档仅限在ECIOT V3.0商业正式合作项目内部团队使用。

© 2021-2031 51DANIU.CN 版权所有