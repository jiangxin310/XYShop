###待改

1. 在商品页面修改规格

1. 商品自动上下架（时间）

1. 折扣计算时间改为购物车时，折扣记录

1. 付款时间记录

1. 充值功能支付模块

1. 砍件功能-砍价活动、参与、日志、直接加订单、定时任务判断是否已经结束

1. 第二半价

1. 三级分销




###第二阶段完成的

1. 积分签到，积分记录（放sign_log表里）

1. 定时关闭团购订单（十分钟）、普通订单（包含有活动商品的订单，每天1/13点两次）、抢购订单（十分钟），每天2/14点检查结束的团购，每天8/22点检查结束的促销（所有活动）把商品状态归0

1. 订单后台展示规则修改

1. 团购规则修改(后台配置内容)

1. 支付前先看看是否选中送货地址

1. 结算时查活动状态，结束了-活动商品恢复原价

1. 分离出各活动（限时，限量等）订单，活动商品单独下单

1. 用户登录页面配适（各浏览器），用户黑名单

1. 充值卡数额修改


###完成的

使用教程：https://www.kancloud.cn/li2016/xiyi-manage-help/432741

系统基于Laravel 5.5，认证使用了RBAC，RBAC主要产生后台菜单

样式表，bootstrap

rbac 中间件控制打开页面是否有权限，同时判断是否登陆

添加调试工具Debugbar http://laravelacademy.org/post/2774.html，主页里关闭调试

提示信息，使用一次性session，在back()或者redirect()后->with('message','信息');

数据库备份功能（改造自V9）

附件删除

商城，分类下可筛选，库存及属性按sku来进行设计

下单及支付过程完整，支付使用包(omnipay-alipay)来完成，目前只支持支付宝与微信，微信做了扫码支付功能

微信包（overtrue/laravel-wechat-4^），PC与微信同步使用的是数据库存根auth_id的办法，pc端ajax轮询

后台订单管理

公用模块有：地区、社区、品牌、广告位、广告

促销活动包含：团购、活动、满赠、抢购、优惠券

团购、抢购里的商品，直接在不同的页面显示出来，在添加购物车的时候进行活动检测，支付后，进行活动库存的减少

活动结束后最好删除掉~~重点

留有自提字段，但没加功能

订单完成三天内可退货

加入图片lay加载