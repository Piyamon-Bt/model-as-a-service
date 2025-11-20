# model-as-a-service

## 1. สร้างและเปิด virtual env (ตัวอย่างบน macOS / Linux)

```bash
python3 -m venv .venv
source venv/bin/activate
```

## 2. ติดตั้ง dependencies
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

## 3. Build Docker image
```bash
docker build -t ds-ml-service .
```

## 4. Run container
```bash
docker run --rm -p 5001:5001 ds-ml-service
```

## 4. Run container
เปิดเบราว์เซอร์แล้วเข้า: http://localhost:5001