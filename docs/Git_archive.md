---
Title | Git archive
-- | --
Create Date | `2022-01-05T03:06:00Z`
Update Date | `2022-01-05T03:06:00Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/246)

---
## Reference
- [flann make release with `git archive`](https://github.com/junxnone/flann/blob/master/bin/make_release.sh#L6)

## Brief

```
git archive --prefix=flann-$VERSION-src/ -o flann-$VERSION-src.zip $VERSION-src
```
