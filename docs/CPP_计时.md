---
Title | CPP 计时
-- | --
Create Date | `2022-04-14T08:42:15Z`
Update Date | `2022-04-14T08:42:15Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/269)

---
## Reference

## Brief
- `system_clock`
- `steady_clock`
- `high_resolution_clock`
- `std::chrono::clock`


## UseCase

UseCase | Code
-- | --
system_clock | `auto tp = std::chrono::system_clock::now();`
steady_clock | `auto tp = std::chrono::steady_clock::now();`
high_resolution_clock | `auto tp = std::chrono::high_resolution_clock::now();`
