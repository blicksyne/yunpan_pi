==全量同步逻辑
* 获取远程(yunpan) 文件目录树并排序
* 获取本地(local) 文件目录树并排序
* 目录树比较
    * 远程存在，本地不存在的目录或文件
    * 本地存在，远程不存在的目录或文件
    * 本地和远程都存在的文件列表
        * 按最后修改时间，文件大小，md5判断
        * 选择下载或上传动作
* 写同步任务执行方案文件 (SyncJob)
    * 按方案顺序执行
    * 纪录执行的进度日志文件
    * Commit 日志文件
    * 生成冲突纪录

==增量同步逻辑
* 获得一个文件变化事件
    * 新增
    * 删除
    * 更新
* 累计5分钟的变化事件，生成SyncJob
    * 提交SyncJob执行

ABOUT
=====
A command line based cloud disk client designed for Raspberry Pi, implemented in Go. It should also work on other platforms.
