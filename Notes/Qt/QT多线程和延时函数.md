### 延时函数

    void delay(int millisecond)
    {
        QEventLoop loop;
        QTimer::singleShot(millisecond, &loop, SLOT(quit()));
        loop.exec();
    }

### 继承QObject的多线程

    //创建线程的实例
    QThread *thr = new QThread;
    //实现类
    filethread = new fileThread;
    //将类移动到线程中
    filethread->moveToThread(thr);
    //线程启动
    thr->start();