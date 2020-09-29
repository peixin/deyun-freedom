Scientific Internet Access

Automatically check in on the deyun platform everyday, just for knowledge freedom is more cost-effective.

- update user.config set user username password
  - `cd _data && mv user.config.template user.config`
  - `vi user.config`

- You can use a scheduled task to run the script
  e.g.
  crontab
  `30 9 * * * /user-path/run.py`

- It is recommended to use cloud functions such as AWS Lamdba, Tencent Cloud SCF, Aliyun Function Compute etc.

- Deploy to Tencent SCF (Serverless Cloud Function)
    - create SCF in [Tencent Cloud Console](https://console.cloud.tencent.com/scf/index?rid=1)
    - `cd _data && mv qcloud.env.template qcloud.env`
    - `vi qcloud.env`
    - `python deploy/deploy-to-qcloud-scf.py`
    - set user.config to SCF environment variable 

- Send check in result to personal Wechat use [「Server酱」，英文名「ServerChan」](http://sc.ftqq.com/3.version)
    - `cd _data && mv server-chan-key.template server-chan-key`
    - `vi server-chan-key`
    - set SERVER_CHAN_KEY to SCF environment variable