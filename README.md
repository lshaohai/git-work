## Git 的使用
```powershell
    # 1-拉取远程代码 一般 是 master
    $ git clone  url      
    
    # 2-将本地仓库跟远程仓库关联， 具体意思就是 `设置一个上传的管道流` 
    $ git push --set-upstream origin master   

    # 3-安装相关依赖模块
    $ cnpm  i 
    
    
    # 查看 READEME.md文档，这个是项目介绍  -- 熟悉项目，有一个大概的了解

    # 4-启动项目，具体查看 package.json文件的 scripts 写的内容。 
    $ npm run dev / $ npm  run start

    # 5-如果有测试分支stage（名字可能是其他的），拉取远程测试分支代码 并映射到本地的git 仓库 名字为stage，就是第二个stage。
    $ git fetch origin stage:stage    
    $ git push --set-upstream origin stage   

    # 6-在stage分支的基础上创建一个 本地分支，
    # 所有开发的代码的这个地方去写， 写完代码之后 继续往下 
    $ git checkout -b  分支名    

    # 7-将本地修改提交到缓存区， 中间的“/”是或者的意思
    $ git add filename / $ git add  .   

    # 8-将缓存区的代码，提交到本地仓库
    $ git commit -m  “备注内容”    

    # 9-切换到 测试分支
    $ git checkout stage   

    # 10-拉取远程分支最新的代码 到本地分支， 如有冲突，解决冲突
    $ git pull  /  git pull origin stage   

    # 11-切换到  你开发的分支名
    $ git checkout   本地开发的分支名   


    # 12-合并 stage 分支 到 开发分支，如有冲突 解决冲突
    $ git merge stage 

    # 13-切换分支
    $ git checkout stage  

    # 14-合并分支
    $ git merge 本地开发的分支
    
    # 15-拉取最新的代码， 一定要保证是最新的代码，
    # 如果不是最新的代码 重复 11，12， 13， 14 步骤
    $ git pull   

    # 16-如果是最新的 执行$  git push ,将本地分支提交到 远程的 git 仓库 
    # 17-如果你有权限，还有可能会让你 构建项目，发布项目，线上环境 测试、调试。
    # 具体流程具体分析

    > 以上是测试分支的 git 的使用流程，
    > 一般都是master 上的分支都是经过测试环境测试过后没问题了，
    > 才会提交push到master分支
    > 所以
    > stage 构建，测试没问题了 继续往下 

    # 18-切换到master分支，前提：保证stage 是最新的代码，并且是没有问题的代码
    $ git checkout master  

    # 19-拉取远程的 master分支的代码，并且合并到本地分支。如有冲突，解决冲突。
    # 这里有两个步骤的。暂时就这么用把，具体的自行百度
    $ git pull  

    # 20-合并stage 测试分支的代码到 master分支，如果有冲突解决冲突。
    # 本地测试，效果是否正常
    $ git merge stage  


    # 21-将本地的master分支推送到 远程的master分支
    $ git push  

    # 22-项目正式上线 。

    # 这个是我的 git 使用流程。可能会跟你做的项目 不一致。
    # 当然使用的过程有可能会遇到问题，
    # 比如：比如把同事的代码覆盖了，怎么办？ 这就是需要 版本回退 等操作。
    # 为什么会有冲突？怎么解决？ 
    # 当两个，或多个开发人员同时修改一个地方的时候，
    # 或者你本地的分支比较久远，
    # 别人对它自己的代码 重复修改了，然后你本地的代码跟远程的不一致，就会出现冲突。

    # 解决冲突的方法：
        # 1. 放弃本地 仓库 ，拉取远程最新的代码，
        # 把刚刚开发的内容，复制到最新的仓库中去。（冲突比较多的时候，使用这种）

        # 2. 把冲突的代码改成最新的代码，
        # 具体我是到 “码云” 上面去 查看日志，
        #然后把最新的代码复制 到本地。（如果冲突的地方比较少的时候，使用这个） 
    # 以 $  开头表示这个命令 是在 命令行中执行。
    # cms 或者 powershell 或者 git 命令行 中 
```