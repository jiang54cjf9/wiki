# Python

## 启动 Python 项目

安装依赖

```
pip install <依赖名> <依赖名>
```

```
python main.py
```

如果系统里同时安装了多个版本的 Python，可以用：

```
python310 main.py
```

## 使用低版本虚拟环境

```
# 首先安装旧版 Python（推荐 3.10 或 3.11）
# 比如下载：https://www.python.org/downloads/release/python-3119/
# 然后创建虚拟环境
python3.10 -m venv eegenv
eegenv\Scripts\activate

pip install numpy scipy matplotlib mne pywavelets torch
python inference.py
```

## 启动 WEB 服务

### Flask

1.安装

```
pip install flask
```

2.编写接口

```py
from flask import Flask, request, jsonify

app = Flask(__name__)

# 定义一个简单接口
@app.route('/hello', methods=['GET'])
def hello():
    return jsonify({'message': 'Hello from Python!'})

# 带参数的接口
@app.route('/add', methods=['POST'])
def add():
    data = request.get_json()
    a = data.get('a', 0)
    b = data.get('b', 0)
    return jsonify({'result': a + b})

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

3.运行服务

```
python app.py
```

### 跨域

1.安装 Flask-CORS

```
pip install flask-cors
```

2.在代码中添加

```py
from flask_cors import CORS
CORS(app)
```

### FastAPI

> FastAPI 比 Flask 快、类型提示友好，还能自动生成接口文档。

1.安装

```
pip install fastapi uvicorn
```

2.示例

```py
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class AddRequest(BaseModel):
    a: int
    b: int

@app.get("/hello")
def hello():
    return {"message": "Hello from FastAPI"}

@app.post("/add")
def add(req: AddRequest):
    return {"result": req.a + req.b}

# 启动服务：uvicorn app:app --reload
```

3.API文档

API 文档自动生成在：http://127.0.0.1:8000/docs
