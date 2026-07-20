# CODEX_NOTES_2026-07-20

本文件是 2026-07-20 当天新增/整理内容的统一注释索引。它不被 HOI4 加载，只用于以后继续改 mod 时快速理解设计意图。

## 总原则

- HJM 的叙事方向是“古老帝国被战争唤醒，胜利越盛，裂缝越深”。新增内容不要只写凯旋，也要写债务、地方离心、穿越者权柄、藩属怨气和摄政政府的治理负担。
- `HJM.1` 的首个事件文案不要改。
- 国策本地化文案不要改，除非用户明确要求。
- 用户要求恢复过 `HJM.34` 和 `HJM.35` 的文本；这两个文本不要再主动“修正”成别的版本。
- `events/HJM.txt` 中 `HJM_news.*` 统一视为世界范围重大新闻；普通剧情推进使用 `country_event`。
- 重复的新闻尾段只在这里解释一次：新闻事件共用“帝国叙事尾段”，作用是把单条新闻接回同一条主线，即睡狮苏醒、恩威并用、胜利背后埋下战后危机。
- `.txt` 脚本内注释尽量用 ASCII 英文，避免中文注释和 HOI4 脚本粘连导致解析问题。
- `.yml` 本地化文件必须保留 UTF-8 BOM。

## 今日核心改动

### 1. HJM 事件与新闻文案统一

涉及文件：

- `localisation/simp_chinese/HJM_events_l_simp_chinese.yml`

注释：

- 将 HJM 事件/新闻统一为“赳赳老秦式、雄浑动员体、史书檄文帝国叙事”。
- 新闻事件强调对外叙事与世界震动，普通事件强调朝堂、村庄、账册、工坊和地方治理。
- 文案统一时保留了用户指定不动的内容：`HJM.1` 未改，国策文案未改。
- 后续如果要继续写事件，优先采用“具体场景 + 制度后果 + 帝国裂缝伏笔”的结构。

### 2. HJM 战时国策效果补全与注释

涉及文件：

- `common/national_focus/Hajimi.txt`
- `common/national_focus/HJM_war_focus.txt`

注释：

- 给缺少机制收益的国策补了政治点、稳定度、战争支持度、陆军经验、指挥点、装备、建筑或科研奖励。
- 这些数值不是单纯加强，而是把国策文本里的“动员、整合、反攻、清算”落实为可见收益。
- 脚本内对新增效果逐条加了 ASCII 注释；重复逻辑如“动员带来战支/经验”“战后结算带来 PP/稳定变化”不在每处重复解释。

### 3. 解放下界后的固定国策顺序

涉及文件：

- `common/national_focus/HJM_war_focus.txt`
- `localisation/simp_chinese/HJM_national_focus_l_simp_chinese.yml`

固定顺序：

- `HJM_liberate_nether`
- `HJM_is_it_over`，显示名“结束了？”
- `HJM_emperor_passes`，显示名“人皇逝世”
- `HJM_regional_situation_summary`，显示名“各地情况汇总”

注释：

- 这是用户明确指定的战后主线顺序，不要调整。
- `HJM_is_it_over` 负责战争结束后的疲惫与不确定感。
- `HJM_emperor_passes` 负责把 Notch 退场接入摄政时代。
- `HJM_regional_situation_summary` 负责开启战后治理地图，为后续决议和普通事件铺路。

### 4. 战后事件链与新闻

涉及文件：

- `events/HJM.txt`
- `localisation/simp_chinese/HJM_events_l_simp_chinese.yml`

事件：

- `HJM.35`：结束了？
- `HJM.36`：各地情况汇总
- `HJM_news.18`：下界战争告终
- `HJM_news.19`：摄政政府发布各地奏报

注释：

- `HJM.35` 和 `HJM.36` 是玩家本国看到的战后事件。
- `HJM_news.18` 和 `HJM_news.19` 是世界新闻，用来给其他国家一个宏观认知。
- 这一段不应写成“天下太平”，而应写成“大战结束，但帝国开始面对胜利的账单”。

### 5. 普通剧情事件链

涉及文件：

- `events/HJM.txt`
- `localisation/simp_chinese/HJM_events_l_simp_chinese.yml`

事件链：

- `HJM.37` 粮车到站
- `HJM.38` 穿越者工坊申请
- `HJM.39` 贡赋延期
- `HJM.40` 旧王冠的座次

注释：

- 这些事件不是新闻，目的是让战后剧情落到日常治理。
- 每个事件都给玩家一个小选择：救地方还是保中央、放权还是复核、宽限藩属还是派军监察、尊重旧臣还是推行摄政新规。
- 这些事件可以作为后续“摄政时代国策树”或“权力平衡系统”的前置铺垫。

### 6. 仆从国处置与反应事件

涉及文件：

- `common/national_focus/HJM_war_focus.txt`
- `events/HJM.txt`
- `localisation/simp_chinese/HJM_events_l_simp_chinese.yml`

国策到反应事件的对应关系：

- `HJM_skyfire_plan` -> `HJM.41` 焚天余烬
- `HJM_no_mercy` -> `HJM.42` 北境空册
- `HJM_homeland_return` -> `HJM.43` 洞穴旧旗入库
- `HJM_golden_offensive` -> `HJM.44` 金库誓约
- `HJM_magma_servant` -> `HJM.45` 熔炉登记
- `HJM_ash_policy` -> `HJM.46` 灰烬里的户籍
- `HJM_bloody_gate` -> `HJM.47` 城门下的宣誓
- `HJM_beneath_magma` -> `HJM.48` 黑石冷却之后

注释：

- 这些是普通 `country_event`，不是新闻。新闻负责“天下看见帝国处置”，反应事件负责“帝国内部开始承担处置后果”。
- 温和线反应重点：保留秩序、接管成本、地方试探、藩属表面顺从。
- 复仇线反应重点：威慑有效、治理昂贵、怨气积累、军纪和财政压力。
- 每个反应事件都设置一次性 flag，避免重复弹出。
- 效果数值保持克制，更多用于叙事反馈，不应变成爆强奖励。

### 7. 小国国策树

涉及文件：

- `common/national_focus/MC_minor_focuses.txt`
- `localisation/simp_chinese/MC_minor_focuses_l_simp_chinese.yml`

国家：

- `GWG` 洞穴聚落
- `LLL` 林地府邸
- `MDG` 末地国
- `MYR` 末影人起义军
- `XWY` 玄武岩城邦
- `ZLG` 猪灵堡垒

注释：

- 每个小国先写 5 个轻量国策，保证国家不再完全空白。
- 奖励以 PP、稳定、战支、陆军经验、指挥点、步枪库存、人力和少量工厂为主。
- 这些树目前是“可用骨架”，后续可以根据 HJM 处置线扩展为臣服、反叛或自治路线。

### 8. 超事件系统

涉及文件：

- `common/scripted_guis/HJM_super_events.txt`
- `interface/HJM_super_events.gui`
- `localisation/simp_chinese/HJM_super_events_l_simp_chinese.yml`
- `common/on_actions/HJM_on_actions.txt`
- `events/HJM.txt`

超事件：

- `HJM_war_superevent_gui`：HJM 与 HIM 开战时显示。
- `HJM_regency_superevent_gui`：`HJM.32` 摄政时代触发时显示。

注释：

- 超事件只负责营造阶段感，不直接改变局势。
- 开战超事件强调“烽烟既起”，摄政超事件强调“王冠仍在，但权力已经换手”。
- `scripted_gui` 关闭按钮只清对应 flag，避免反复显示。

### 9. 战后决议

涉及文件：

- `common/decisions/HJM_decisions.txt`
- `common/decisions/categories/HJM_decision_categories.txt`
- `localisation/simp_chinese/HJM_decisions_l_simp_chinese.yml`

决议分类：

- `HJM_postwar_regency_category`

决议：

- `HJM_postwar_village_relief`
- `HJM_reopen_nether_routes`
- `HJM_inspect_vassal_oaths`
- `HJM_limit_traveler_privileges`
- `HJM_demobilize_front_armies`
- `HJM_old_guard_compromise`

注释：

- 战后决议在 `HJM_regional_situation_summarized` 后显示。
- 设计目标是给玩家处理“胜利后的账”：救济村庄、重开下界路线、巡察藩属、限制穿越者、复员军队、安抚旧臣。
- 决议不是最终系统，后续可以扩展成摄政时代长期治理玩法。

### 10. 重要修复与检查

涉及文件：

- `events/HJM.txt`
- `common/national_focus/HJM_war_focus.txt`
- 多个本地化文件

注释：

- 修复过 `HJM.10` 与 `HJM.32` 都退休 Notch 的重复问题：现在 Notch 退场只保留在 `HJM.32` 摄政时代。
- 仆从国处置国策加了 `exists = yes` 判断，避免目标国家不存在时执行错误。
- LLL/MYR  punitive state transfer 限制为 HJM 实际控制的地区，避免意外转移未占领地区。
- 多轮 HOI4 `-debug` 测试未发现 HJM/MC-Mini 新增内容相关错误。
- 当前长期存在的 `IRQ_kamil_shabib` 报错来自游戏本体 `history/countries/IRQ - Iraq.txt`，不是 MC-Mini 本轮改动。

### 11. HIM 战败后遗产

涉及文件：

- `common/on_actions/HJM_on_actions.txt`
- `common/ideas/HJM.txt`
- `common/decisions/HJM_decisions.txt`
- `events/HJM.txt`
- `localisation/simp_chinese/HJM_ideas_l_simp_chinese.yml`
- `localisation/simp_chinese/HJM_decisions_l_simp_chinese.yml`
- `localisation/simp_chinese/HJM_events_l_simp_chinese.yml`

触发：

- 当 `HIM` 向 `HJM` 投降时，`on_capitulation` 中给 `HJM` 设置 `HJM_him_legacy_unlocked`，添加 `HJM_him_legacy_unsettled`，并延迟触发 `HJM.49`。

内容：

- `HJM_him_legacy_unsettled` 魔族遗患：轻度压低稳定、战支和政治点获取，表示战争结束后仍有残党、污染、唱片异常和俘虏口供压力。
- `HJM.49` 阴影未熄：第一份 HIM 战败遗产奏报，说明胜利后仍要处理残党、传送门污染、异常唱片和俘虏审讯。
- 新增战后决议：
  - `HJM_hunt_demon_remnants` 清剿下界残党
  - `HJM_purify_portal_scars` 净化传送门创痕
  - `HJM_seal_record_anomalies` 封存异常唱片
  - `HJM_interrogate_nether_prisoners` 审讯下界俘虏
  - `HJM_seal_herobrine_legacy` 封存 Herobrine 遗产

注释：

- 这套机制不让 HIM 的失败直接变成“地图干净”，而是留下战后阴影，服务摄政时代第二幕。
- 前四个决议分别处理军事、交通/污染、文化恐慌和情报四类遗产；全部完成后，第五个决议移除负面民族精神。
- 决议仍挂在 `HJM_postwar_regency_category` 下，避免新开太多分类。

## 后续建议

- 做“摄政时代”正式国策树，把今天的战后事件、战后决议、藩属反应串成第二阶段主线。
- 做“藩属忠诚/贡赋/叛乱风险”系统，让 GWG/ZLG/XWY/MDG 等不只是被处置一次，而是长期影响帝国战后政治。
- 给小国国策树增加分支：顺从帝国、暗中复仇、地方自治、被穿越者改造。
- 给超事件加音效和更正式的图片资产，现在主要是功能骨架。

### 12. HIM 叙事补强

涉及文件：

- `events/HIM.txt`
- `common/national_focus/HIM.txt`
- `localisation/simp_chinese/HJM_events_l_simp_chinese.yml`
- `localisation/simp_chinese/HJM_national_focus_l_simp_chinese.yml`

内容：

- 扩写 `HIM.1-HIM.10` 事件描述，让 HIM 线形成“下界集结 -> Herobrine 归位 -> 下界整备 -> 灾厄投诚 -> 末地开门 -> 主世界统治目标 -> 尸潮战书 -> 天空战线 -> 11号唱片黑函 -> 魔族同盟邀请”的敌方叙事链。
- 扩写 HIM 国策描述，使国策树和事件弹窗使用同一套黑暗政治叙事：下界不是散乱怪物，而是被 Herobrine 编成战争机器的阴影秩序。
- 清理 `common/national_focus/HIM.txt` 两处乱码中文注释，替换为 ASCII/English 注释，避免脚本注释再次出现编码粘连问题。

注释：

- HIM 文风不直接复刻 HJM 的“赳赳老秦式帝国檄文”，而是做成反面镜像：冷、黑、像下界史书和战争黑函。
- HIM 的叙事重点是说明“敌人为什么能聚成军、为什么能吸纳仆从国、为什么失败后仍会留下遗产”，从而和 HJM 的睡狮苏醒、仆从国处置、HIM 遗产系统闭环。

### 13. HJM 红石大炮国策图标

涉及文件：

- `gfx/editor/interface/focusIcon/HJM_redstone_cannon.dds`
- `interface/editor/HJM_focus_icons.gfx`
- `interface/HJM_focus_shine.gfx`
- `common/national_focus/Hajimi.txt`

素材来源：

- PNG 参考图：`C:\Users\26739\Documents\Tencent Files\2315489427\nt_qq\nt_data\Pic\2026-07\Ori\HJM_redstone_cannon.png`
- DDS 实装图：`C:\Users\26739\Downloads\HJM_redstone_cannon.dds`

内容：

- 将 `HJM_redstone_cannon.dds` 复制到 focusIcon 目录，作为红石大炮国策正式图标。
- 在 `HJM_focus_icons.gfx` 新增 `GFX_HJM_redstone_cannon`，指向 `gfx/editor/interface/focusIcon/HJM_redstone_cannon.dds`。
- 在 `Hajimi.txt` 的 `HJM_redstone_cannon` 国策中新增 `icon = GFX_HJM_redstone_cannon`。
- 在 `HJM_focus_shine.gfx` 中补齐 `GFX_HJM_redstone_cannon_shine`，并让旧预留的 `GFX_focus_HJM_redstone_cannon_shine` 也指向同一 DDS。

验证：

- 静态检查通过：`Hajimi.txt`、`HJM_focus_icons.gfx`、`HJM_focus_shine.gfx` 花括号平衡。
- 首轮 HOI4 `-debug -skiplauncher` 发现 `Missing icon shine for focus: HJM_redstone_cannon`，原因是国策 icon 名为 `GFX_HJM_redstone_cannon`，shine 需要同名后缀 `GFX_HJM_redstone_cannon_shine`。
- 补齐 shine 后复测通过；`error.log` 中不再有红石大炮图标、sprite、texture 或 shine 相关报错。
- 剩余日志噪音仍为本体旧问题：`IRQ_kamil_shabib`、`PRC_luo_ruiqing`。
