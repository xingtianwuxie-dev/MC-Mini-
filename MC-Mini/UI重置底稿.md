# MC-Mini UI 重置底稿 · 2026-08-22

> 原版 UI 全部在 `D:\game\steam\steamapps\common\Hearts of Iron IV\interface\`（130 个 .gui）
> mod 覆盖姿势：mod 的 `interface\` 放**同名文件** = 整文件替换原版
> ★ = mod 已有覆盖/定制，重做时**别从原版重新拷**（会抹掉定制），在 mod 现有版本上改

## A. 主界面（玩家天天看）
| 文件 | 内容 | mod 状态 |
|---|---|---|
| topbar.gui | 地图顶栏（政点/人力/工厂/稳定度条） | 未动 |
| alerts.gui | 左上警报条 | 未动 |
| minimap.gui | 小地图 | 未动 |
| mapmodes_interface.gui | 地图模式按钮排 | 未动 |
| mapicons.gui | 地图单位图标 | 未动 |
| rightclickmenu.gui | 右键菜单 | 未动 |
| popupwindow.gui | 通用弹窗 | 未动 |
| ingamemenu / menubar | 菜单 | 未动 |

## B. 政府/政治
| 文件 | 内容 | mod 状态 |
|---|---|---|
| countrypoliticsview.gui | 政治总界面（政党/精神/法案） | ★已覆盖（意识形态图标配套） |
| nationalfocusview.gui | 国策树视图 | ★已覆盖 |
| countrydecisionview.gui | 决议界面 | 未动 |
| powerbalanceview.gui | **权力平衡（DWF 的 BOP 走这）** | 未动 |
| advisorroleselectionview.gui | 顾问任命 | 未动 |
| eventwindow.gui | 事件弹窗 | 未动 |
| detailedwindows.gui | 明细弹窗组 | 未动 |

## C. 军事
| 文件 | 内容 |
|---|---|
| countryarmyview / unitview | 陆军总览/编制 |
| naviesview / strategicairview | 海军/空军总览 |
| landcombat / navalcombat / navalcombatresultswindow | 战斗窗口 |
| unitleaderwindow / leadergroups / navyleaderview | 将领界面 |
| countryofficercorpview | 军团（HQ） |
| divisiondesignerview | 师编辑器 |
| theatreselector | 战区选择 |
| combatlogview / garrisonlogview | 战报/驻军日志 |
| countrydeploymentview | 部署界面 |
| countrylogisticsview | 后勤 |
| airselectionview / airwingdetails / airwingreorganization / airgroupview | 空军联队 |
| railway_gun | 列车炮 |

## D. 生产/科研/贸易
| 文件 | 内容 |
|---|---|
| countryproductionlineview | 生产线 |
| countryconstructionsview | 建设 |
| equipmentdesignerview / tank_designer_view / plane_designer_view | 装备/坦克/飞机设计器 |
| equipmentupgradedesignerwindow / equipmentoverview | 装备升级/库存 |
| countrytechtreeview / countrytechnologyview | 科研 |
| countrydoctrinetreeview | 学说树 |
| countrytradeview | 贸易 |

## E. 外交/情报/占领
| 文件 | 内容 |
|---|---|
| countrydiplomacyview | 外交 |
| peaceconferencewindow | 和会 |
| countryintelligenceagencyview / countryintelledger / operative / operativeleader | 谍报系统 |
| worldtensionwindowpopup | 世界紧张度弹窗 |
| waroverview / operationoverview | 战争/行动概览 |
| countryoccupationview / countrystateview | 占领区/州详情 |

## F. 音乐/自制窗口（mod 已有）
| 文件 | 内容 | 状态 |
|---|---|---|
| HJM_super_events.gui / .gfx | 四超事件窗 | ★新建 |
| music_station_base.gui / .gfx | 音乐电台 | ★新建（原版同名） |
| music_station_classic.gui / musicplayer.gui | 原版电台/播放器 | 未动 |

## G. 自定义界面参考模板（DLC 的 scripted_gui 窗口）
想做 mod 专属界面（BOP 专属视图/灾厄系统面板/四姐妹终端窗）就抄这些的结构：
- `sov_paranoia_system_scripted_gui.gui`（SOV 大清洗进度面板——BOP 式双轨UI的绝佳参考）
- `usa_congress_scripted_gui.gui`（国会两党席位）
- `JAP_imperial_influence_scripted_gui.gui`（派系影响力条）
- `RAJ_famine.gui`（饥荒计量条——灾厄猖獗度面板可抄）
- `ast_right_vs_left_campaign_scripted_gui.gui`（左右互搏）

## H. 前端/系统（一般不动）
frontend*（主菜单/多人）、settings、credits、load_screen、tutorialscreen、matchmaking、chat、ai_trace、nudge 本体

## 🔧 重排版两条正道
1. **nudge 工具**：游戏内开控制台（`~`）输入 `nudge` → GUI 页签 → 可视化拖动任意窗口元素 → 保存自动导出到 `Documents\Paradox Interactive\Hearts of Iron IV\interface\` → 拷回 mod 同名文件。比手改 x/y 坐标快十倍。
2. **坐标体系**：窗口内一律相对左上角；`orientation/origo = center` 居中锚；分辨率按 1920×1080 设计（缩放自适应）。

## mod 侧全部 UI 资产（现有）
- interface\：HJM_super_events.gui/.gfx、countrypoliticsview.gui★、nationalfocusview.gui★、music_station_base.gui/.gfx、HJM_focus_shine.gfx(23KB 国策shine)、HJM_equipment_icons.gfx、HJM_goals.gfx、HJM_ideas_icons.gfx、HJM_ideologies.gfx、HJM_tech_icons.gfx、MC_rescue_icons_0818.gfx、editor\HJM_focus_icons.gfx
- common\scripted_guis\HJM_super_events.txt（唯一 scripted_gui）
- gfx\interface\：goals / ideas / ideologies / technologies / topbar / topbar\musicplayer 图源
