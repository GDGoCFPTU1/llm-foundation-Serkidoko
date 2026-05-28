# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

1. Mở `starter-code/template.py` và hoàn thành các hàm:
   - `call_openai`
   - `call_gemini`
   - `compare_models`
   - `streaming_chatbot`

2. Đảm bảo bạn sử dụng đúng SDK và hướng dẫn trong README:
   - `from openai import OpenAI`
   - `client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))`
   - `client.chat.completions.create(...)`
   - `from google import genai`
   - `types.GenerateContentConfig(...)`

3. Chạy kiểm tra:
```bash
pytest tests/test_template.py -q
```

4. Nếu cần chạy thử thủ công, dùng:
```bash
python starter-code/template.py
```

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Khảo sát Temperature
Gọi `call_openai` với prompt:

```text
Hãy kể cho tôi một sự thật thú vị về Việt Nam.
```

và các giá trị sau:
- `temperature = 0.0`
- `temperature = 0.5`
- `temperature = 1.0`
- `temperature = 1.5`

**Ghi nhận:**
- Sự khác biệt về độ sáng tạo, độ dài câu trả lời, và mức độ lặp lại.
- Mô tả ngắn gọn 2–3 câu về kết quả bạn thấy.

---

### Bài tập 2.2 — Tính Chi Phí So Sánh
Sử dụng output token và input token từ `compare_models` để trả lời:

- GPT-4o có chi phí cao hơn bao nhiêu lần so với GPT-4o-mini nếu cùng số token đầu vào/ra?
- Trường hợp bạn nên chọn GPT-4o (chất lượng cao, độ chính xác, ngữ cảnh phức tạp).
- Trường hợp GPT-4o-mini là lựa chọn tốt hơn (chi phí thấp, phản hồi nhanh, nội dung đơn giản).

---

### Bài tập 2.3 — Thiết kế Chatbot Streaming
**Viết 1 đoạn ngắn mô tả:**
- Khi nào cần streaming (ví dụ: trợ lý chat trả lời từng câu, UX tức thì).
- Khi nào không cần streaming (ví dụ: batch generation, báo cáo tóm tắt, không cần latency thấp).

---

## Danh Sách Kiểm Tra Nộp Bài
- [ ] Mọi hàm trong `starter-code/template.py` đã được triển khai
- [ ] `pytest tests/test_template.py -q` chạy thành công
- [ ] `call_openai` hoạt động đúng với `OPENAI_API_KEY`
- [ ] `call_gemini` hoạt động đúng với `GEMINI_API_KEY`
- [ ] `compare_models` trả về đầy đủ các trường `response`, `latency`, `cost`, `input_tokens`, `output_tokens`
- [ ] `streaming_chatbot` có chế độ truy xuất lịch sử 3 lượt
- [ ] `retry_with_backoff` hoạt động với hàm thất bại tạm thời
- [ ] `batch_compare` trả về danh sách kết quả và mỗi item có `prompt`
- [ ] `format_comparison_table` có thể xuất Markdown rõ ràng
- [ ] Đã lưu file `excercises.md` và cập nhật thông tin nộp bài
- [ ] Sao chép bài làm vào thư mục `solution` và đặt tên theo yêu cầu
 