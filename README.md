# alloy_touch 使用文档

丝般顺滑的触摸运动方案

## 例子

[https://github.com/AlloyTeam/AlloyTouch](https://github.com/AlloyTeam/AlloyTouch)


## API


	var alloyTouch = new AlloyTouch({
        touch:"#wrapper",//反馈触摸的dom
        vertical: true,//不必需，默认是true代表监听竖直方向touch
        target: target, //运动的对象
        property: "translateY",  //被运动的属性
        min: 100, //不必需,运动属性的最小值
        max: 2000, //不必需,滚动属性的最大值
        sensitivity: 1,//不必需,触摸区域的灵敏度，默认值为1，可以为负数
        factor: 1,//不必需,表示触摸位移与被运动属性映射关系，默认值是1
        step: 45,//用于校正到step的整数倍
        bindSelf: false,
        maxSpeed: 2, //不必需，触摸反馈的最大速度限制 
        initialValue: 0,
        change:function(value){  }, 
        touchStart:function(evt, value){  },
        touchMove:function(evt, value){  },
        touchEnd:function(evt,value){  },
        tap:function(evt, value){  },
        pressMove:function(evt, value){  },
        animationEnd:function(value){  } //运动结束
 	})


通过对象的实例可以自行运动DOM:

	alloyTouch.to(value, time, ease)

- value是必填项
- time是非必填项，默认值是600
- ease是非必填项，默认值是先加速后减速的运动函数，CSS版本默认值是cubic-bezier(0.1, 0.57, 0.1, 1)

通过对象的实例可以自行停止DOM运动:

	alloyTouch.stop()

## 注意

仓库里面有alloytouch.js和alloytouch.css.js，他们的区别如下：

	alloytouch.js是使用 requestAnimationFrame 去运动，alloytouch.css.js使用transition去运动。后者性能更优~

默认下载下来用的是alloytouch.js，请自行修改



