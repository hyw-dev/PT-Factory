<h1 align="center">PT-Factory</h1>
一个可以自动获得PTGen信息，精简版MediaInfo，重编码前后对比截图并自动上传图床，生成发布所需BBode的PT快速发种工具


## Features
* 可生成重编码前后对比截图，单个视频截图
* 可配置socks5代理来进行网络请求
* 生成精简的Mediainfo
* 动漫自动匹配bangumi生成信息

## 快速开始
#### 在 [Github Release](https://github.com/Tohrusky/PT-Factory/releases) 下载即可快速使用，命令行参数及配置文件同下
```shell
./ptf -e "/home/Toaru Kagaku no Railgun T - 01 [BDRip 2160p HEVC-Main10 FLAC].mkv"
```

## 准备
Prerequisites for [PT-Factory](https://github.com/Tohrusky/PT-Factory)

**Linux玩家** 可能需要

```bash
apt install libmediainfo-dev
apt install libgl1-mesa-glx
```
**Python > 3.6**
```
git clone https://github.com/Tohrusky/PT-Factory
pip install -r requirements.txt
```
* （可选）配置 [FFmpeg-GPL](https://github.com/BtbN/FFmpeg-Builds/releases)

## Run
 ```shell
 python PT-Factory -e "/home/Toaru Kagaku no Railgun T - 01 [BDRip 2160p HEVC-Main10 FLAC].mkv"
 ```
 
## 效果
![pt-factory-sample _2_.png](https://s2.loli.net/2022/08/29/mBCIih9NEFyYzPg.png)

## 配置

### 支持的图床

- [x] 0 - [SM.MS](https://sm.ms)
- [x] 1 - [ImgURL](https://www.imgurl.org)

使用前请先在./config.yaml填写配置文件
```shell
usage: PT-Factory [-h] [-u URL] [-e ENCODE] [-s SOURCE]

如果不需要对比图，仅填写-e或-s参数即可 || 对于二次元番剧电影，可尝试不指定-u参数直接搜索

optional arguments:
  -h, --help            show this help message and exit
  -u URL, --URL URL     豆瓣，bangumi，IMDB的详细URL
  -e ENCODE, --ENCODE ENCODE
                        Encode资源路径
  -s SOURCE, --SOURCE SOURCE
                        Source资源路径
# 注意，特殊字符时添加引号
```
*完成后会复制发布所需BBcode到你的剪贴板，生成的内容，日志，种子在./下的文件夹*
### config.yaml
```shell
proxy-settings:                                
  # socks5 proxy, 使用前请先配置好socks5代理, 使用时会检测其是否有效，未生效时等同false
pt-gen: 
  # 内置的pt-gen服务器，可替换为自行搭建的，填写API和地址即可
pic-hosting-settings:
  # 图床编号，图床地址和API
mediainfo-settings:                           
  # 选择的 mediainfo 格式编号，默认为 0(精简)
torrent-settings:
  # 是否生成种子，以及种子信息
upload-settings:
  # 是否使用FFmpeg来快速截图，使用前请先自行配置环境变量
  # 发布的截图数量，和发布人的一些信息
upload-logo:
  # 使用额外的logo
```
## 测试环境
* Windows 11
* Windows 10
* Debian 9 X86
* Debian 10 X86
* Ubuntu 20.04 LTS X86
* Ubuntu 20.04 LTS ARM
* MacOS Big Sur X86
* MacOS Monterey X86
* MacOS Ventura X86
* MacOS Monterey ARM
* MacOS Ventura ARM

## ToDo

- [ ] 更多的图床支持
- [ ] 更多的 Mediainfo 格式

## Reference

### [pt-gen](https://github.com/Rhilip/pt-gen-cfworker)
### [SRVFI-Raws](https://srvfi.top)
