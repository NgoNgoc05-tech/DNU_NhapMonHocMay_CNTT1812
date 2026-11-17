# DNU_NhapMonHocMay_CNTT1812
Bài tập lớn Nhập môn Học máy – Đề tài 6: Chẩn đoán viêm phổi qua ảnh X-quang

Open In Colab

Thông tin
Sinh viên: Ngô Văn Ngọc – MSV: 1871020425
Lớp: CNTT1812 – Đại học Đại Nam (DNU)
Môn học: Nhập môn Học máy
Giảng viên: Trần Thu Trang

Mô tả

Bài toán phân loại ảnh X-quang ngực thành hai lớp: NORMAL (bình thường) và PNEUMONIA (viêm phổi). Notebook so sánh hai hướng trích xuất đặc trưng:

Hướng	Đặc trưng / Mô hình
(A) Cổ điển	HOG, HOG + LBP + Histogram, kết hợp bộ phân loại học máy truyền thống
(B) Transfer Learning	ResNet50, DenseNet121, EfficientNet-B0 (pretrained ImageNet, lấy vector đặc trưng trước lớp phân loại)
Dataset
Chest X-Ray Images (Pneumonia) – Kaggle (Paul Mooney)
Tải tự động trong notebook bằng thư viện kagglehub.
Cấu trúc notebook
Cell / Mục	Nội dung
1. EDA	Đặt vấn đề và phân tích dữ liệu
2. Tiền xử lý, 3. Trích xuất đặc trưng, 4. Huấn luyện	Thiết kế giải pháp và quy trình
5. Đánh giá	Thử nghiệm và kết quả
6. Lưu mô hình & GUI	Giao diện demo bằng Gradio (điểm thưởng)
Cách chạy trên Colab
Bấm nút Open In Colab ở đầu file này.
(Tùy chọn) Bật GPU: Runtime → Change runtime type → GPU.
Chạy lần lượt từ trên xuống dưới: Runtime → Run all.

Lưu ý:

Mặc định notebook chạy bản nhẹ cho CPU (AUG_COPIES = 0, chỉ dùng ResNet50).
Nếu có GPU, đặt AUG_COPIES = 1 và thêm 'EfficientNet-B0', 'DenseNet121' vào DEEP_NAMES.
Thư viện sử dụng
bash
pip install kagglehub gradio scikit-image

Ngoài ra: numpy, pandas, matplotlib, seaborn, Pillow, scikit-learn, joblib, tqdm.

Kết quả

Bổ sung bảng so sánh độ chính xác, F1-score, ma trận nhầm lẫn của các mô hình sau khi chạy xong.
