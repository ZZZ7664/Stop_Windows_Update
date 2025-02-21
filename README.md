# WIN10系统彻底永久关闭自动更新
## 一、首先我们需要做的就是禁用Windows Update服务
  1、通过键盘Win + R健，弹出运行对话框，输入命令 services.msc ，按“确定”按钮，即可打开服务弹窗。
  ![image](https://github.com/user-attachments/assets/2c94b2d7-3adc-4155-9c31-e166f24ded1f) 
  
  2、往下拉，寻找到找到Windows Update，双击打开。
![image](https://github.com/user-attachments/assets/55bf6823-9dfd-4cea-bfe2-0ac2fbc7c036)

  3、双击打开弹框，点击“停止”，将启动类型选为“禁用”，最后点击确定。
  ![image](https://github.com/user-attachments/assets/c46b9304-6303-400d-b8ce-90dbd2f027bd)
  
  4、然后切换到“恢复”选项，将第一次失败、第二次失败、后续失败全部修改为“无操作”，点击“应用”“确定”。
  ![image](https://github.com/user-attachments/assets/a22388f7-2037-4991-810e-27d487aba466)

## 二、通过组策略进行Win10自动更新相关服务关闭
  1、按Win + R 组合键，调出运行命令操作弹框，输入“gpedit.msc”，点击确定。
  ![image](https://github.com/user-attachments/assets/39cf3063-bf5f-4db5-ba27-b979ca63eff0)

 2、本地组策略编辑器左侧菜单栏，依次选择：计算机配置 -> 管理模板 -> Windows组件 -> Windows更新。
  ![image](https://github.com/user-attachments/assets/fd89a502-28f4-4c6b-9ad0-3b4b95b2e084)

 3、双击右侧“配置自动更新”，弹出框中设置为“已禁用”，点击“应用”并“确定”。
![image](https://github.com/user-attachments/assets/e701ac09-85e7-4cbc-8ae0-031c5307f971)

 4、接着再找到“删除使用所有Windows更新功能的访问权限”，双击弹出框，设置已启用，然后“确定”。
![image](https://github.com/user-attachments/assets/c30c8e1e-749d-49fc-a56a-a9cc6866c397)

## 三、禁止任务计划中的Win10自动更新服务
1、按 Win + R键，调出运行弹框，输入“taskschd.msc”，并“确定”。
![image](https://github.com/user-attachments/assets/2d6342dc-c42f-4965-a5a8-52d0cd14207d)

2、任务计划程序弹框中，依次选择：任务计划程序库 -> Microsoft -> Windows -> WindowsUpdate，将其展示出来的项目均设置为 [ 禁用 ]。
![image](https://github.com/user-attachments/assets/9e85918b-3288-429b-b04c-d399b25d730b)

## 四、通过注册表关闭Win10自动更新功能
1、按Win + R 组合键，在弹出的运行框中输入：regedit，确定。

![image](https://github.com/user-attachments/assets/b81e559f-d8d5-4339-b621-3f4f9196f99d)

2、在注册表编辑器中找到：HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\UsoSvc。然后在右侧找到“Start”键。
![image](https://github.com/user-attachments/assets/456db3b3-6639-4d8c-b5b9-3974371f0873)

3、双击start，在弹出框中把基数改成：16进制，数值数据改为“4”，点击确定。
![image](https://github.com/user-attachments/assets/9f5dd6a2-c938-4613-b2fc-15f7520a218b)

 4、右侧找到“FailureActions”，双击弹出框中，把“0010”、“0018”行的左起第5个数值由原来的“01”改为“00”， “确定”。这样我们就可以彻底把win10自动更新永久关闭。
 
![image](https://github.com/user-attachments/assets/ec8c4712-12e2-4b06-80d3-2182fa620393)





























  
