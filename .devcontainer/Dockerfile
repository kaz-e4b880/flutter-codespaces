# ベースイメージとして公式のDebianスリムイメージを使用
FROM debian:bullseye-slim

# 必要なツールをインストール
RUN apt-get update && apt-get install -y \
    curl \
    git \
    unzip \
    xz-utils \
    zip \
    libglu1-mesa && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Flutterのインストール
RUN git clone https://github.com/flutter/flutter.git -b stable /usr/local/flutter

# Flutterのパスを設定
ENV PATH="/usr/local/flutter/bin:/usr/local/flutter/bin/cache/dart-sdk/bin:${PATH}"

# flutter doctorを実行して初期セットアップを行う
RUN flutter doctor

# ワークディレクトリを設定
WORKDIR /workspace

# デフォルトのコマンドを設定（必要に応じて変更可能）
CMD ["bash"]
