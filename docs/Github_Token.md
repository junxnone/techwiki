---
Title | Github Token
-- | --
Create Date | `2021-09-22T09:10:53Z`
Update Date | `2021-09-22T09:10:53Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/145)

---
# Brief
- Generate the github token for ssh access

## Steps
- **1 Generate the key**

```
ssh-keygen
cat .ssh/id_rsa.pub
```

- **2 copy the publickey to the github**


![image](https://user-images.githubusercontent.com/2216970/49859317-36711280-fe32-11e8-8168-2d00e0d8ea96.png)
![image](https://user-images.githubusercontent.com/2216970/49859332-3f61e400-fe32-11e8-9d3c-8718e55534e5.png)

`
ssh-rsa xxxxxxxxxxxxxxxxxxxxxABAQC4OI93xICB3nyCM57MGXu1t/ZVBrvqsaZCrEokOOHzWHbd3UdEmALRkrm9U0srP8VBVdYcv6RSE0tYSntuN+tT6BJmzOMRMPbDnXJyHniDsFtzQcbrZd6RPKXXsk4Bhnjxtx2dNBdJkOXoWIGH2sK0Nbt5Z2jqF8DPF8AWIkuK66YOtazkPCLzddTl8EWMinLH/Zr55Pw940MTPIswDu3sYzQJBFZ2z+85t3jwFH/O2ZmrZmqtEKHu0IDeakUDZxxxxxxxxxxxxxxxxxxxxxxxx name@hostname`
