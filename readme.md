# 简介
这是针对粉笔错题回顾的谷歌浏览器插件。默认隐藏答案，点击选项展示答案

# JSON数据
首页暂时未发现JSON请求方式

# 思路
在已经进入错题页面的情况下，点击插件按钮，插件自动收集从首页到最后一页的所有题目信息，然后调整相应格式，形成可以转换为pdf的页面，并提供pdf下载按钮。
错题页面[示例](https://www.fenbi.com/spa/tiku/exam/error/practice/xingce/xingce/20995/2?total=74&order=desc&timeRange=0)

## 重点功能
1.可以设置单个图片的大小（针对辅助图片、选项图片）
2.可以针对某个元素进行删除（侧重针对有选项图片的选项，删除多余内容）

## 详细内容
content.js文件获取当前页面信息；
popup.js主控。
1.popup页面点击生成按钮；
2.popup向content获取页面信息；
3.popup向content发出定位第一页的指令，content执行；并触发计时器（2s）
4.计时器触发，判断是否加载完成，完成则发出读取页面指令，并触发随机计时器（定位下一个页面的计时器8s内）
5.当读取完所有页面之后，覆盖当前页面，重新布局

## todo
1.通过js生成pdf方式（参考jspdf+html2canvas方式），将页面生成pdf（因为粉笔页面限制打印）

