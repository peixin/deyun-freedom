Scientific Internet Access

Automatically check in on the "Airport"(机场) platform everyday, just for knowledge freedom is more cost-effective.

- update user.config set user username password
  - `cd _data && mv user.config.template user.config`
  - `vi user.config`

- You can use a scheduled task to run the script
  e.g.
  crontab
  `30 9 * * * /user-path/run.py`

- It is recommended to use cloud functions such as AWS Lamdba, Tencent Cloud SCF, Aliyun Function Compute etc.

### Use Tencent Cloud SCF
- Send check in result to personal Wechat use [「Server酱」，英文名「ServerChan」](http://sc.ftqq.com/3.version)
    - `cd _data && mv server-chan-key.template server-chan-key`
    - `vi server-chan-key`
    
- account or sub account grant permission: `QcloudSCFFullAccess`

- Create Function
    - `python deploy/create-qcloud-scf-func.py`
    - You can do it manually in the console 

- Create Function Trigger
    - `python deploy/create-qcloud-scf-trigger.py`
    - You can do it manually in the console
    
- Invoke Function
    - `python deploy/run-qcloud-scf.py`
    - You can do it manually in the console

---

- Deploy / Update Code to Tencent SCF (Serverless Cloud Function)
    - ~~manually create SCF in [Tencent Cloud Console](https://console.cloud.tencent.com/scf/index?rid=1)~~
    - ~~manually set user.config to SCF environment variable~~
    - `cd _data && mv qcloud.env.template qcloud.env`
    - `vi qcloud.env`
    - `python deploy/deploy-to-qcloud-scf.py`
