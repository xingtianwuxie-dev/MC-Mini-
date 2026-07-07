# MC-Mini 项目检查报告

生成日期：2026-06-24  
项目路径：`C:\Users\Administrator\Documents\Paradox Interactive\Hearts of Iron IV\mod\MC-Mini`  
项目类型：《Hearts of Iron IV》Mod

## 1. 项目概况

`MC-Mini` 是一个以 Minecraft 风格势力为主题的 HOI4 Mod。当前核心玩法围绕两个自定义国家展开：

- `HJM`：Hajimi / MC 帝国，当前主玩法国家。
- `HIM`：Demons / 魔族，当前敌对势力。

`descriptor.mod` 当前内容：

| 字段 | 当前值 |
| --- | --- |
| name | `MC-Mini` |
| version | `0.0.2` |
| supported_version | `1.19.0.1` |
| tags | `Gameplay` |

项目已经包含国家标签、国家历史、角色、理念、意识形态、国策、事件、决议、本地化、旗帜、头像、国策图标、地图建筑与大量州历史文件，属于已经成形但仍需要收口测试的 Mod 项目。

## 2. 文件规模

当前项目共有 1187 个文件，总大小约 6.02 MB。

按顶层目录统计：

| 目录 | 文件数 | 大小 |
| --- | ---: | ---: |
| `history` | 1096 | 约 541.2 KB |
| `gfx` | 56 | 约 2221.8 KB |
| `common` | 16 | 约 52.3 KB |
| `interface` | 5 | 约 33.4 KB |
| `map` | 5 | 约 3272.7 KB |
| `_codex_disabled` | 2 | 约 0.2 KB |
| `localisation` | 2 | 约 24.0 KB |
| `events` | 2 | 约 10.2 KB |
| 项目根目录 | 2 | 约 11.4 KB |
| `.paradoxart` | 1 | 约 0.4 KB |

按扩展名统计：

| 类型 | 文件数 | 大小 | 用途 |
| --- | ---: | ---: | --- |
| `.txt` | 1119 | 约 3876.4 KB | HOI4 脚本、历史、地图文本 |
| `.tga` | 30 | 约 211.5 KB | 旗帜 |
| `.png` | 16 | 约 448.9 KB | 头像、装备图标、国策图标 |
| `.dds` | 10 | 约 1561.4 KB | 国策编辑器图标 |
| `.gfx` | 4 | 约 10.0 KB | Sprite 定义 |
| `.yml` | 2 | 约 24.0 KB | 简体中文本地化 |
| `.disabled` | 2 | 约 0.2 KB | 被禁用的脚本备份 |
| `.md` | 1 | 约 11.3 KB | 项目报告 |
| `.mod` | 1 | 约 0.1 KB | Mod 描述文件 |
| `.json` | 1 | 约 0.4 KB | Paradox Art 数据 |
| `.gui` | 1 | 约 23.4 KB | GUI 覆盖 |

## 3. 目录结构判断

项目当前主要目录用途如下：

| 路径 | 说明 |
| --- | --- |
| `common/country_tags` | 自定义国家标签 `HJM`、`HIM` |
| `common/countries` | 国家颜色、图形文化等 |
| `common/characters` | HJM/HIM 角色、领导人和将领 |
| `common/national_focus` | HJM/HIM 国策树，以及 ABDA 共享分支文件 |
| `common/ideas` | HJM 初始理念、设计商、理论家 |
| `common/ideologies` | 自定义意识形态 |
| `common/decisions` | HJM 13 号唱片战争倒计时决议 |
| `events` | HJM/HIM 剧情事件 |
| `history/countries` | 国家开局历史 |
| `history/units` | HJM 开局部队和师模板 |
| `history/states` | 1081 个州历史文件 |
| `gfx/flags` | HJM/HIM 旗帜 |
| `gfx/leaders` | HJM/HIM 角色头像 |
| `gfx/interface` | 国策与装备图标 |
| `interface` | GFX 和 GUI 定义 |
| `localisation/simp_chinese` | 简体中文本地化 |
| `map` | 建筑和战略区域文件 |
| `_codex_disabled` | 当前不会被游戏加载的备份脚本 |

`common/dynamic_modifiers`、`common/idea_tags`、`common/on_actions` 等目录当前存在，但本次扫描未发现其中有加载文件。

## 4. 核心内容

### 国家标签

`common/country_tags/HJM_countries.txt` 定义了：

- `HJM = "countries/Hajimi.txt"`
- `HIM = "countries/HIM.txt"`

对应国家文件存在：

- `common/countries/Hajimi.txt`
- `common/countries/HIM.txt`

### 国家历史

`history/countries/HJM - Hajimi.txt`：

- 首都：`1036`，注释为武汉。
- 开局 OOB：`HJM_1936`。
- 科研槽：3。
- 稳定度：0.6。
- 战争支持度：0.7。
- 执政党：`feudalist`。
- 初始角色：`HJM_wutu`、`HJM_Notch`。
- 初始理念：`Wulin`、`liuxue`、`tongmeng`、`bingyuanqiangzheng`。

`history/countries/HIM - Demons.txt`：

- 首都：`439`。
- 科研槽：2。
- 稳定度：0.45。
- 战争支持度：0.8。
- 执政党：`fascism`。
- 初始角色：`HIM_Herobrine`、`HIM_Zombie_Overseer`。
- 初始领导人：`HIM_Zombie_Overseer`。
- 当前没有 `oob = ...`，因此 HIM 开局不会加载预置部队。

### 开局部队

当前只有 `history/units/HJM_1936.txt`：

- 定义 4 个 HJM 师模板：
  - `HJM Militia`
  - `HJM Infantry Division`
  - `HJM Elite Infantry`
  - `HJM Iron Golem Armor`
- 定义 13 个 HJM 开局师。
- HIM 当前没有 `history/units/HIM_1936.txt`。

### 国策

国策文件统计：

| 文件 | focus_tree 数 | focus 数 | 行数 |
| --- | ---: | ---: | ---: |
| `common/national_focus/Hajimi.txt` | 1 | 17 | 341 |
| `common/national_focus/HIM.txt` | 1 | 8 | 217 |
| `common/national_focus/abdacom_shared_branch.txt` | 0 | 0 | 1094 |

`HJM` 主线包括：

- 开局与预兆：`MC_start`、`HJM_underground_riot`、`HJM_illager_spy`、`HJM_brother_returns`
- 防御路线：`HJM_village_defense`、`HJM_iron_golem`
- 红石科技路线：`HJM_redstone_research`、`HJM_redstone_cannon`
- 外交路线：`HJM_outsider_contact`、`HJM_player_pact`
- 反攻与终局：`HJM_liberate_village`、`HJM_player_general`、`HJM_nether_strike`、`HJM_notch_vanished`、`HJM_dignity_blade`、`HJM_total_war`、`HJM_liberate_nether`

`HIM` 主线包括：

- `HIM_demon_host`
- `HIM_evil_resurgence`
- `HIM_nether_mobilization`
- `HIM_illager_defectors`
- `HIM_open_the_gate`
- `HIM_overworld_dominion`
- `HIM_zombie_siege`
- `HIM_sky_is_not_the_limit`

### 事件

事件文件统计：

| 文件 | country_event 数 | 行数 |
| --- | ---: | ---: |
| `events/HJM.txt` | 25 | 423 |
| `events/HIM.txt` | 10 | 156 |

本次检查确认：事件 ID 扫描中出现的 `HIM.9`、`HJM.19`、`HJM.20`、`HJM.21` 等重复行是事件触发引用和事件定义同时出现造成的，不是重复定义。

### 决议

决议文件：

- `common/decisions/categories/HJM_decision_categories.txt`
- `common/decisions/HJM_decisions.txt`

核心分类为 `HJM_record_13_category`。核心任务为 `HJM_record_13_war_countdown`：

- 在 `HJM_brother_returns` 后可见。
- 倒计时 180 天。
- 倒计时结束后，如果 HIM 存在且 HJM 尚未与 HIM 交战，HJM 会向 HIM 宣战。
- `HJM_delay_record_13_war` 可花费 50 政治点数延后 30 天。

### 本地化

本地化文件统计：

| 文件 | 键数量 | 行数 |
| --- | ---: | ---: |
| `localisation/simp_chinese/Hajimi_l_simp_chinese.yml` | 159 | 160 |
| `localisation/simp_chinese/HJM_countries_l_simp_chinese.yml` | 109 | 119 |

两个文件均包含 `l_simp_chinese:` 头。主线国策、事件、决议、国家名、政党名、角色名、理念名、意识形态名和设计商文本都有覆盖。

### 地图与州历史

`history/states` 当前有 1081 个州历史文件：

- 最小州 ID：1。
- 最大州 ID：1081。
- 文件名中的州 ID 未发现重复。

`map` 目录包含：

- `map/buildings.txt`
- `map/strategicregions/141-East India.txt`
- `map/strategicregions/146-Himalayas.txt`
- `map/strategicregions/250-Kham.txt`
- `map/strategicregions/251-Ngari.txt`

这说明项目包含大量地图相关覆盖，后续兼容性测试需要重点关注。

## 5. 静态检查结果

本次执行的检查：

- 统计全项目文件数、大小和扩展名。
- 检查 `descriptor.mod`。
- 检查 HJM/HIM 国家标签、国家文件、国家历史、角色、OOB。
- 检查 HJM/HIM 国策树和事件连接。
- 检查决议分类和战争倒计时任务。
- 检查简体中文本地化文件头和键数量。
- 检查核心 `.txt`、`.gfx`、`.gui`、`.mod`、`.yml` 文件花括号数量。
- 检查 `history/states` 文件名州 ID 重复。
- 扫描核心脚本中的 `TODO`、`FIXME`、`placeholder`、`missing` 等标记。

结论：

- 未发现花括号数量不匹配。
- 未发现州历史文件名 ID 重复。
- 未发现核心脚本中残留的 TODO/FIXME/placeholder 标记。
- HJM/HIM 国家标签和主要文件存在。
- HJM/HIM 国策触发的主线事件均有对应事件定义。
- HJM 战争倒计时决议链路存在。
- 简体中文本地化覆盖较完整。

限制：

- 当前环境没有可用的 `git` 命令，因此无法检查 Git 工作区状态或历史差异。
- 本次检查是静态文件检查，没有启动 HOI4，也没有读取游戏错误日志。

## 6. 主要问题与风险

### 高优先级：HJM_liberate_village 缺少前置国策

`common/national_focus/Hajimi.txt` 中 `HJM_liberate_village` 上方注释写明前置应为铁傀儡和红石大炮路线，但实际只写了：

```hoi4
available = {
    has_war_with = HIM
}
```

没有 `prerequisite`。这意味着只要 HJM 与 HIM 交战，玩家可能绕过 `HJM_iron_golem` 和 `HJM_redstone_cannon` 直接选择该国策。

建议：为 `HJM_liberate_village` 增加明确前置，例如 `HJM_iron_golem` 与 `HJM_redstone_cannon`。

### 高优先级：HIM 没有开局 OOB

`history/countries/HIM - Demons.txt` 没有 `oob = ...`，且 `history/units` 目录里只有 `HJM_1936.txt`。

影响：

- HIM 开局可能没有部队。
- HIM 虽然有国策奖励和战争目标，但 AI 前期威胁会偏弱。
- HJM 的防御和倒计时压力可能无法达到设计预期。

建议：新增 `history/units/HIM_1936.txt`，并在 HIM 国家历史中加入 `oob = "HIM_1936"`。

### 高优先级：铁傀儡装甲师装备供给不匹配

`HJM Iron Golem Armor` 模板需要轻型坦克、摩托化装备和支援装备等。  
但 `events/HJM.txt` 中 `HJM.15` 只添加：

```hoi4
add_equipment_to_stockpile = {
    type = infantry_equipment_1
    amount = 10000
    producer = HJM
}
```

随后创建 `HJM Iron Golem Armor`。如果库存里没有轻坦、摩托化和支援装备，该装甲师可能装备不足。

建议：事件同时添加 `light_tank_equipment`、`motorized_equipment`、`support_equipment`，或把铁傀儡模板调整为不依赖装甲装备的特殊步兵模板。

### 中优先级：大量国策图标仍使用占位 DDS

`interface/editor/HJM_focus_icons.gfx` 中大量 `GFX_focus_HJM_*` 指向 `F099F7AC57E87FA5D11604599A9E7846.dds`。  
`HJM_iron_golem` 甚至同时存在：

- `GFX_HJM_iron_golem`：指向专用 `HJM_iron_golem.dds`
- `GFX_focus_HJM_iron_golem`：指向占位 DDS

但国策实际使用的是 `GFX_focus_HJM_iron_golem`。

建议：把 `HJM_iron_golem` 国策图标改为 `GFX_HJM_iron_golem`，并逐步替换其他占位图标。

### 中优先级：禁用脚本容易造成误判

`_codex_disabled/common__on_actions__HJM_on_actions.txt.disabled` 定义了 `on_startup`，会在开局 1 天后给 HJM 触发 `HJM.1`。当前该文件位于 `_codex_disabled`，不会被 HOI4 加载。

这不一定是错误，因为 `MC_start` 国策也会触发 `HJM.1`。但如果设计目标是开局自动触发剧情事件，目前不会发生。

建议：明确设计选择。如果需要开局自动事件，恢复到 `common/on_actions/`；如果只允许国策触发，则保留禁用状态并写入 README。

### 中优先级：地图覆盖范围很大

项目包含 1081 个州历史文件和完整 `map/buildings.txt`。这类覆盖会显著提高与游戏版本和其他 Mod 的冲突概率。

建议：

- 标记哪些州文件是项目实际改动，哪些只是依赖地图数据。
- 发布前确认是否必须携带完整州历史覆盖。
- 用 HOI4 错误日志检查地图、建筑、战略区域和州历史是否有缺失引用。

### 低优先级：项目说明文档不足

当前项目有报告文件，但没有面向开发或发布的 README。

建议新增 README，至少记录：

- Mod 名称、版本、支持游戏版本。
- 国家标签和核心玩法链路。
- 主要事件 ID 和国策树文件。
- 测试步骤。
- 已知问题。

## 7. 优先级建议

建议优先处理：

1. 给 `HJM_liberate_village` 补上前置国策。
2. 给 HIM 增加开局 OOB 和初始部队。
3. 修正 `HJM.15` 铁傀儡装甲师装备奖励。
4. 替换 `HJM_iron_golem` 等明显已有专用资源的占位图标。
5. 明确 `_codex_disabled` 中脚本是否应恢复加载。

后续整理：

1. 梳理 1081 个州历史文件的来源和必要性。
2. 新增 README。
3. 增加 AI 策略和战争节奏控制。
4. 逐步补齐非占位国策图标和事件图片。

## 8. 推荐游戏内测试清单

建议在 HOI4 中按以下顺序测试：

1. 启动游戏并加载 Mod，确认无启动时报错。
2. 选择 HJM，检查国家名、国旗、领袖、政党、理念、国策树、决议分类是否正常显示。
3. 检查 HJM 开局 13 个师是否出现在正确位置。
4. 完成 `MC_start`，确认 `HJM.1` 触发。
5. 推进到 `HJM_brother_returns`，确认 13 号唱片战争倒计时任务出现。
6. 检查 `HJM_delay_record_13_war` 是否能延后倒计时 30 天。
7. 等待倒计时结束，确认 HJM 正确向 HIM 宣战。
8. 测试 `HJM_liberate_village` 是否能被过早选择。
9. 完成 `HJM_iron_golem`，检查生成的装甲师装备是否充足。
10. 观察 HIM AI 是否能正常推进国策并形成军事压力。
11. 检查 HOI4 `error.log`，重点看地图、国策图标、事件、本地化和 OOB 报错。

## 9. 总体评价

当前项目已经具备可运行 Mod 的主要结构：国家、国策、事件、决议、角色、理念、本地化和美术资源都已经成形。HJM 主线完成度较高，HIM 也具备敌对势力骨架。

主要短板不在内容缺失，而在玩法链路严谨性和测试收口：关键国策前置、HIM 开局兵力、事件奖励与师模板消耗、国策图标占位、地图覆盖兼容性都需要进一步处理。完成这些修复后，项目会更接近稳定可玩的版本。
