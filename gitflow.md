# 现阶段基于Git的开发流程（不断修订中）

## 分支说明
develop 分支：最新的开发分支，所有开发人员的本地分支最终要合并到的分支

## 每天每个开发人员的工作流程

1.获取develop分支最新代码

    git checkout develop
	git pull origin develop

2.创建本地分支
	
	git checkout -b today_branch develop

3.在本地分支上进行开发
	
	add && commit

4.一天开发结束，把本地分支合并到develop分支
	
	# 获取最新develop
	git checkout develop
	git pull origin develop
	# 本地合并
	git merge today_branch
	# 解决出现的冲突,提交代码
	add && commit 
	# 推送develop到服务器
	git push origin develop

	# 删除本地分支
	git branch -D today_branch

## 版本发布流程

1.切换到最新develop分支

    git checkout develop
    git pull origin develop

2.打上tag，如v1.0

    git tag -a v1.0 -m 'my version 1.0'
    # 如果tag打错了
    # 删除本地tag
    git tag -d v1.0
    # 删除远程tag
    git push origin --delete tag v1.0


3.把tag信息推送到远端服务器

    git push origin v1.0
    # 或者
    # 一次推送所有本地新增的标签
    git push origin --tags
