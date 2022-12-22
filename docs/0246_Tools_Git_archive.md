---
Title | Tools Git archive
-- | --
Created @ | `2022-01-05T03:06:00Z`
Last Modify @| `2022-12-22T06:49:10Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/246)

---
## Reference
- [flann make release with `git archive`](https://github.com/junxnone/flann/blob/master/bin/make_release.sh#L6)

## Brief

```
git archive --prefix=flann-$VERSION-src/ -o flann-$VERSION-src.zip $VERSION-src
```
