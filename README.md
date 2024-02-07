# Sign
签到啦

(目前支持京东京豆、南航、川航、携程、微信支付有优惠小程序龙舟游戏刷免费提现券、美团优惠券、统一快乐星球、中国移动、中国联通、东鹏特饮、云闪付、卡亨星球、鸿星尔克、迪卡侬、萤石)

```bash
pip install uvicorn fastapi websockets httpx loguru diskcache apscheduler SQLAlchemy python-dateutil -i https://pypi.tuna.tsinghua.edu.cn/simple
```

运行项目（两种方式运行: 第一种直接运行脚本;第二种启动服务后通过接口添加token设置定时任务）

第一种：直接运行脚本

```bash
python sign.py
```

追加参数

```bash
python sign.py --pt_pin jd_XXX --pt_key AAJXXX
```

第二种：启动服务(服务可用于添加token和设置定时任务)

```bash
uvicorn sign:app --host 0.0.0.0 --port 8081
```

打开 http://127.0.0.1:8081/docs

通过接口添加账户token等

apschedule调度运行(默认早上九点签到),也可使用crontab运行

crontab运行脚本后面添加参数即可(例如 `0 9 * * * ~/python3 ~/sign.py --pt_pin jd_XXX --pt_key AAJXXX`)

后续增加其它平台...
