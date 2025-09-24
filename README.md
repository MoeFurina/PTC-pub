# 这里是哪里

这里是[PhiTogheter](https://github.com/moefurina/phitogether)的谱面仓库，用于储存谱面文件

点击[此处](https://github.com/moefurina/ptc-pub)前往PTC的GitHub仓库

# 提交谱面

在一切的之前，您需要PhiEditor或Re:PhiEdit创建的PEC格式谱面或官方的JSON格式谱面，没有就别说了（请注意，我们不提供PhiEditor和Re:PhiEdit的副本）

请注意：导出合适的PEC谱面后，需要前往[lchzh3473的模拟器](https://lchzh3473.github.io/sim-phi)测试是否能正常播放，再进行提交。

并且在提交前确保您已经获得曲师、谱师和曲绘画师的授权。

首先`Fork`这个仓库到你的账号，这一步需要一个GitHub账号。如果您没有，只需注册一个，然后 Fork。

首先创建一个具有正确名称的新文件夹，例如 `rrhar` 或 `rrharil` 指的是 `Rrhar'il`。（不要包含特殊字符，如 `' / \ ` 等，不能以`.`开头）

我们建议的文件夹名称格式是`谱师.曲名`，例如`baibiao.senbonzakura`。

在其中创建或粘贴以下文件
```
meta.json          必须-元数据     (名称不可变更)
base.mp3           必选-音乐       (名称可变更)
chart.json         必须-铺面       (名称可变更)
line.json          可选-判定线贴图  (名称可变更)
bga.mp4        	   可选-背景动画   (名称可变更)
illustration.jpg   必须-曲绘       (名称可变更)
```
> 音乐要求：MP3/OGG/WAV等常见格式(能正常兼容各个浏览器的AudioContext即可)，大小小于5MB，建议小于2.5MB(建议调整采样率为44100kHz，调整比特率108~128Kbps，声道双通道)

> 曲绘要求：JPG/PNG等常见格式(WebP没测试过)，大小小于0.5MB

> 背景动画要求：MP4/WebM等常见格式，大小小于25MB，建议小于10MB，去除声音通道。

在`meta.json`内填入歌曲元信息（见下），注意要删除注释，使用英文字符，且双引号需要添加`\`转译，不填的值直接删除该行或填写`null`。
```javascript
{
    "id": "r100000002",                                                // 必须-歌曲ID(唯一且不可更改，开头为r100000XXX，建议使用随机字符串)
    "charts": [
        {
            "id": "r100000002",                                        // 必须-谱面ID(唯一且不可更改，开头为r100000XXX，建议使用随机字符串)
            "song": "r100000002",                                      // 必须-歌曲ID(与上方id相同)
            "charter": "WHC",                                          // 必须-谱师
            "chart": "https://ptc.focalors.ltd/song/r100000002/1.pec", // 必须-铺面文件URL(内容为https://ptc.focalors.ltd/song/歌曲ID/谱面文件名.pec)
            "level": "IN",                                             // 必须-难度等级(可选值：EZ, HD, IN, AT)
            "difficulty": "15",                                        // 必须-难度数值(1~20之间的整数或浮点数)
            "ranked": false,                                           // 必须-是否Ranked(布尔值true或false)
            "notes": "0"                                               // 必须-音符数
         }
     ],
    "composer": "WHC",                                                 // 必须-曲师
    "illustrator": "Mechari",                                          // 必须-曲绘
    "name": "Inverted World",                                          // 必须-曲名   
    "song": "https://ptc.focalors.ltd/song/r100000002/song.mp3",       // 必须-音乐文件URL(内容为https://ptc.focalors.ltd/song/歌曲ID/音乐文件名.mp3)
    "edition": "PTF社区自建",                                           // 必须-版本(例如：PTF社区自建、PhiTogether、PhiEditor等)
    "illustration": "https://ptc.focalors.ltd/song/r100000002/cover.jpg",// 必须-曲绘文件URL(内容为https://ptc.focalors.ltd/song/歌曲ID/曲绘文件名.jpg)
    "bpm": 170,                                                        // 必须-BPM
    "duration": "00:02:13",                                            // 必须-时长(格式为00:00:00)
    "preview_start": "00:00:00"                                         // 必须-预览起始时间(格式为00:00:00)
}
```

完成后，将谱面文件夹（您之前创建的）上传到 *你的Git仓库*（您之前复刻的那个），然后打开一个新的 `Pull Request` 然后等待合并。

如果您觉得此操作实在无法理解，您可以提出[Issue](https://github.com/moefurina/ptc-pub/issues)，让我代为添加。

# 请最好一次Commit搞定(真的不想Git仓库体积爆炸)

# 搞错了什么的话就删掉仓库重新Fork一个
