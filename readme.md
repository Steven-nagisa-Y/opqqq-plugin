# opqqq-docker

### 基础环境
构建基础镜像 `Dockerfile` ：
```bash
    docker build --no-cache -t opqqq:base .
```

### 使用
挂载本地目录：
```bash
    docker run \
        -v /opqqq/OPQBot_3.0.8_linux_amd64:/opq \
        --name opqqq \
        -w /opq \
        -p 8888:8888 \
        -d opqqq:base \
        ./OPQBot
```

### 内存监控
```bash
    # 找到 pid
    ps aux | grep OPQBot
    # 监控
    top -d 2 -p <pid>
```

### 日志监控
```bash
    docker logs -tf opqqq --tail 20
```
