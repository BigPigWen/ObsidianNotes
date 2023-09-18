## 串口
### 获取串口
	QstringList seriaNamePort;
	foreach(const QSerialPortInfo &info,QSerialPortInfo::availablePorts()){
	    serialNamePort<<info.portName();
	}