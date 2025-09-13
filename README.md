## 正文

这是一个完全免费的脚本，只需要你们自己配置好 openai 的 api 即可

## 操作步骤

1. 请首先配置好 openai 的 api（使用.env 文件或者在代码中配置）
2. 将 pdf 简历上传到文件夹 auto_job_find 里，命名为 **“my_cover.pdf"**
3. 将需要的包安装好
4. 执行 write_response.py

## 关于 asistant

会自动生成 openai 的 asistant，并在本地产生一个 .json 文件，只有第一次运行的时候才会产生，后面每次运行如果检测到这个 json ，就会调用已有的 asistant。

## 使用到的包

- `python-dotenv`
- `openai`
- `selenium`
- `robotframework`
- `robotframework-seleniumlibrary`
- `robotframework-pythonlibcore`
- `faiss-cpu不支持3.12（faiss-gpu不清楚）。建议大家用3.11及以下版本的python运行脚本。` from @[huanmit](https://github.com/huanmit)

## About RPA

tutorial video about how to learn [rpa](https://www.youtube.com/watch?v=65OPFmEgCbM&list=PLx4LEkEdFArgrdD_lvXe_hYBy8zM0Sp3b&index=1)

Plugin: Intellibot@Selenium Library

------------------下面是简单的教学视频---------------------

[B 站链接](https://www.bilibili.com/video/BV1UC4y1N78v/?share_source=copy_web&vd_source=b2608434484091fcc64d4eb85233122d)

[油管链接](https://youtu.be/TlnytEi2lD8?si=jfcDj2MZqBptziZc)

## 运行方式

先将该项目 clone 到本地，然后在项目根目录下执行

```bash
pip install -r requirements.txt
```

### assistant 方式运行

打开.env 文件，在里面配置好 OpenAI 的 API key
随后将 pdf 简历上传到文件夹 auto_job_find 里，命名为“my_cover".随后执行 write_response.py 即可
这种方式不支持使用自定义 api，优势是执行速度更快
如果需要使用自定义 api，请使用下面的方式运行

### langchain 方式

同样打开.env 文件，在里面配置好 OpenAI 的 API key 和你想要请求的 api 地址
随后将 pdf 简历放到文件夹 resume 里
最后执行 write_response.py 即可

### chatgpt4 及以上运行方式

如果尝试使用更新的 chatGPT 则不能保持最新版本为`v1.1.1`，同时如果报错信息为`An error occurred: Error code: 400 - {'error': {'message': "The requested model 'gpt-4o-mini' cannot be used with the Assistants API in v1. Follow the migration guide to upgrade to v2: https://platform.openai.com/docs/assistants/migration.", 'type': 'invalid_request_error', 'param': 'model', 'code': 'unsupported_model'}}`

1. 需要手动将 chatgpt 更新到最新版，

```shell
pip install --upgrade openai
```

2. 以及更改`create_assistant`中的结构体，详细参考[迁移模型](https://platform.openai.com/docs/assistants/migration)中的描述。建议直接在[平台](https://platform.openai.com/assistants/)上手动添加最新的 assist 然后复制代码到`assistant.json`中最为方便.

```json
{ "assistant_id": "asst_token" }
```

------------下面是其他朋友基于 js 构建的更加易于使用的代码---------------

我一直也在考虑如何可以降低各位的使用门槛，基于现在项目的热度，我发现很多朋友都需要这个东西来帮助自己，但是我相信对于更多的人而言，甚至 vpn 都是一个障碍

下面这位朋友基于 js 实现了一个更加简易的版本，虽然因为调用的免费 api，无法使用 assistant 进行 retrival，需要自己对简历进行简单的处理，但我依然认为这是个很棒的项目

感谢朋友的贡献，以下是链接：

[https://github.com/noBaldAaa](https://github.com/noBaldAaa/find-job)https://github.com/noBaldAaa/find-job

------------下面是其他朋友基于 azure 的 openai api 构建的版本的更加易于使用的代码---------------
https://github.com/LouisCaixuran/auto_job_find_azure
