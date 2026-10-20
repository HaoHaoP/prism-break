# PRISM BREAK · 棱镜爆破

一款塞进单个 HTML 文件的霓虹打砖块 Roguelike。零构建、零依赖、零素材 —— 每一块砖、每一张卡、每一个音效都由代码生成。

**在线玩：<https://prism.haohaop.com>** · 界面默认中文，菜单里可一键切英文

![PRISM BREAK](assets/screenshot.png)

## 玩法核心：光色共鸣

大多数打砖块只要求你「接住球」。这里球带着一种**光色**（青 / 紫 / 金），每块砖也染着三种色之一。

**球色与砖色相同 → 伤害翻倍**，得分更高，超载槽充得更快。于是每一秒你都在做选择：追球，还是花半拍切个色去打对的那一列。

### 染光连锁

连着三次用**同一光色**命中，会引爆全场所有该色的砖 —— 一次能清掉整屏三分之一。切色、或打到异色砖，连锁就断。所以真正的技巧不是「追球」，而是**在球乱飞的情况下保持打对颜色**。

### 光痕

砖块碎掉后会在原地留下一团残留的光。球穿过光痕会持续加速，光痕也随之暗淡。所以「先打穿一条通道，再让球在通道里越跑越快」是可以主动经营的路子，而不是纯看运气。

### 时间倒带

球掉了不会立刻扣命：画面会停 1.5 秒等你决定。按 `R` 或点一下屏幕，球就回到 1.5 秒前的位置继续打。开局 2 次，每过五层恢复 1 次（上限 3）。所以失误是可以花掉的资源，而不是纯惩罚。

### 合光

场上有两颗以上球时按 `F`：所有球塌缩成一道竖直光束，从挡板一路扫上去，路径上的砖全部融化（冷却 12 秒）。代价是所有球都没了，只剩一颗重新发球 —— 多球既是火力也是安全网，用它来赌。

另外每层都混着特殊的砖：会**再生**的、被击中会**翻转你的光色**的、破了会**炸开邻居**的、永远不会碎的钢柱，还有会**整行左右漂移**的砖墙。

## 层规则

从第 2 层起，大半的层会随机带一条**层规则**（HUD 左上角标注），当场改变打法：

| 规则 | 效果 |
| --- | --- |
| 急流 | 球速 +15% |
| 静滞 | 球速 −12% |
| 致密 | 砖块 +1 血，得分 ×1.4 |
| 贪婪 | 得分 ×1.6，球速 +8% |
| 蜂群 | 砖块全 1 血，得分 ×1.2 |
| 暗场 | 隐藏砖块血条 |
| 下坠 | 球被持续向下牵引，得分 ×1.2 |
| 横风 | 侧风来回吹动球，得分 ×1.2 |
| 色轮 | 整场砖块每 5 秒换一次色，得分 ×1.3 |

| 按键 | 动作 |
| --- | --- |
| `Q` / `E` | 切换光色（也可点左下角色块） |
| `1` `2` `3` | 直接跳到某一种色 |
| `SHIFT` | 充满后释放**超载爆发** |
| `F` | 两颗以上球时释放**合光**扫射 |
| 鼠标 / 方向键 | 移动挡板（手机上是按住拖动） |
| 点击 / 空格 | 发球 |
| `P` | 暂停 · `M` 静音 · `L` 中英切换 |

## 超载

每破一块砖都给底部能量条充能。充满时按 `SHIFT` 释放棱镜爆发：全场砖块同时掉血，屏幕闪白，时间降到三分之一速度让你重新站位。一层密集砖块可以一键清空 —— 也可以留到金色核心棱镜。

## 结构

- **10 层**，每层图案不同、砖块血量递增，越深越有钢柱挡住你的舒适路线。
- **每 5 层**出现金色核心棱镜，外面套着三片护盾；护盾不破，核心免疫。它还会每隔几秒向下抛**干扰弹**，命中挡板会让挡板缩小 3 秒。
- **打完第 10 层**触发结局，之后可继续进入无尽模式。
- **31 张强化卡**，清层后三选一：多球、加宽、穿透、爆破、自动激光、暴击、护盾、缓冲、寻踪、分裂、共鸣增幅、电弧、吸血、专注、镜面……以及专门咬住新机制的六张：**染光**（连锁只需两次同色）、**光痕**（光痕加速翻倍）、**余烬**（合光后留一颗球）、**回响**（倒带 +2 次）、**锚定**（无视层规则的牵引力）、**血债**（每掉一命永久 +1 伤害）。还有几张**风险卡**（玻璃 / 狂战 / 易爆 / 血债），换来高伤害但付出代价。

一局 5～15 分钟。

## 成就与统计

标题界面会记住你的累计局数、破砖总数与成就进度。八个成就：击碎核心、连击 25、一击 12 块、下潜 15 层、千砖、时光倒流、染光大师、合光者。全部本地存档，不上传任何数据。

## 每日挑战

标题界面左下角的「每日挑战」按钮会用**当天日期做随机种子**——所有人都拿到同一套层规则和同样的三选一顺序。同一天内可以反复重试刷分，今日最佳会显示在按钮下方。

## 装到手机

用手机浏览器打开站点，菜单里可以「添加到主屏幕」—— 带 manifest 与图标，启动后是全屏横屏，没有地址栏。

手机上没有键盘也能完整玩：

- **挡板**：相对拖动，手指在屏幕任意位置滑动即可，不会挡住挡板
- **发射**：点画面任意处
- **换色 / 合光**：点左下角三个色块和「合光」槽
- **超载**：直接点底部那条能量条
- **暂停 / 静音**：右上角两个小按钮
- **多指**：一根手指拖挡板的同时，另一根手指可以点任何按钮，互不干扰

## 本地运行

```bash
git clone https://github.com/HaoHaoP/prism-break.git
cd prism-break
open index.html          # macOS
# 或 python3 -m http.server 8080
```

`index.html` 自包含，也可以只下载这一个文件双击打开。

---

# English

A neon brick-breaker roguelike in a single HTML file. No build step, no dependencies, no assets.

**Play: <https://prism.haohaop.com>** — Chinese UI by default, `L` or the menu button switches to English.

## The twist: light tones

The ball carries one of three light tones — cyan, violet, amber — and every brick is tinted with one of the same three. Hitting a matching brick deals **double damage**, scores more and charges your overdrive faster.

### Lit chain

Land three hits **in a row with the same light tone** and every brick of that tone on the floor detonates at once — often a third of the board. Switching tone or clipping an off-tone brick breaks the streak. The real skill is holding the right colour while the ball does whatever it wants.

### Light scars

Shattered bricks leave a fading glow behind. Fly the ball through one and it keeps picking up speed, burning the scar down as it does. Breaking a corridor open and then running the ball through it is now something you can deliberately build toward.

### Rewind

Dropping the ball no longer costs a life immediately — the game freezes for 1.5 seconds and waits. Press `R` or tap and the ball snaps back to where it was 1.5 seconds ago. Two charges per run, one more every fifth floor (max 3). Mistakes are a resource you can spend.

### Fusion

With two or more balls alive, press `F`: every ball collapses into a single vertical beam that sweeps up from the paddle and melts everything in its path (12s cooldown). You spend your whole board to do it and get one ball back — multi-ball is both your firepower and your safety net.

Floors also mix in **regenerating** bricks, **prism cores** that flip your tone on contact, **bombs** that chain to neighbours, indestructible steel struts, and rows that **drift sideways**.

## Floor modifiers

From floor 2 on, most floors carry a random rule (shown top-left): **CURRENT** (ball speed +15%), **STILL** (−12%), **DENSE** (+1 hp, score ×1.4), **GREED** (score ×1.6, speed +8%), **SWARM** (all bricks 1 hp, score ×1.2) **BLACKOUT** (brick health hidden), **DOWNDRAFT** (constant downward pull, score ×1.2) or **CROSSWIND** (the ball gets blown sideways, score ×1.2) or **COLOUR WHEEL** (every brick rotates its tone every 5s, breaking your chain, score ×1.3).

## Overdrive

Breaking bricks charges the meter. At full, `SHIFT` fires a prism burst: every brick takes a hit, the screen flashes, and time drops to a third speed so you can reposition.

## Structure

- 10 floors, each with a generated layout, growing brick health and drifting rows.
- Every 5th floor spawns a golden core prism guarded by three shield plates — the core is immune until they are gone, and it lobs **disruptor orbs** that shrink your paddle for three seconds.
- Clear floor 10 for the ending, then continue into endless mode.
- 31 upgrades, three at a time: extra balls, wider paddle, pierce, blast, auto-lasers, crits, shields, cushion, seeker, fork, resonance amp, arc, vampire, focus, mirror — plus six that lean on the new systems (CHAIN, SCAR, EMBER, RECALL, ANCHOR, BLOOD) and a few **risk** cards that trade safety for damage.

## Stats and achievements

The title screen tracks lifetime runs, bricks broken and eight achievements (clear the core, a 25 combo, a 12-brick burst, floor 15, a thousand bricks, a rewind save, a lit chain, a fusion). Everything stays in `localStorage` — nothing is uploaded.

## Daily run

The DAILY RUN button on the title screen seeds the RNG with today's date, so everyone gets the same floor modifiers and the same card offers. Retry as often as you like; today's best score is shown under the button.

## On a phone

Open the site on a mobile browser and add it to the home screen: the web app manifest plus icons give a full-screen landscape launch with no address bar. Everything is reachable by thumb:

- **Paddle**: relative dragging — slide anywhere on screen, your thumb never covers it
- **Launch**: tap anywhere
- **Tone / fusion**: tap the three swatches and the fusion slot, bottom-left
- **Overdrive**: tap the meter itself
- **Pause / mute**: two chips in the top-right
- **Multi-touch**: one finger steers while another taps buttons — they no longer interfere

## Controls

| Key | Action |
| --- | --- |
| `Q` / `E` | shift light tone |
| `1` `2` `3` | jump to a tone |
| `Shift` | spend a full overdrive meter |
| `F` | fuse every ball into one beam (needs 2+) |
| mouse / arrows | move paddle |
| click / space | launch ball |
| `P` pause · `M` mute · `L` language | |

## How it is built

- Plain JavaScript, `requestAnimationFrame`, no framework, no bundler.
- Canvas 2D at a fixed 960×640 logical resolution, letterboxed and DPR-aware.
- Swept sub-stepping for collision so a fast ball never tunnels through a thin brick, plus anti-stall logic that re-aims a ball grazing empty space.
- Sound is synthesised live with WebAudio oscillators — there are no audio files in this repo.
- Best score and deepest floor persist in `localStorage`; the UI language does too.

## License

MIT. Fork it, reskin it, ship it.
