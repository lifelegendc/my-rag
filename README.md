# MyRag - Cat Finder with Qdrant & LLM

本项目演示了如何结合向量数据库（Qdrant）、文本嵌入（Sentence Transformers）和本地大语言模型，实现“以自然语言查找猫咪”的智能检索。

## 主要功能
- 读取并处理猫咪信息数据集（cats_worldwide.csv）
- 使用 Sentence Transformers 对猫咪描述进行文本向量化
- 利用 Qdrant 向量数据库实现语义检索
- 通过本地 LLM（如 llava-v1.5-7b）生成自然语言回复，智能推荐猫咪

## 文件说明
- `findMycats.ipynb`：主流程 notebook，包含数据加载、向量化、检索和 LLM 调用
- `cats_worldwide.csv`：猫咪信息数据集
- `requirements.txt`：依赖包列表
- `pre-download.py`：用于预下载 Sentence Transformers 模型

## 快速开始
1. 安装依赖
   ```bash
   pip install -r requirements.txt
   ```
2. 运行 notebook
   - 推荐用 Jupyter Lab/Notebook 打开 `findMycats.ipynb`
   - 按顺序执行各代码块
3. 启动本地 LLM API 服务（如 llama.cpp/llava.cpp，需支持 OpenAI API 格式）
   - 并确保 `findMycats.ipynb` 里的 `base_url`、`model` 参数与实际服务一致

## 数据说明
`cats_worldwide.csv` 包含如下字段：
- name：猫咪名字
- region：地区
- breed：品种
- age：年龄
- notes：详细描述

## 依赖环境
- pandas >=2.3.1
- numpy >=2.0.2
- sentence-transformers >=5.0.0
- qdrant-client >=1.9.0
- openai >=1.11.1
- huggingface_hub >=0.33.2

## 致谢
- [Qdrant 向量数据库](https://qdrant.tech/)
- [Sentence Transformers](https://www.sbert.net/)
- [llama.cpp/llava.cpp](https://github.com/ggerganov/llama.cpp) 