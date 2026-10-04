# 三分钟比赛 Demo 录制流程

适用于正式版 v1.0.0。推荐录制英文界面，终端宽度约 85–90 列。全程使用
下方的合成案例、合成名字和示例留言；不要录入朋友的真实偏好、菜单、日记或
健康信息。目标时长 **2 分 50 秒**，最长不要超过 3 分钟。

操作指示使用中文。由于比赛文章是英文，建议旁白使用英文；每段下方给出可
直接照读的英文台词。录制中可以按提示逐条输入，不要一次粘贴全部按键。

## 录制前准备

1. 解压 v1.0.0 正式版，或进入项目文件夹，在该文件夹打开终端。
2. 确认终端当前目录是解压后的项目文件夹。把这条**完整命令**复制进终端并
   按回车。它会创建临时目录、启动合成 Demo；完成并退出后，会自动打开刚刚
   导出的 HTML 卡片：

   ```sh
   export DEMO_DIR="$(mktemp -d /tmp/plate-memory-demo.XXXXXX)" && python3 plate-memory.py --demo --language en --profile "$DEMO_DIR/friend.json" && open "$DEMO_DIR"/postcards/postcard-*.html
   ```

   录制期间，按下一节的顺序逐项输入。完成后在 app 里按 `0`，浏览器就会自动
   打开导出的明信片。

3. 终端宽度设为 85–90 列，打开终端装饰和颜色，关闭无关窗口、通知和其他
   隐私内容。临时目录只用于本次录制；合成资料留在内存里，只有最后主动导出
   的明信片会写入这个临时目录。
4. 先不录影，完整走一遍按键流程，确认屏幕字号和滚动速度合适。guard 部分
   使用仓库内的 canned fixture，要如实称为“预设合成案例”，不能说成现场
   调用了模型。

## 按时间录制

| 时间 | 终端操作与镜头 | 英文旁白参考 |
|---|---|---|
| 0:00–0:17 | 停在欢迎画面和四个主入口。让两只饭碗和留座的装饰完整显示。 | “We ate together every day in high school. Now we’re at different universities. Plate Memory is a small way to save each other a seat.” |
| 0:17–0:55 | 按 `6` 打开更多选项，输入 `demo`，再输入 `weekend`。报告出现后，慢慢滚动到 Saturday 日期、`WEEKDAY_OUT_OF_SCOPE` 和 `HIGH_RISK_HUMAN_REVIEW_REQUIRED`。 | “Same memory, new context. The weekday note doesn’t carry into Saturday. The allergy note still asks a person to check with the preparer. The Python guard makes that call. This screen uses the clearly labeled canned weekend fixture; it does not call the model.” |
| 0:55–1:25 | 回到饭桌后按 `1` 找东西吃，按 `2` 选食堂，输入 `something warm`，再按 `1` 打开一条建议。停在 **Food family**、**On the menu** 和相近选择提示。 | “When all you know is that you want something warm, offline food references offer a few directions. They don’t claim a shop has it, or guess ingredients, price or nutrition.” |
| 1:25–1:48 | 按 `4` 看相近选择，按 `1` 打开其中一条，再按 `1` 选它。停在“没有下单或记录为已吃”的说明和食堂下一步。 | “The related choices help you keep browsing. Choosing one is just a plan: check the cafeteria board before you walk over.” |
| 1:48–2:34 | 回饭桌后按 `4` 写下次吃饭的留言。名字依次输入 `Synthetic Jesse`、`Synthetic Bro`，留言输入 `Different campuses. Still my lunch buddy. See you at the table soon. 🥣`。确认加入食物，选 `1 Export`、`1 Share folder`，确认加入项目链接。在保存路径处直接回车，采用临时目录的默认路径。停在预览、**Saved locally. Nothing was sent.** 和文件列表。 | “The card is a little note from one friend to another. The meal is identified as an idea for next time. The export makes a real HTML card, text copy and importable lunchbox file, with a checksum manifest. I choose whether to include the public quick-start link; nothing sends automatically.” |
| 2:34–2:50 | 按 `0` 退出。启动命令会自动打开导出的明信片；让离线卡片填满画面。 | “The drawing is fictional; the words are mine. The HTML carries its artwork with it and opens offline. That’s Plate Memory: practical food ideas, careful memory decisions, and a place for your friend at the table.” |

启动命令最后的 `open` 会在浏览器打开刚才导出的独立 HTML 明信片。它本地自带插画，无需联网。

## 终端里逐项输入什么

先粘贴上面的启动命令。应用启动后，不要一次粘贴下面所有答案；请等当前屏幕
出现对应提示，再输入本步骤的内容：

1. 饭桌主菜单 `Choose` → 输入 `6`（更多选项）。
2. 更多选项 `Choose an option` → 输入 `demo`。
3. `Scenario: weekday / weekend / stale / allergy` → 输入 `weekend`。等报告完成；
   滚动展示 Saturday、`WEEKDAY_OUT_OF_SCOPE` 和
   `HIGH_RISK_HUMAN_REVIEW_REQUIRED`，然后回到饭桌。
4. 饭桌主菜单 `Choose` → 输入 `1`（找吃的）。
5. 今天怎么样 `1 / 2` → 输入 `2`（去食堂）。
6. `Anything you’re craving?` → 输入 `something warm`。
7. 食物列表 `Number / food keyword` → 输入 `1`。
8. 食物详情 `1 Pick / 2 Check ingredients / 3 Source / 4 Similar ideas` → 输入 `4`。
9. 相近食物列表 → 输入 `1`。
10. 食物详情 → 输入 `1`，确认选这个想法。看完“没有下单或记录为已吃”后回到饭桌。
11. 饭桌主菜单 `Choose` → 输入 `4`（下次再一起吃）。
12. `Your name or nickname` → 输入 `Synthetic Jesse`。
13. `Your friend’s name or nickname` → 输入 `Synthetic Bro`。
14. `A little message for your friend` → 输入 `Different campuses. Still my lunch buddy. See you at the table soon. 🥣`。
15. `Include this food idea ... yes / no` → 输入 `yes`。
16. 明信片预览 `1 Export / 2 Edit note / 3 Style` → 输入 `1`。
17. 导出格式 `1 Share folder ...` → 输入 `1`。
18. `Include the link to try Plate Memory? yes / no` → 输入 `yes`。
19. `Save path` → **直接按回车**，使用新建临时目录中的默认位置。
20. 等终端显示 `Saved locally. Nothing was sent.` 和导出的文件路径。饭桌主菜单
    再输入 `0` 退出；启动命令会接着自动打开刚才的 `.html` 明信片。

录制时间预算见上方时间表。滚动如果占时过多，可以缩短停留；过敏人工核对
这段要让观众看清楚。合成案例报告和正式模型推理的区别也要说清楚。

## 录制时的准确表述

- guard 报告会标出 `canned-demo`。请称它为仓库里的合成预设案例。正式菜单
  审核流程可用本地开源模型 Gemma 提取候选食物短语；模型不能决定记忆权限、
  适用范围、风险或 guard 最终裁决。不要把这个预设画面说成刚刚现场推理。
- 食物建议来自带来源的离线名称目录和有限的分类浏览。实际餐馆是否供应、
  价格、分量、配料和营养资料都未知。
- 明信片和分享文件夹会真正导出。插画人物是虚构形象，并不代表 Jesse 或
  Harold。示例留言是演示文案，不要说成朋友真实说过的话。
- 这段视频展示的是可用的本地 v1.0.0，不是朋友的实际试用。不要编造 Harold
  的使用感想或个人偏好。
- [v1.0.0 正式版发布页](https://github.com/Jesse-Zeng423/that-bro-who-ate-with-you-everyday-back-in-highschool/releases/tag/v1.0.0)
