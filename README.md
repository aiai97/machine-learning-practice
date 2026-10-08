# SDK 使用说明

### Java SDK 使用说明
使用前请登陆门户申请应用id和应用秘钥：

字段 | 描述       |获取说明 |
---- |----------|----
appId  | 应用id     | 登陆-应用管理-我的应用-应用id字段查看
appSecret | 应用秘钥     | 登陆-应用管理-我的应用-应用详情-应用秘钥
host   | 请求host地址 | API文档公共请求地址

引入依赖：
```mvn
        <dependency>
            <groupId>com.zt</groupId>
            <artifactId>zt-openapi-sdk</artifactId>
            <version>1.0.0</version>
        </dependency>
```
### 调用说明
```java
import com.zt.openapi.mode.AccessTokenResp;
import com.zt.openapi.service.OpenapiService;
import com.zt.openapi.service.impl.OpenapiServiceImpl;

import java.util.HashMap;

class ZtOpenapiSdkTests {

    public static void main(String[] args) {
        OpenapiService openapiService = new OpenapiServiceImpl("https://openapi-sbx.yunexpress.cn",
                "appId", "appSecret","sourceKey");
        AccessTokenResp accessTokenResp = openapiService.generateAccessToken();
        System.out.println(accessTokenResp);

//        String res = openapiService.getApi("/v1/order/info/get", new HashMap<String, Object>() {{
//            put("order_number", 1);
//        }});
        //https://openapi-sbx.yunexpress.cn/v1/order/last-mile/get

        String resPost = openapiService.postApi("/v1/order/last-mile/get", new HashMap<String, Object>());
        System.out.println(resPost);
        System.out.println(accessTokenResp);

    }

}
```# machine-learning-practice
