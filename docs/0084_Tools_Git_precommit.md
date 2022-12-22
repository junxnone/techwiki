---
Title | Tools Git precommit
-- | --
Created @ | `2019-11-14T02:36:49Z`
Last Modify @| `2022-12-22T06:48:56Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/84)

---
## Reference
- [git commit前检测husky与pre-commit](https://www.jianshu.com/p/f0d31f92bfab)
- [Pre-commit and post-deploy code reviews are dead](https://about.gitlab.com/blog/2019/01/31/pre-commit-post-deploy-is-dead/)
- [Github - pre-commit](https://github.com/pre-commit)
- [Pre-commit is awesome](https://blog.jerrycodes.com/pre-commit-is-awesome/)
- [Custom server-side Git hooks](https://github.com/gitlabhq/gitlabhq/blob/master/doc/administration/custom_hooks.md)

## Brief

- pre-commit 更倾向于commit 之前自我审查。
- push之后 merge时还是需要review
- 因为security 原因不会默认作为新clone的repo的hooks

**优点**
- 优化 CI 之前的自检查
- formatting check
- build test


