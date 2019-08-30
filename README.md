# DevelopmentLog


## git

### git delete branches

git branch -d branchname

git branch -D branchname

git push origin --delete branchname

### pip

pip freeze > requirements.txt
pip install -r requirements.txt

### python package install

python setup.py install --force

### QA System
####Task and engine
import QUANTAXIS as QA




# 创建一个类,继承QA_Worker


class job(QA.QA_Worker):
    def __init__(self):
        super().__init__()

    def run(self, event):
        if event.event_type is 'selfdesign':
            print(vars(event))
            if event.callback:
                event.callback(event.message)
        else:
            print('unknown/unsupport event type')


jobx = job()  # 实例化这个类

# 创建一个event
event = QA.QA_Event(event_type='selfdesign', message='ssss', callback=print)

# 创建一个标准task
task = QA.QA_Task(event=event, worker=jobx, engine='backtest')

# task有result方法
print(task.result)

thread = QA.QA_Thread()  # 创建一个QA_Thread
thread.start()  # 开启thread 线程
thread.put(task)  # 向thread线程推送任务

engine = QA.QA_Engine()  # 创建一个QA_Engine
engine.start()  # engine 开启
engine.create_kernel('backtest')  # engine创建一个叫 backtest的线程
engine.start_kernel('backtest')  # engine 启动该线程
engine.run_job(task)  # 向engine推送任务


####Mongodb
已找到使用远程MongoDB的入口，更改 ~/.quantaxis/setting/config.ini 里的 uri 即可。
添加Mongodb权限,修改QASetting和QACmd即可.
https://zhuanlan.zhihu.com/p/36001584 mongo查询优化

停牌 https://github.com/QUANTAXIS/QUANTAXIS/issues/1248

实盘 https://github.com/QUANTAXIS/QUANTAXIS/issues/967
https://github.com/QUANTAXIS/QUANTAXIS/issues/1188
https://github.com/QUANTAXIS/QUANTAXIS/issues/72

UI https://github.com/QUANTAXIS/QUANTAXIS/issues/370

### Docker compose. Restart from pulled images

docker-compose stop
docker-compose rm -f
docker-compose pull
docker-compose up -d

### Github

 git commit -a -m 'message'

### generator
gen.__next__()


## Linux System
### check and kill process on certain ports
sudo lsof -i tcp:portnum
sudo kill -9 $portnum
