---
title: aboutPhone
---

## syber.system.aboutPhone(Object object)

获取手机信息，支持Promise调用

### 参数

**Object object**

| 属性    | 类型     | 是否必填 | 描述                                                         |
| ------- | -------- | -------- | ------------------------------------------------------------ |
| modem   | number   | 否       | 在双卡平台可用，默认为0，<br />0：取第一个modem的imei<br />1：取第二个modem的imei |
| success | function | 否       | 接口调用成功的回调函数                                       |
| fail    | function | 否       | 接口调用失败的回调函数                                       |

**object.success 回调函数参数**

**Object object**

| 属性           | 类型    | 描述                                 |
| -------------- | ------  | ------------------------------------ |
| id             | String  | 设备ID                               |
| brand          | String  | 设备品牌（未实现，下个版本开发）      |
| manufacturer   | String  | 设备生产商（未实现，下个版本开发）    |
| model  	 | String  | 设备型号（未实现，下个版本开发）  	 |
| name           | String  | 手机名称                             |
| imei           | String  | 移动设备国际识别码                    |
| simCardNumbers | Array   | 如果是双卡，有多个手机号              |
| imsis          | Array   | 如果是双卡，有多个国际移动用户识别码  |
| hardware       | String  |系统的平台类型 |
| KernelVersion  | String  | 内核版本 |
| osVersion      | String  | 系统版本号 |
| osVersionCode  | String  | 系统小版本号 |
| softwareVersion| String  | 系统版本号的简称或者代号 |
| height         | number  | 手机分辨率，高度 |
| width          | number  | 手机分辨率，宽度 |
| desktopAvailableHeight   | number  | 可使用窗口高度 （未实现，下个版本开发） |
| desktopAvailableWidth    | number  | 可使用窗口宽度 （未实现，下个版本开发） |
| statusBarHeight| String  | 状态栏的高度 （未实现，下个版本开发） |
| pixelRatio     | number  | 设备像素比|
| language       | String  | 系统语言|
| region     	 | String  | 系统地区|

**object.fail回调函数参数**

**Object object**

| 属性 | 类型   | 描述     |
| ---- | ------ | -------- |
| code | String | 错误码   |
| msg  | String | 错误信息 |

### 示例
```js
syber.system.aboutPhone({
    modem: 0,
	success:function(result){
        console.log('id: ', result.id);
        console.log('brand: ', result.brand);
        console.log('manufacturer: ', result.manufacturer);
        console.log('model: ', result.model);
        console.log('name: ', result.name);
        console.log('simCardNumbers: ', result.simCardNumbers);
        console.log('imsis: ', result.imsis);
        console.log('hardware: ', result.hardware);
        console.log('KernelVersion: ', result.KernelVersion);
        console.log('osVersion: ', result.osVersion);
        console.log('osVersionCode: ', result.osVersionCode);
        console.log('softwareVersion: ', result.softwareVersion);
        console.log('height: ', result.height);
        console.log('width: ', result.width);
        console.log('desktopAvailableHeight: ', result.desktopAvailableHeight);
        console.log('desktopAvailableWidth: ', result.desktopAvailableWidth);
        console.log('statusBarHeight: ', result.statusBarHeight);
        console.log('pixelRatio: ', result.pixelRatio);
        console.log('language: ', result.language);
        console.log('region: ', result.region);

    }
    fail:function(error){
        console.log('code: ', error.code);
    	console.log('msg: ', error.msg);
    }
});

syber.system.aboutPhone({
    modem: 0,
}).then(function(result) {
        console.log('id: ', result.id);
        console.log('brand: ', result.brand);
        console.log('manufacturer: ', result.manufacturer);
        console.log('model: ', result.model);
        console.log('name: ', result.name);
        console.log('simCardNumbers: ', result.simCardNumbers);
        console.log('imsis: ', result.imsis);
        console.log('hardware: ', result.hardware);
        console.log('KernelVersion: ', result.KernelVersion);
        console.log('osVersion: ', result.osVersion);
        console.log('osVersionCode: ', result.osVersionCode);
        console.log('softwareVersion: ', result.softwareVersion);
        console.log('height: ', result.height);
        console.log('width: ', result.width);
        console.log('desktopAvailableHeight: ', result.desktopAvailableHeight);
        console.log('desktopAvailableWidth: ', result.desktopAvailableWidth);
        console.log('statusBarHeight: ', result.statusBarHeight);
        console.log('pixelRatio: ', result.pixelRatio);
        console.log('language: ', result.language);
        console.log('region: ', result.region);

}).catch(function(error) {
    console.log('code: ', error.code);
    console.log('msg: ', error.msg);
});
```