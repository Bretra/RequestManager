# RequestManager

>一个很简单的网络请求封装，post &amp; get ，功能简单，代码很少，很容易看懂和使用。

## 概述

VHRequestManager是个人封装的一个网络请求的类，是一个单例，支持简单的post和get请求，使用非常简单，就调用一个方法就能发起一个网络请求。

```
/// 网络超时时间
#define VHRequestManagerRequestTimeOut 30

/// 请求类型
typedef NS_ENUM(NSUInteger, VHHTTPMethod) {
    VHHTTPMethodGET,
    VHHTTPMethodPOST,
};

@interface VHRequestManager : NSObject

@property(class, nonatomic, readonly) VHRequestManager *sharedManager;

+ (instancetype)sharedManager;

// request
- (void)requestWithMethod:(VHHTTPMethod)method url:(NSString *)url params:(NSMutableDictionary *)params sucess:(void(^)(NSDictionary *))result failed:(void(^)(void))failure;

@end
```

## 说明

VHJsonTool类是一个提供json和字典互转方法的类
```
@interface VHJsonTool : NSObject

//字典转json
+ (NSString *)jsonStringFromDictionary:(NSDictionary *)dict;

//json转字典
+ (NSDictionary *)jsonStringToDictionary:(NSString *)jsonString;

@end
```

Reachability仅提供了判断网络状态的功能，无其他更多扩展。使用前切记引入系统库：
```
SystemConfiguration.framework
```

## 使用说明

直接将VHNetwork文件夹放入到项目中，并添加依赖库SystemConfiguration.framework就可以了。就是这么简洁。

缺点就是，功能少...haha


