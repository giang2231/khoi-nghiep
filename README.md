# Startup Idea Analyzer

Trợ lý AI thẩm định ý tưởng khởi nghiệp (Streamlit + Google Gemini).

## Đưa website lên Internet (làm một lần)
1. **Lấy API Key Gemini** tại https://aistudio.google.com/apikey
2. **Tạo GitHub repo** (tài khoản github.com), tải toàn bộ thư mục này lên (nút *Add file > Upload files*). Giữ nguyên thư mục `fonts` và `.streamlit`.
   Không tải file `secrets.toml` thật lên.
3. Vào https://share.streamlit.io, đăng nhập bằng GitHub, chọn **Create app**, chọn repo vừa tạo, file chính là `app.py`.
4. Trong **Advanced settings > Secrets**, dán:
   ```
   GEMINI_API_KEY = "api-key-của-bạn"
   ```
5. Nhấn **Deploy**. Sau vài phút bạn nhận được đường link công khai để gửi cho mọi người.

## Kiểm soát chi phí
Mặc định: 3 lượt/phiên, 20 giây giữa hai lần, 100 lượt/ngày cho toàn website. Chỉnh bằng `SESSION_LIMIT` và `DAILY_LIMIT` trong Secrets.
Nên đặt hạn mức chi tiêu trong Google AI Studio / Cloud Billing.

## Chạy thử trên máy (tùy chọn)
```
pip install -r requirements.txt
mkdir -p .streamlit && cp .streamlit/secrets.toml.example .streamlit/secrets.toml   # rồi sửa API key
streamlit run app.py
```

## Kiểm thử trước khi công khai
- Thử ít nhất 5 loại ý tưởng khác nhau (kể cả ý tưởng yếu).
- Kiểm tra trên điện thoại và máy tính.
- Kiểm tra AI có ghi nhãn "giả định" cho số liệu không có nguồn.
- Kiểm tra giới hạn lượt dùng và nút tải PDF.
