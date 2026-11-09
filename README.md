# Artifact Sweep · 数字去伪影

**面向 AI 音乐和数字音频的修复插件。** 用来减轻生成、音源分离和数字处理后出现的毛刺、沙粒感和发刺的高频，尽量保留鼓点、人声细节和乐器尾音。

Artifact Sweep is an audio restoration plug-in in development for AI-generated and digitally processed music. It targets brittle highs, grain and fizz left by generation or source separation.

## 它怎么处理

插件把声音拆成短时频谱，估计各频段需要衰减多少，再把处理后的频谱合成回音频。可以按频段调整处理重点，并控制强度、启动与释放速度，让衰减跟着声音变化。

开发版有三种观察方式。衰减图看处理量，折线频谱对照原声、处理后和被移除的成分，彩色声谱图看这些变化出现在什么时间和频率。还可以用「旁路」对比，或用「只听噪音」单独听被移除的成分。

## 在宿主里怎么用

将插件加到需要修复的音轨，循环播放问题最明显的一段。逐步增加处理强度，再打开「只听噪音」。如果被移除的成分里出现明显的人声、鼓点或乐器细节，就调低强度，或提高对应的保护。当前开发目标是 Apple Silicon Mac，支持 VST3 和 AU。

## 发布状态 · Early preview

这个仓库目前是项目预告。首个公开版本将使用独立开发的模型。模型和宿主验证完成后，会在这里发布源码、构建说明和版本记录。

This repository is an early project preview. Source code and build instructions will follow after the independently developed model and host validation are ready.
