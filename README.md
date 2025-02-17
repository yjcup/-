## 项目介绍

智慧医药系统（smart-medicine）是一个基于 SpringBoot 开发的标准 Java Web 项目。整体页面非常的简约大气，整合了目前非常火爆的 AIGC 生成式 AI（选用的阿里的通义千问大语言模型）技术充当智能医生，以此提升系统的 B 格，整体来看是一个偏向百科查询类的系统，功能设计的较为简单，便于初学者理解和学习，也适合学校中的项目答辩或者毕业设计。

### 角色介绍

系统共设计了三个角色：游客、用户、管理员。

1. 游客：尚未进行注册和登录。具备登录注册、疾病、药品的搜索、查询详情等权限。
2. 用户：除了游客的功能权限外，还具备登录、个人资料的修改、登录密码修改、意见反馈、智能医生咨询等权限。
3. 管理员：除了用户的功能权限外，还具备疾病管理、药品管理、反馈管理等权限。

## 系统截图

![image-20241101155046133](./assets/image-20241101155046133.png)

![image-20241101155054011](./assets/image-20241101155054011.png)

![image-20241101155102638](./assets/image-20241101155102638.png)

![image-20241101155202748](./assets/image-20241101155202748.png)

![image-20241101155215062](./assets/image-20241101155215062.png)

![image-20241101155300978](./assets/image-20241101155300978.png)

## 价格（良心价）

1. **199单项目**
2. **249包安装**

![1](./assets/1.jpg)

### 功能介绍

#### 游客功能介绍

| 功能模块     | 功能描述                                                   |
| ------------ | ---------------------------------------------------------- |
| 登录注册方面 | 注册成为系统用户                                           |
| 系统主页     | 浏览系统主页、疾病、药品信息搜索、详情的查看（统计浏览量） |

#### 用户功能介绍

| 功能模块     | 功能描述                                                     |
| ------------ | ------------------------------------------------------------ |
| 登录注册方面 | 填写用户信息进行账号注册（邮件接收验证码）、使用账号密码进行登录 |
| 个人资料方面 | 修改个人资料（姓名、年龄、手机号、头像等）、修改登录密码     |
| 系统反馈方面 | 提交系统反馈意见                                             |
| 智能医生方面 | 与智能医生进行交流聊天                                       |

#### 管理员功能介绍

| 功能模块     | 功能描述                                                     |
| ------------ | ------------------------------------------------------------ |
| 登录注册方面 | 填写用户信息进行账号注册（邮件接收验证码）、使用账号密码进行登录 |
| 个人资料方面 | 修改个人资料（姓名、年龄、手机号、头像等）、修改登录密码     |
| 系统反馈方面 | 提交系统反馈意见                                             |
| 智能医生方面 | 与智能医生进行交流聊天                                       |
| 疾病管理方面 | 发布疾病、编辑（名称、原因、症状、分类等）、删除药品等       |
| 药品管理方面 | 发布药品、编辑（名称、搜索关键词、功效、用法用量、类型等）、关联疾病、删除药品等 |
| 反馈管理方面 | 管理用户提交的反馈信息                                       |

## 技术介绍

### 前端

| 名称               | 描述                                                         |
| :----------------- | ------------------------------------------------------------ |
| HTML、CSS          | 用于设计网页的内容和样式                                     |
| JavaScript、JQuery | 作为开发 Web 页面的脚本语言，为网页添加各式各样的动态功能，为用户提供更流畅美观的浏览效果 |
| Bootstrap          | 基于 HTML、CSS、JavaScript 开发的简洁、直观、强悍的前端开发框架，使得 Web 开发更加快捷 |
| 前端模板           | 智慧医药系统页面模板，模板文件已放在分享项目目录下           |

### 后端

| 名称       | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| SpringBoot | SpringBoot 是由 Pivotal 团队提供的全新框架，其设计目的是用来简化新 Spring 应用的初始搭建以及开发过程。该框架使用了特定的方式来进行配置，从而使开发人员不再需要定义样板化的配置。通过这种方式，SpringBoot 致力于在蓬勃发展的快速应用开发领域成为领导者。 |
| SpringMVC  | Spring MVC 属于 SpringFrameWork 的后续产品，已经融合在 Spring Web Flow 里面。Spring 框架提供了构建 Web 应用程序的全功能 MVC 模块。 |
| MyBatis    | MyBatis 是一个 Java 持久化框架，它可以帮助开发者更轻松地管理数据库访问和SQL映射。它提供了一种简单且灵活的方式来进行数据库操作，同时还支持动态 SQL、缓存和批量操作等功能。 |
| Thymeleaf  | Thymeleaf 是一个流行的模板引擎，该模板引擎采用 Java 语言开发的，用于渲染 XML/XHTML/HTML5 内容的模板引擎。类似 JSP、Velocity、FreeMaker 等，它也可以轻易的与 Spring MVC 等 Web 框架进行集成作为 Web 应用的模板引擎。 |
| Druid      | Druid 是一个高效的数据查询系统，主要解决的是对于大量的基于时序的数据进行聚合查询。数据可以实时摄入，进入到 Druid 后立即可查，同时数据是几乎是不可变。通常是基于时序的事实事件，事实发生后进入 Druid，外部系统就可以对该事实进行查询。 |

- **阿里云 OSS 对象存储**

  阿里云对象存储 OSS（Object Storage Service）是一款海量、安全、低成本、高可靠的云存储服务，对于我们这个项目而言，所有的二进制文件，包括头像、用户上传的文件都是存储到了 OSS 里面（调用相关的工具类），在数据库中只是保存了文件的 URL 地址。通过这个 URL 地址就可以获取、下载指定文件

- **阿里云 AIGC 通义千问大语言模型**

  通义千问，是阿里云推出的一个超大规模的语言模型，功能包括多轮对话、文案创作、逻辑推理、多模态理解、多语言支持。能够跟人类进行多轮的交互，也融入了多模态的知识理解，且有文案创作能力，能够续写小说，编写邮件等。



