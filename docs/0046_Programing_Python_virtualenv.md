---
Title | Programing Python virtualenv
-- | --
Created @ | `2018-11-25T09:53:47Z`
Last Modify @| `2022-12-22T08:07:56Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/46)

---

# Brief
- 用于创建独立的 python 虚拟环境, 隔离 host python 环境
- 一般使用 [[virtualenvwrapper]] 管理虚拟环境

# Install

Install from | cmd
-- | --
Raspberry pi 3B & Ubuntu | `sudo apt install -y virtualenv`
pip | `pip3 install virtualenv`

# UseCase

Usecase | cmd
-- | --
Create New virtualenv | `virtualenv yourenv` <br>`source yourenv/bin/activate`
Create New python3 env | `virtualenv -p python3 env`
Exit virtualenv | `deactivate`

