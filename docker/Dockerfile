# 使用官方Python镜像作为基础镜像
FROM python:3.9-slim

# 设置工作目录
WORKDIR /app

# 安装系统依赖
RUN apt-get update && apt-get install -y \
    gcc \
    libmariadb-dev \
    pkg-config \
    netcat-openbsd \
    && rm -rf /var/lib/apt/lists/*




# 仅复制requirements.txt文件到容器中
COPY requirements.txt .

# 安装Python依赖
RUN pip install --no-cache-dir --upgrade pip \
    && pip install --no-cache-dir -r requirements.txt

# 复制应用程序代码到容器中
COPY . /app

# 暴露FastAPI运行的端口
EXPOSE 8000

# 运行应用程序
CMD ["python", "web_demo.py"]
