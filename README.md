# MJ你快回来吧

抖音 / TikTok 的 LSPosed 模块。发送 `mj`，把当年那个蜘蛛侠彩蛋放回来。

| 蜘蛛侠吊着蛛丝出场 | 蜘蛛侠荡秋千送爱心 |
| :---: | :---: |
| <img src="https://raw.githubusercontent.com/sjtt2/MJComeBack/main/docs/img/drop.gif" alt="蜘蛛侠吊着蛛丝出场" width="200"> | <img src="https://raw.githubusercontent.com/sjtt2/MJComeBack/main/docs/img/swing.gif" alt="蜘蛛侠荡秋千送爱心" width="200"> |

## 功能

- 在抖音 / TikTok 的评论、私信、群聊、回复弹窗输入框**发送** `mj`，本地重放两段原版蜘蛛侠彩蛋动画（各约 3 秒，含原版音效）
- 两段动画（吊着蛛丝出场 / 荡秋千送爱心）可交替或随机播放
- 关键词判定贴合原版：整段必须是 `mj` 连写（`mj`、`mjmj`、`MJMJ`、`MjMj` 都算；`mj 好看` 不算）
- 设置页：总开关、音效开关、播放顺序、附加关键词（如 `蜘蛛侠,spiderman`）、两段动画预览，
  以及不需要安装抖音就能用的「试一试」
- 只在本地屏幕上播放：不修改消息内容、不拦截触摸、零权限、零联网

## 背景

2026 年 8 月，抖音上线过「蜘蛛侠联动彩蛋」：在私信、群聊、评论区输入框发送 `MJ` 会弹出动画。
9 月因刷屏被官方下线——服务端配置撤了，素材也不随安装包下发，所以靠「改配置」复活不了。
本模块把两段原版素材内置在 APK 里，在输入框层面嗅探关键词、本地重放。

## 安装与使用

1. 安装模块 APK；
2. 在 LSPosed 中启用「MJ你快回来吧」，作用域勾选**抖音**（TikTok 的两个包名已预置）；
3. 强制停止抖音后重新打开；
4. 在评论 / 私信输入框发送 `mj`。

## 兼容范围

| 项目 | 说明 |
| --- | --- |
| LSPosed API | libxposed Modern API 102 |
| 作用域 | `com.ss.android.ugc.aweme`、`com.ss.android.ugc.trill`、`com.zhiliaoapp.musically` |
| Android | 9（API 28）及以上（动画依赖系统 AnimatedImageDrawable） |
| 抖音 | 与具体版本无关，已在真机实测通过 |
| 模块版本 | 1.0.0（versionCode 1） |

## 说明与限制

- 动画只在你自己手机上播放，对方看不到（原版当年也是本地 CG，不随消息下发）。
- 「发送」是启发式判定（点击发送按钮 / 输入法发送键 + 输入框被清空）。如果某个抖音版本发送后
  **不清空**输入框，会静默不播放；遇到这种情况欢迎提 issue。
- 只覆盖原生 `EditText` 输入框及其子类；Lynx / Compose 自绘输入框不覆盖。
- 素材来自 [qiu7c/Tiktok-MJ-for-Wechat](https://github.com/qiu7c/Tiktok-MJ-for-Wechat)，
  动画与角色版权归原权利方，仅供个人学习与怀旧，请勿商用。

## 源码与反馈

- 源码：<https://github.com/sjtt2/MJComeBack>
- 问题反馈：<https://github.com/sjtt2/MJComeBack/issues>
- 排障日志：`adb logcat -s MJComeback MJAssets MJOverlay`
