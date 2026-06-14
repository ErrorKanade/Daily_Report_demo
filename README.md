Daily Failure Analysis Report
项目简介

Daily Failure Analysis Report 是一套面向生产制造与FA（Failure Analysis）团队设计的每日异常管理看板，用于汇总各产品模块在生产过程中的异常信息，并实时展示问题状态、失效率趋势以及改善进度。

系统目标是将原本分散在邮件、Excel、MES、会议记录中的异常信息进行集中管理，通过可视化方式帮助主管快速掌握生产风险与FA处理进展，提高问题响应效率和决策速度。
<img width="2561" height="1283" alt="image" src="https://github.com/user-attachments/assets/aadca018-0ffe-4072-8ede-5f87603c3b52" />

设计目标
1. 一屏掌握当日异常状态

页面顶部使用 KPI Summary Card 的方式展示：

今日收件（Received）
已结案（Closed）
分析中（Ongoing）
重大异常（Critical）

主管无需阅读详细报告即可快速了解：

当日异常总量
当前处理负荷
问题关闭率
是否存在高风险项目

实现从“阅读日报”向“查看状态”转变。

2. 聚焦问题而非数据

传统日报通常展示大量表格数据，但管理者真正关注的是：

哪些问题影响最大？

为什么发生？

什么时候能关闭？

因此左侧 CA 分类区域重点展示：
<img width="721" height="417" alt="image" src="https://github.com/user-attachments/assets/ba76fe88-2b86-4ed9-99d0-7ba626dc9395" />

项目	目的
Main	异常分类
Log Image	对应失效图片
Input Qty	投入数量
Fail Qty	失效数量
F/R	Fail Rate
Root Cause	根因分析
Result	当前改善状态

通过将 Root Cause 与 Result 并列展示，实现：

异常 → 原因 → 对策 → 状态

的完整闭环管理。

3. 风险优先级可视化

系统将异常按照处理状态进行颜色区分：

蓝色：信息展示
绿色：已完成
橙色：处理中
红色：重大异常

使管理者能够在数秒内识别：

当前卡点
高风险项目
资源投入重点

避免在大量文字中寻找关键信息。

4. 失效率趋势追踪

右侧 Fail 折线图用于展示：

Daily Fail Rate
Daily Input Quantity

趋势变化情况。
<img width="705" height="191" alt="image" src="https://github.com/user-attachments/assets/bf3e07dd-467a-4a7b-b2b4-05b25aaae159" />

设计目的：

帮助主管快速判断：

是否存在批次性异常
是否出现持续恶化趋势
改善措施是否有效

相比单纯查看当日数据，更关注：

Fail Rate 是在下降还是上升。

5. 模组维度分析
<img width="710" height="224" alt="image" src="https://github.com/user-attachments/assets/16d78475-8f1e-468b-8ec9-845c7bf80009" />

Module Choose 区域提供：

Camera 0
Camera 1
Camera 4

等模块切换功能。

设计思路：

生产异常往往具有模块集中性。

通过模块切换可快速定位：

哪个机种问题最多
哪个供应商贡献异常
哪个零件风险最高

实现：

总体异常 → 模组异常 → 零件异常

的逐层钻取分析。

交互设计
图表放大查看

右侧所有趋势图及统计图均支持点击放大查看。

目的：

由于主管会议中通常使用：

电脑投屏
大尺寸显示器
会议室电视

当需要分析某个异常趋势时，可以直接点击图表进入放大模式，查看完整数据细节，而无需额外导出报表。
<img width="2550" height="1393" alt="image" src="https://github.com/user-attachments/assets/d3a8ddd8-f8f9-4d1c-b2df-dafe2cfee514" />

支持：

图表放大显示
数据点详细查看
趋势追踪分析
会议讨论展示
使用场景
Daily Meeting（日会）

用于每日生产例会：

昨日问题回顾
今日异常汇总
Critical Issue追踪
Closing Status Review
FA Review Meeting

用于FA分析会议：

Root Cause Review
Corrective Action Review
Risk Assessment
Issue Closure Tracking
Manager Dashboard

供主管实时查看：

当前异常状态
Closing Rate
Critical Issue
Production Risk
未来规划

后续计划增加以下功能：

异常详情弹窗

点击异常项目后查看：

Log
图片
分析记录
改善措施
自动日报生成

从数据库自动生成：

Daily Report
Weekly Report
Monthly Report

减少人工整理时间。

邮件自动推送

每日定时发送：

Team Leader
FA Engineer
Manager

实现异常信息自动同步。

数据库整合

未来将与：

MES
Jira
Test System
SQL Database

进行数据联动，实现实时更新。

设计理念

“让主管在30秒内了解当天最重要的问题，让工程师在3分钟内找到需要处理的问题。”

本系统并非单纯展示生产数据，而是围绕 异常管理（Issue Management） 与 闭环改善（Closed Loop Improvement） 的理念设计，通过可视化方式连接生产、测试、FA与管理层，提升问题响应效率和决策质量。
