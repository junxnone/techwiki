---
Title | Jupyter docker image
-- | --
Create Date | `2021-09-22T09:08:10Z`
Update Date | `2021-09-22T09:08:10Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/142)

---
# Reference
- [selecting docker images](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html)
- [jupyter/docker-stacks](https://github.com/jupyter/docker-stacks)

# Images
**N.B.**
因为 NVIDIA license 原因，官方docker image 不支持 GPU

- base-notebook
- minimal-notebook
- r-notebook
- scipy-notebook
- tensorflow-notebook
- datascience-notebook
- pyspark-notebook
- all-spark-notebook

![image](https://user-images.githubusercontent.com/2216970/64486768-09884980-d264-11e9-9331-fbf6c8b1184d.png)

# 定制适合项目的 docker
- [ ] pandas/numpy/matplotlib/sklearn/opencv
- [ ] clone the work repo
- [ ] mount the work folder
- [ ] tensorflow/keras
- [ ] gpu support

