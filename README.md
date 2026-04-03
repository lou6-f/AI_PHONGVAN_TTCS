# IT InterviewPrep AI: Ứng Dụng Luyện Lập Phỏng Vấn IT Bằng Giọng Nói

Đây là dự án ứng dụng web mô phỏng môi trường phỏng vấn dành cho sinh viên và lập trình viên IT. Ứng dụng tích hợp **Google Gemini AI** đóng vai trò như một người phỏng vấn ảo, giao tiếp trực tiếp qua giọng nói (SST/TTS).

## Tính năng nổi bật
- **Phỏng vấn trực tiếp bằng Voice Chat:** Lắng nghe và trò chuyện mượt mà.
- **Tuỳ chọn linh hoạt:** Hỗ trợ nhiều vai trò (Frontend, Backend, DevOps, Data Science...) và độ khó (Intern -> Senior).
- **Đánh giá AI chi tiết:** Chấm điểm dựa trên mức độ hiểu biết chuyên môn, tính liên kết của câu trả lời, nhận diện độ "căng thẳng" hoặc ngắt ngữ của người trả lời để đưa ra nhận xét xây dựng.
- **Lịch sử học tập:** Lưu lại toàn bộ điểm số, nhận xét và dòng thời gian phỏng vấn trong bộ nhớ thiết bị.
- **Kho tài nguyên:** Tổng hợp các links học thuật chuẩn từ những nguồn uy tín nhất như MDN, Oracle, Document chính thức.
- **Giao diện hiện đại:** Hỗ trợ Light/Dark Mode xịn xò.

## Công nghệ sử dụng
- **Cốt lõi:** React (khởi tạo qua Vite) + Javascript.
- **Styling:** Vanilla CSS (CSS3 System Variables, Flexbox/Grid).
- **AI Model:** Google Gemini 1.5 Flash (Xử lý siêu nhanh).
- **APIs:**
  - `@google/generative-ai`
  - Web Speech API (native browser STT/TTS).

---

## 🚀 Hướng Dẫn Cài Đặt & Khởi Chạy Code

### 1. Yêu cầu hệ thống
- Máy tính đã cài **Node.js** (phiên bản >= 18).
- Trình duyệt **Google Chrome** hoặc **Microsoft Edge** (rất quan trọng, để hỗ trợ Web Speech API nhận diện giọng nói chuẩn nhất).

### 2. Cấu hình ban đầu
1. Mở Terminal / Command Prompt và đi tới thư mục chứa code:
   ```bash
   cd src/it-interview-ai
   ```
2. Cài đặt các gói thư viện cần thiết:
   ```bash
   npm install
   ```

### 3. Cấu hình API Key (Bắt buột)
Dự án sử dụng Google Gemini nên bạn cần nạp key của mình vào hệ thống.
1. Khởi tạo một file `.env` ở **thư mục gốc của project** (ngang hàng với `package.json`).
2. Mở file `.env` và nhập nội dung sau:
   ```env
   VITE_GEMINI_API_KEY=điền_api_key_của_bạn_vào_đây
   ```
   *(Lưu ý: Không dùng dấu ngoặc kép bọc key).*

3. File này sẽ không bị đẩy lên host nếu bạn deploy vì đã được cấu hình ẩn trong `.gitignore` chuẩn.

### 4. Chạy dự án
Chạy server local để xem dự án:
```bash
npm run dev
```
Trình duyệt sẽ cung cấp link (thường là `http://localhost:5173/`). Nhấn vào và trải nghiệm!

## 💡 Hướng dẫn Deploy lên mạng
Tất cả code đã được cấu hình Vite tiêu chuẩn. Khi banj muốn đẩy lên nền tảng như **Vercel** hay **Netlify**:
1. Commit code lên Github.
2. Link repo Github vào Vercel/Netlify.
3. Ở trang cấu hình của Vercel/Netlify, nhớ thiết lập **Environment Variables** cho biến môi trường:
   - Key: `VITE_GEMINI_API_KEY`
   - Value: `<apikey của bạn>`
4. Nhấn Deploy.

Dữ liệu lịch sử người dùng chỉ được lưu trên LocalStorage thuộc trình duyệt cá nhân của họ, do vậy hoàn toàn riêng tư và không cần bảo trì database.
