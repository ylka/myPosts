# 使用 vscode markdown 遇到的问题

## 0x1 问题1

Markdown 预览文字设置为 'Courier New'，markdown.preview.fontFamily = 'Courier New'。预览的内容字体有变，但是 code 部分的字体不变，看起来是 Consolas。  

### 解决方法

预览区默认样式使用的是目录
>D:\Program Files\Microsoft VS Code\resources\app\extensions\markdown-language-features\media

默认有两个css文件：highlight.css，markdown.css，我的是黑色主题，用的是 markdown.css，找到 code 的样式：

```css
code {
    font-family: "Courier New", Menlo, Monaco,Consolas, "Droid Sans Mono",  monospace, "Droid Sans Fallback";
    font-size: 1em;
    line-height: 1.357em;
}
```

将字体 'Courier New' 提前，问题解决。
