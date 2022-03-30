# JDiip
欢迎进入京东工业互联网平台模型库！

该模型较为复杂，具体使用方法请咨询：

- 售前：400-623-0183
- 售后：400-098-8505转2
- 邮箱：jdcloud@jd.com

**SDK示例：**

1、可在以下链接下载，我们提供java与python两种语言的sdk供您选用：
- [Java SDK](http://jdai.oss.cn-north-1.jcloudcs.com/aisdk/sdk-java.zip)
- [Python SDK](http://jdai.oss.cn-north-1.jcloudcs.com/aisdk/sdk-java.zip)

2、查看每个API使用sdk调用的示例代码（示例代码仅作参考，请根据实际情况做相应调整）

```python
#!/usr/bin/python
# -*- coding: utf-8 -*-
# 本代码仅供参考，请根据实际情况进行调整
import wx_sdk

url = 'https://aiapi.jd.com/jdai/faceCompareV1'
bodyStr = '{"imgBase64A":"","imgBase64B":""}' #body中的内容
params = { 
    'appkey' : '0ccd6e004761ce2463bcab06054e0815',
    'secretkey' : 'your secretKey'
}

response = wx_sdk.wx_post_req( url, params, bodyStr=bodyStr )
print( response.text )
```

3、通过sdk计算sign：
- 把secretkey和timestamp参数值进行拼装 例如：

| 字段 | 参数 |
|--------|--------|
|secretkey	|2e148773a0338a8f2200ba90d445f084|
|timestamp	|1541491668060|

拼装结果为： ```2e148773a0337a8f2200ba90d445f0841541491668060```

- 在maven仓库的pom.xml中增加以下内容

```xml
<dependency>
    <groupId>com.google.guava</groupId>
    <artifactId>guava</artifactId>
    <version>27.1-jre</version>
</dependency>
```

- 使用MD5对拼装完的字符串进行加密，获取```sign```

```java
import com.google.common.hash.Hashing;
import java.nio.charset.Charset;

String secretKey = "2e148773a0338a8f2200ba90d445f084";
long timestamp = System.currentTimeMillis();
String sign = Hashing.md5().hashString(secretKey + timestamp, Charset.forName("UTF-8")).toString();
```

4、业务错误代码说明：

| 业务错误码 | 说明 |
|--------|--------|
|1	|成功|
|8	|校验信息错误|
|10	|无法识别|
|100 |	参数错误|
|103	|文件编码后大小超限|
|105	|查询失败|

### **现有模型：**



- [deeplabv3_mvp_coarse.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/deeplabv3_mvp_coarse.pth)
- [deeplabv3_mvp_fine.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/deeplabv3_mvp_fine.pth)
- [detection.caffemodel](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/detection.caffemodel)
- [hrnet_mvp_coarse.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/hrnet_mvp_coarse.pth)
- [hrnet_mvp_fine.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/hrnet_mvp_fine.pth)
- [LIP_BraidNet.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/LIP_BraidNet.pth)
- [LIP_CCNet.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/LIP_CCNet.pth)
- [LIP_CE2P.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/LIP_CE2P.pth)
- [LIP_DANet.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/LIP_DANet.pth)
- [LIP_DeepLabV3.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/LIP_DeepLabV3.pth)
- [LIP_DenseASPP.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/LIP_DenseASPP.pth)
- [LIP_HRNet.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/LIP_HRNet.pth)
- [LIP_OCNet.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/LIP_OCNet.pth)
- [LIP_PSPNet.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/LIP_PSPNet.pth)
- [pspnet_mvp_coarse.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/pspnet_mvp_coarse.pth)
- [pspnet_mvp_fine.pth](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/pspnet_mvp_fine.pth)
- [search.caffemodel](https://github.com/lxc86739795/human_vehicle_parsing_platform/releases/download/v0.1/search.caffemodel)


- [yolof_r101_c5_4x6_2x_coco](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__person_detection__yolof_r101_c5_4x6_2x_coco/yolof_r101_c5_4x6_2x_coco.zip)
- [ipcsn_ig65m_pretrained_bnfrozen_r152_32x2x1_58e_parthuman_rgb](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__person_action/ipcsn_ig65m_pretrained_bnfrozen_r152_32x2x1_58e_parthuman_rgb.zip)
- [ipcsn_sports1m_pretrained_bnfrozen_r152_32x2x1_58e_parthuman_rgb](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__person_action/ipcsn_sports1m_pretrained_bnfrozen_r152_32x2x1_58e_parthuman_rgb.zip)
- [ircsn_ig65m_pretrained_bnfrozen_r152_32x2x1_58e_parthuman_rgb](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__person_action/ircsn_ig65m_pretrained_bnfrozen_r152_32x2x1_58e_parthuman_rgb.zip)
- [ircsn_sports1m_pretrained_bnfrozen_r152_32x2x1_58e_parthuman_rgb](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__person_action/ircsn_sports1m_pretrained_bnfrozen_r152_32x2x1_58e_parthuman_rgb.zip)
- [yolof_r101_c5_4x6_2x_coco_part_color](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__part_detection__yolof_r101_c5_4x6_2x_coco_part_color/yolof_r101_c5_4x6_2x_coco_part_color.zip)
- [model_part_action_arm](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__part_action/arm.zip)
- [model_part_action_foot](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__part_action/foot.zip)
- [model_part_action_hand](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__part_action/hand.zip)
- [model_part_action_head](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__part_action/head.zip)
- [model_part_action_hip](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__part_action/hip.zip)
- [model_part_action_leg](https://github.com/SheldongChen/A-Baseline-Framework-for-Part-level-Action-Parsing-and-Action-Recognition/releases/download/model__part_action/leg.zip)