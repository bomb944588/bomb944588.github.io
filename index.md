# 个人信息

<table border="0">
  <tr>
    <tr width="75%">
      <p><b>王宏超</b></p>
      <p><b>硕士研究生</b></p>
      <p><b>齐鲁空天信息研究院</b></p>
      <p><b>邮箱：ytyzsmdd@126.com</b></p>
      <p><b>地址：山东省济南市历城区空天信息科技馆，邮编250100</b></p>
    </tr>  
    <tr width="25%">
      <img src="/mine.jpg" width="40%">   
    </tr>
  </tr>
</table>

本科毕业于山东大学控制科学与工程学院，硕士毕业于北京理工大学自动化学院，导师为马宏伟老师和马中静老师，本科研究单片机与自控原理，硕士研究方向为计算机视觉与深度学习，主要应用于电力巡检无人机。现阶段在齐鲁空天信息研究院工作，目前主要研究语义分割在无人车与无人机方向的应用及服务部署、deepstream与mqtt目标检测、定位业务流程开发部署。
目前正在从事UE与自研仿真引擎的开发工作，UE方面主要从事Airsim模拟飞行底层代码修改、Cesium地理信息构建；自研仿真引擎方面主要从事轻量化引擎搭建、卫星、通信模型构建。

## 教育经历

控制理论与控制工程——北京理工大学自动化学院(2018.9-2021.6)

自动化——山东大学控制理论与工程学院(2014.9-2018.6)

## 发表文章

H. Wang, Y. Shao, S. Zou, Z. Ma and S. Zhao, "Detection of cotter pins missing of connection fittings on transmission lines of power system," 2021 40th Chinese Control Conference (CCC), 2021, pp. 6873-6879, doi: 10.23919/CCC52363.2021.9550162.
王宏超,邵云峰,马中静,等.基于深度学习增强的LSD杆塔倾斜度检测[J].电子测量与仪器学报,2021,35(09):204-213.DOI:10.13382/j.jemi.B2003733.

## 参与项目

### 杆塔识别与倾斜度检测

![杆塔倾斜度检测](/杆塔.png)

杆塔的倾倒会对整个电网产生严重的破坏并威胁周围居民的生命安全，电力巡检无人机利用计算机视 觉对杆塔进行巡检既节省了人力资源又显著地提高了电网的巡检效率。为了国网巡检人员在杆塔倾倒前及时 得到预警，文章为对电力巡检无人机中的基于计算机视觉的杆塔倾斜检测算法进行了研究，设计了一种基于 YOLOv3 的深度神经网络结合 LSD 线段提取方法对杆塔的倾斜进行检测。利用在山西电网无人机实际巡检的 杆塔图片制作杆塔的 VOC2007 数据集并利用 YOLOv3 神经网络对杆塔进行目标检测，并将检测后得到的 Bounding box 根据网络训练后的 mIOU 参数进行微调后作为 LSD 检测的 ROI。接着，该方法在 ROI 中将检 测的线段进行过滤和融合，根据杆塔特点进行杆塔的二次识别。最后利用得到的杆塔外边线做出该方向上的 杆塔中线并计算杆塔在该方向的倾斜度。该文中实验利用山西国网电力公司提供的数据进行验证，结果表明 杆塔的倾斜检测效果在各种拍摄高度和背景干扰下都较为精确，杆塔目标的正确识别率达到 97%，倾斜度检 测平均误差小于 0.85°。

### 开口销脱落检测

![开口销脱落检测](/开口销.png)

Connection fittings are widely used in the transmission lines. However, the missing of cotter pins usually happens
to the bolts of connection fittings due to the complex environment and aging. Cotter pins missing detection is one of the most
time-consuming and labor-intensive parts of manual judgment. It belongs to the small target detection because the cotter pins
with less features in the images are much smaller than other components on transmission lines. This paper designs a three-stage
cotter pin missing detecting method based on pictures taken by UAVs. The first stage utilizes YOLOv4 to detect insulators and
locate the connection fittings by extending the predicted bounding box of the insulator in the original pictures. The second stage
is a small object detection model based on an object network called Faster R-CNN with ResNet-101 backbone.The network of
this stage detects the bolts on the connection fittings and divides these bolts into two categories. The third stage utilizes the
DenseNet121 classification network to identify the integrity or missing of the cotter pins. The experimental dataset consists of a
public dataset and pictures captured by the UAVs from state grid. The result shows the accuracy of the bolts detection exceeds
90%, and the accuracy of front pins missing detector exceeds 85%. However, the lower accuracy of lateral pins detector due to
the samples of dataset.

### 无人机检测目标定位

基于mqtt数据传输协议，接受deepstream目标检测结果，将uav——imu、相机内外参与目标检测结果送入目标定位算法获取目标定位结果，并加入hash去重，防止同一目标重复发送，部署于px4与dji无人机。在终端设备上可实时获取定位结果、检测切片、实时rtmp视频流、无人机心跳包。

![目标定位系统](/目标定位.png)

### UE仿真系统开发

1、UE数据采集系统开发

以蓝图和UMG为主要开发工具，设计了一款具有天气时间控制、关卡场景切换、目标实时添加功能的数据采集工具，主要服务于深度学习算法中的数据集制作，具体服务于zc数据采集项目。

![模拟打击](/模拟打击.png)                ![数据采集界面](/数据采集.png)      

2.基于Airsim的插件开发

以C++为主要开发工具，对Airsim的源码进行修改，设计了坠机功能，在指定GPS点动态生成无人机（包括px-tpye）功能，目前正在进行混合模式开发（融合car-multirotor mode），使插件同时支持无人机与无人车。

此外搭建px4-stil，对从边缘设备发送指令到px4虚拟飞控接受指令并解析，发送mavlink消息给airsim中的px-tpye无人机进行了全流程开发。


### 无人模拟训练项目

对Airsim代码大量修改，修改无人机的控制逻辑，结合蓝图重新设计人机界面，封装MQTT包，实现无人机的实时状态发送、前端界面对打包项目的操控（包括场景切换、无人机控制）。
涉及到技术包括：无人机PID控制、桨叶机体等参数配置、输入轴映射信息读取、蓝图新类构建、Acotr、gamemode设计、MQTT消息交互等。

### 低空场景本体数字孪生

构建全球地形贴图、在指定位置构建逼真场景、以无人机为第一人称执行任务，与web前端实时交互，并将视频流信息通过pixel_streaming实时同步到前端。

### 自研仿真引擎及模型构建

主要从事卫星、通信等模型的构建、包括从AFsim代码抽取，构建轻量化仿真引擎，通过websocket、restful等通信中间件发送给前端实时渲染并实时操控。
```



For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/bomb944588/bomb944588.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
