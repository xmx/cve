## 简介

- CVE-2023-4357-Chrome-XXE
- Chrome XXE 漏洞 POC
- 实现对访客者本地文件读取

## 影响版本

- Chrome 版本 < 116.0.5845.96
- Chromium 版本 < 116.0.5845.96
- Electron 版本 < 26.1.0

## 复现截图

| 访问者环境 | 截图 |
| -- | -- |
| Linux | <img src="/assets/poc-l.png" width="660"></img> |
| Windows | <img src="/assets/poc-w.png" width="660"></img> |

## 复现1

1. 访问者环境：

```
Linux
```

2. 下载并运行 Chrome

```
wget https://edgedl.me.gvt1.com/edgedl/chrome/chrome-for-testing/114.0.5735.90/linux64/chrome-linux64.zip
unzip chrome-linux64.zip
./chrome-linux64/chrome --no-sandbox
```

3. 启动 Web 服务

```
wget https://codeload.github.com/xcanwin/CVE-2023-4357-Chrome-XXE/zip/refs/heads/main -O CVE-2023-4357-Chrome-XXE.zip
unzip CVE-2023-4357-Chrome-XXE.zip
python3 -m http.server 8888 -d CVE-2023-4357-Chrome-XXE-main
```

4. 浏览器访问

```
http://127.0.0.1:8888/c.html
```

## 复现2

1. 访问者环境：

```
Windows
```

2. 下载并运行 Chrome

```
https://edgedl.me.gvt1.com/edgedl/chrome/chrome-for-testing/114.0.5735.90/win64/chrome-win64.zip

./chrome-win64/chrome --no-sandbox
```

3. 启动 Web 服务

```
https://codeload.github.com/xcanwin/CVE-2023-4357-Chrome-XXE/zip/refs/heads/main

python3 -m http.server 8888 -d CVE-2023-4357-Chrome-XXE-main
```

4. 浏览器访问

```
http://127.0.0.1:8888/c.html
```