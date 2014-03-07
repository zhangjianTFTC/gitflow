# 现阶段基于Git的代码管理流程

## 每天每个开发人员的工作流程

1. 获取develop分支最新代码 

	git checkout develop
	git pull origin develop

2. 创建本地分支
	
	git checkout -b today_branch develop

3. 在本地分支上进行开发
	
	add && commit

4. 一天开发结束，把本地分支合并到develop分支
	
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