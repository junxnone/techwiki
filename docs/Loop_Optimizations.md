---
Title | Loop Optimizations
-- | --
Create Date | `2021-12-14T07:42:33Z`
Update Date | `2021-12-14T07:42:33Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/235)

---

## Brief


## Loop Unrolling

```
accum = 0;
#pragma unroll N
for (size_t i=0; i<4; i++) {
  accum += data[i];
}
sum_out = accum;
```

unroll/nounroll | Execution
-- | -- 
nounroll | ![image](https://user-images.githubusercontent.com/2216970/145953746-fad404d3-49e6-4edf-b2d3-d4814f1bb540.png)
Unroll 2 | ![image](https://user-images.githubusercontent.com/2216970/145953821-50eee22e-0f1b-4f5c-a08b-f8fa45d7ddcb.png)
Fully Unroll | ![image](https://user-images.githubusercontent.com/2216970/145954135-e01209eb-6b54-41b2-ad3f-cf9df07dc19e.png)


