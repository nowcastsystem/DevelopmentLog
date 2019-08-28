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
