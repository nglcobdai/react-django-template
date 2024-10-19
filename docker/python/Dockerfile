FROM ubuntu:22.04

# 環境変数の設定
ENV LANG=C.UTF-8 \
    LANGUAGE=en_US \
    PYTHONPATH="/backend:$PYTHONPATH" \
    DEBIAN_FRONTEND=noninteractive \
    TZ=Asia/Tokyo

# Python のインストール
RUN apt-get update && apt-get install -y python3.10 python3-pip \
    && ln -s /usr/bin/python3.10 /usr/bin/python \
    && rm -rf /var/lib/apt/lists/*

# Python の標準出力のバッファリングを無効化
ENV PYTHONUNBUFFERED 1

# システム依存のライブラリをインストール
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx \
    && rm -rf /var/lib/apt/lists/*

# 作業ディレクトリを作成して設定
WORKDIR /backend

# Poetryのインストールと依存関係のインストール
RUN pip install --no-cache-dir --upgrade pip \
    && pip install --upgrade poetry

COPY docker/python/pyproject.toml docker/python/poetry.lock docker/python/poetry.toml $WORKDIR/

# キャッシュをクリアしてディスク領域を解放
RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Poetryを使用して依存関係をインストール
RUN poetry install --no-root
