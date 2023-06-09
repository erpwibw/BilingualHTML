# BilingualHTML
用 Python 和 ChatGPT API 实现的 HTML 网页翻译工具，可以将本地 HTML 网页批量翻译成中文双语对照。

A HTML webpage translation tool implemented with Python and ChatGPT API, which can translate local HTML webpages in batch into bilingual versions in Chinese and English.

---
## 🌟用 chatGPT API 制作双语网页或电子书


参考 [Minja](https://twitter.com/Minja_Rin) 的[将外文电子书翻译成双语对照版本，并在任何设备上阅读](https://utgd.net/article/10001) 和 Github 上的 ChatGPT [bilingual_book_maker
](https://github.com/yihong0618/bilingual_book_maker) 项目，我实现了通过 Python 使用 chatGPT API 来制作双语网页/电子书。


### 💡主要功能：
- 本地 HTML 文件批量制作为简体中文的双语对照格式（图1）
![image](https://user-images.githubusercontent.com/23517447/225020527-96fca4b7-5545-41c0-ac41-7adcd663fa9b.png)

- 尽量保留原有的 HTML 格式（图2）

![image](https://user-images.githubusercontent.com/23517447/225020585-9f030fab-685a-45e9-ad74-090f9c943d3e.png)

- 中断后可以继续翻译（图3）

![image](https://user-images.githubusercontent.com/23517447/225020640-07391e45-3e5c-43af-b408-f66cba86194d.png)

- 显示翻译进度、花费时间和预计时间（图4）

![image](https://user-images.githubusercontent.com/23517447/225020706-60c53a3e-e05b-43a7-a74d-a2aeb5bde4f5.png)

结合 [Minja](https://twitter.com/Minja_Rin) 介绍的保存网页、拆 epub 电子书、在 Kindle 阅读网页等（见 [UNTAG 网站](https://utgd.net)），我们阅读的脚步再一次向前迈进🚀

### 🤔做这个脚本的原因是：
- 双语电子书项目功能太复杂了
- 市面上还没有 chatGPT 翻译网页
- 参考 Minja 的方案网页/电子书翻译兼得
- 学习使用 ChatGPT API


### ⬇️使用流程：
使用这个脚本需要电脑上可以运行 Python 脚本，并安装 BeautifulSoup 包，剩下的交给 ChatGPT。

- 保存我编写的 Python 脚本到任意目录，例如 test
- 在这个 test 目录下，创建 2 个文本文件
  - `api_key.txt` 里面保存你的 api_key（只输入 api_key 的内容即可）
  - `chatGPT_prompt.txt`里面保存你的 prompt（可以在我的基础上根据自己的需要微调）
- 创建一个名为 `translatable` 的文件夹，将要翻译的 HTML 文件放进去（可以包含子文件夹，在子文件夹中放 HTML 文件，用来区分不同的项目一起制作）
- 运行 Python 脚本，即可开始翻译并制作双语对照 HTML
  - 翻译结果会暂存在 `test/translated.json`。单个 HTML 文件翻译完成后，会创建一个 HTML文件名_cn.html 文件并将翻译结果一起写入。
  - 翻译进度会暂存在 `test/index.json`，用来记录翻译到哪一个文件。
  - 翻译时所有输出保存在 `test/log.txt` 文件中，作为调试的参考
  - 翻译中断时再次运行脚本即可。
  - 翻译结束后暂存文件都会删除（`log.txt`除外，不需要的话需手动删除）。


### 🤖**这是我使用的 prompt：**
>Translate the HTML webpage into simplified Chinese, and return the translated HTML code. Translate in the style of Python programming books. Do not translate the text wrapped in `<code>` tags. If the text cannot be translated, return the original text as is. Do not add any additional text to the translation. Do not translate person's name. The HTML webpage to be translated is:

### 待补充内容：
- [ ] token 的使用情况
- [ ] 时间花费情况
- [ ] 工作原理

