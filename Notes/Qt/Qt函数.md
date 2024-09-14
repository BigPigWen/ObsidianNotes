# 串口
## 获取串口
``` C++
QstringList seriaNamePort;
foreach(const QSerialPortInfo &info,QSerialPortInfo::availablePorts()){
	serialNamePort<<info.portName();
}
```
# 多线程
## 继承QObject的多线程
```C++
//创建线程的实例
    QThread *thr = new QThread;
    //实现类
    filethread = new fileThread;
    //将类移动到线程中
    filethread->moveToThread(thr);
    //线程启动
    thr->start();
```
## 延时函数
```C++
void delay(int millisecond)
{
	QEventLoop loop;
	QTimer::singleShot(millisecond, &loop, SLOT(quit()));
	loop.exec();
}
```
# 文件
## 应用的安装目录下
`QCoreApplication::applicationDirPath()`
## 文档目录下
`QStandardPaths::writableLocation(QStandardPaths::DocumentsLocation)`
## 文件拖放
```C++
void dragEnterEvent(QDragEnterEvent *event)
{
	if (event->mimeData()->hasFormat("text/uri-list"))
    {
        event->acceptProposedAction();
    }
}

void dropEvent(QDropEvent *event)
{
    QList<QUrl> urls = event->mimeData()->urls();
    if(urls.isEmpty())
    {
        return;
    }
    //文件路径
    urls.at(0).toLocalFile();
}

```
# 判断暗色
``` C++
bool paletteIsDark(const QPalette &pal) {
    return pal.color(QPalette::Window).lightnessF() < pal.color(QPalette::WindowText).lightnessF();
}
if (paletteIsDark(QApplication::palette())) {
    qDebug()<<"true";
} else {
    qDebug()<<"false";
}
```


