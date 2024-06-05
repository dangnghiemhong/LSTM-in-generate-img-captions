# Tạo Caption cho Hình ảnh bằng Mô hình LSTM

## Giới thiệu
Dự án này sử dụng mô hình Long Short-Term Memory (LSTM) để tạo caption (mô tả văn bản) cho hình ảnh. Đây là một ứng dụng kết hợp giữa học máy và xử lý ngôn ngữ tự nhiên, giúp tạo ra các mô tả tự động cho hình ảnh, hỗ trợ người mù hoặc người già mắt kém và cải thiện khả năng tìm kiếm hình ảnh dựa trên mô tả văn bản.

## Ứng dụng
- **Hỗ trợ người mù hoặc người già mắt kém:** Giúp họ biết được nội dung của hình ảnh xung quanh thông qua mô tả bằng giọng nói. Quy trình: Hình ảnh -> Văn bản -> Giọng nói.
- **Cải thiện tìm kiếm hình ảnh:** Giúp các công cụ tìm kiếm như Google có thể tìm kiếm hình ảnh dựa trên caption.

## Dữ liệu
- Dataset: [Flickr8k](https://academictorrents.com/details/9dea07ba660a722ae1008c4c8afdd303b6f6e53b)
- Dữ liệu gồm 8000 ảnh, trong đó:
  - 6000 ảnh cho tập huấn luyện (training set)
  - 1000 ảnh cho tập kiểm tra (validation set)
  - 1000 ảnh cho tập kiểm thử (test set)
- Mỗi ảnh có 5 caption khác nhau, tạo ra 30000 mẫu huấn luyện.

## Mô hình học sâu sử dụng trong đề tài
- **LSTM**: Để xử lý và tạo chuỗi văn bản từ các đặc trưng hình ảnh.
- **InceptionV3**: Mô hình đã được huấn luyện trước để trích xuất đặc trưng từ hình ảnh.
- **GLOVE**: Mô hình được sử dụng để word embedding, chuyển đổi các từ thành các vector số, giúp cải thiện chất lượng của các caption được tạo ra.

## Thư viện và công cụ
- **Python**: Ngôn ngữ lập trình chính.
- **Thư viện Keras**: Để xây dựng và huấn luyện mô hình học sâu.
  - Các lớp sử dụng trong mô hình: LSTM, Embedding, Dense, Bidirectional, etc.
  - Tối ưu: Adam, RMSprop
  - `keras.preprocessing` sử dụng để xử lý ảnh và ngôn ngữ
- **Pandas, Numpy**: Xử lý và phân tích dữ liệu.
- **Matplotlib**: Vẽ đồ thị và hiển thị hình ảnh.
- **PIL (Python Imaging Library)**: Xử lý hình ảnh.
- **Glob, OS, re:** Thư viện Python tiêu chuẩn để xử lý tệp và hoạt động biểu thức chính quy.

## Cài đặt
1. **Cài đặt các thư viện cần thiết:**
    ```bash
    pip install numpy pandas matplotlib pillow keras tensorflow
    ```
2. **Tải dataset Flickr8k và giải nén vào thư mục dự án.**

## Hướng dẫn sử dụng
1. **Tiền xử lý dữ liệu:**
    - Đọc và xử lý dữ liệu hình ảnh và văn bản (caption).
    - Trích xuất đặc trưng từ hình ảnh bằng mô hình InceptionV3.
    - Chuẩn bị dữ liệu đầu vào cho mô hình LSTM.
2. **Huấn luyện mô hình:**
    - Sử dụng mô hình LSTM kết hợp với các đặc trưng hình ảnh và từ để huấn luyện mô hình sinh caption.
3. **Dự đoán caption:**
    - Sử dụng mô hình đã huấn luyện để tạo mô tả văn bản cho các hình ảnh mới.

## Liên hệ
Nếu có bất kỳ câu hỏi hoặc góp ý nào, vui lòng liên hệ qua email: dangnghiem200@gmail.com
