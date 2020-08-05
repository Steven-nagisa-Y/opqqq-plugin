# iotqq-docker

### 基础环境
构建基础镜像 `Dockerfile` ：
```bash
    docker build --no-cache -t iotqq:base .
```

### 使用
挂载本地目录：
```bash
    docker run \
        -v /iotqq/iotbot_3.0.6_linux_amd64:/iot \
        --name iotqq \
        -w /iot \
        -p 8888:8888 \
        -d iotqq:base \
        ./iotbot
```

### 内存监控
```bash
    # 找到 pid
    ps aux | grep iotbot
    # 监控
    top -d 2 -p <pid>
```

### 日志监控
```bash
    docker logs -tf iotqq --tail 20
```
