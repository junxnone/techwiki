---
Title | Loop Optimizations
-- | --
Create Date | `2021-12-14T07:42:33Z`
Update Date | `2021-12-15T03:30:39Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/235)

---
## Reference
- [HLS Loop Optimizations](https://learning.intel.com/developer/learn/course/external/view/elearning/242/hls-loop-optimizations-part-3-of-7)

## Brief
- Loop Pipelining
- Loop Unrolling


## Loop Pipelining


![image](https://user-images.githubusercontent.com/2216970/146112942-ece86f96-caec-4da2-9aa9-941399a8eae0.png)
-- | 
![image](https://user-images.githubusercontent.com/2216970/146112374-5301c59a-18fa-4005-852f-0db370354697.png)



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

Basic Loop | Unrolled Loop
-- | --
![image](https://user-images.githubusercontent.com/2216970/146117988-a24d301e-9f05-4508-8bde-815f66e1c9cf.png) | ![image](https://user-images.githubusercontent.com/2216970/146118021-038c8534-461f-4348-b819-6d85d247fea4.png)

