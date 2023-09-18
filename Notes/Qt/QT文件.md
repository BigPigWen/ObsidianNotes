### 应用的安装目录下

    QCoreApplication::applicationDirPath()

### 文档目录下

    QStandardPaths::writableLocation(QStandardPaths::DocumentsLocation)

### 文件拖放

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
