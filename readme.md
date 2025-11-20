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

## 5. การใช้งานผ่าน Web UI
เปิดเบราว์เซอร์แล้วเข้า: http://localhost:5001

## 6. การทดสอบ api
### ผ่าน postman 
ใช้ METHOD: POST http://localhost:5001/predict
ตัวอย่างข้อมูลที่ใช้ในการส่ง
```bash
{
  "features":[8.3,25.0,6.0,1.0,1200,3.0,34.2,-118.3]
}
```
ผลลัพธ์
```bash
{
    "prediction": 4.038992599999997
}
```

### ผ่าน terminal
ใช้ curl ใน bash/zsh เนื่องจาก macos ไม่มี PowerShell
```bash
curl -X POST "http://127.0.0.1:5001/predict" \
  -H "Content-Type: application/json" \
  -d '{"features":[8.3,25.0,6.0,1.0,1200,3.0,34.2,-118.3]}'
```
