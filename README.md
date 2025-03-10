### 介绍
java毕业设计，微信小程序酒店管理系统
### 3000多套系统，需要联系
抠：3565014707 微：a13424421017

#### 软件架构
#### 分层架构设计
表现层（Web Layer）

controller 包（如 CommonController）处理 HTTP 请求，提供 RESTful API。

前端代码位于 resources/admin，Vue.js 实现动态页面交互。

业务层（Service Layer）

service 包（CommonService 接口 + CommonServiceImpl 实现类）封装核心业务逻辑。

持久层（DAO Layer）

dao 包（CommonDao）与 resources/mapper 下的 XML 文件结合，通过 MyBatis 操作数据库。

实体与数据模型

entity 包（如 ConfigEntity）定义数据库表映射的实体类。
vo（值对象）、view（视图模型）用于不同层间的数据传输。
#### 权限与安全机制
认证拦截器
AuthorizationInterceptor 校验用户登录状态，配合 @APPLoginUser 注解实现方法级权限控制。

前端路由权限
前端通过 router-static.js 控制页面访问权限，与后端接口权限联动。
#### 前后端分离模式
前端工程结构
Vue.js 单页应用（SPA）位于 resources/admin/src，通过 api.js 调用后端接口。

静态资源（图片、文件）存储在 static/upload，支持文件上传功能。

后端服务化
Spring Boot 提供 API 服务，通过 application.yml 配置项目参数。
#### 核心功能模块
#### 车辆全生命周期管理
车辆信息管理
qichexinxi：维护车辆基础属性（型号、状态等）。

出入库管理
qicheruku：记录车辆入库操作，关联库存状态变更。

投放与归还
qichetoufang：管理车辆投放区域（如 toufangdiqu 模块定义可投放地区）。
qicheguihai：处理车辆归还流程，可能涉及状态回调和费用计算。
#### 订单与用户管理
使用订单
shiyongdingdan：跟踪用户用车订单，记录租借时间、费用等。

用户体系
yonghu 和 users：管理后台用户和普通用户账户，支持增删改查及密码修改。
#### 系统配置与工具
动态参数配置
config 模块（ConfigEntity）：支持在线修改系统参数（如文件路径、API 密钥）。

第三方服务集成
BaiduUtil：集成百度 API，可能用于地图服务（如 LBS 定位）或 AI 能力（如 OCR 识别车牌）。
