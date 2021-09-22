---
Title | Download google drive files without browser
-- | --
Create Date | `2021-09-22T02:47:45Z`
Update Date | `2021-09-22T02:47:45Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/81)

---
# Reference
- [command alias](https://gist.github.com/iamtekeste/3cdfd0366ebfd2c0d805#gistcomment-2359248)
- [gdrivedl](https://github.com/matthuisman/gdrivedl)


# Brief
## gdrivedl

```
python3 gdrivedl.py the_share_url
```

## shell commands
- 添加如下 function 到 ~/.bashrc
- 重新打开一个终端
- 执行 `gdrive_download <file_id> <save_name>`

```
function gdrive_download () {
  CONFIRM=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate "https://docs.google.com/uc?export=download&id=$1" -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')
  wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$CONFIRM&id=$1" -O $2
  rm -rf /tmp/cookies.txt
}
```
