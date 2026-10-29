# **https\://share.gemini.google/XeHFwlHAdeKM**

# 

# **BIÊN BẢN TỔNG KẾT NGHIÊN CỨU & THẨM ĐỊNH BÀI BÁO NỀN TẢNG (BASELINE PAPER)**

| Thông tin | Chi tiết |
| :---- | :---- |
| **Đề tài nghiên cứu:** | **Early Prediction of Driver Drowsiness using Computer Vision with AI-Assisted Calibration** *(Dự đoán sớm trạng thái buồn ngủ của tài xế sử dụng Thị giác máy tính kết hợp Hiệu chuẩn hỗ trợ bởi AI)* |
| **Học phần:** | Phương pháp Nghiên cứu Khoa học (Scientific Method) |
| **Tác giả / Nhóm thực hiện:** | Lê Tiến Bình (MSSV: 25125007\) và Cộng sự |
| **Ngày lập biên bản:** | 25/10/2026 |
| **Mục đích tài liệu:** | Chốt bài báo khoa học nền tảng (Baseline Paper), phân tích tính phù hợp theo 4 tiêu chí học thuật, xác định điểm cải tiến (Optimization) và vạch rõ lộ trình kỹ thuật kế tiếp. |

## **1\. THÔNG TIN BÀI BÁO KHOA HỌC ĐƯỢC LỰA CHỌN**

* **Tên bài báo:** *A Dataset and Benchmark for Malfunctioning and Drowsy Driver Detection (Early Drowsiness Detection)*  
* **Tác giả:** Reza Ghoddoosian, Marnim Galib, Vassilis Athitsos  
* **Đơn vị nghiên cứu:** Vision-Learning-Mining (VLM) Laboratory – Đại học Texas tại Arlington (UTA), Hoa Kỳ.  
* **Hội nghị xuất bản:** **IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW 2019\)**.  
* **Liên kết arXiv:** [https\://arxiv.org/abs/1904.07312](https://arxiv.org/abs/1904.07312)  
* **Kho mã nguồn & Dữ liệu GitHub:** [https\://github.com/rezaghoddoosian/Early-Drowsiness-Detection](https://github.com/rezaghoddoosian/Early-Drowsiness-Detection)  
* **Tập dữ liệu chuẩn đi kèm:** **UTA Real-Life Drowsiness Dataset (UTA-RLDD)**.

## **2\. THẨM ĐỊNH THEO 4 TIÊU CHÍ CHỌN ĐỀ TÀI KHOA HỌC**

| Tiêu chí | Đánh giá thực tế trên bài báo của Reza Ghoddoosian et al. (CVPRW 2019\) | Kết luận |
| :---- | :---- | :---- |
| **1\. Thích (Relevance & Interest)** | Đề tài trực tiếp giải quyết bài toán an toàn giao thông, cứu sống sinh mạng con người bằng công nghệ AI và Thị giác máy tính (DMS). Có sản phẩm trực quan thời gian thực. | **ĐẠT** |
| **2\. Có Paper chuẩn (Credibility)** | Xuất bản tại **CVPRW** – hội nghị Thị giác máy tính danh giá bậc nhất thế giới. Đây là công trình tiêu chuẩn (Benchmark) được hầu hết các nghiên cứu từ 2019 đến nay trích dẫn. | **ĐẠT** |
| **3\. Có Dataset thực tế (Benchmark Data)** | Đi kèm bộ dữ liệu **UTA-RLDD** gồm 60 đối tượng với 180 video (\~30 giờ) ở 3 trạng thái: Alert (0), Low Vigilance (1), Drowsy (2) quay trong điều kiện đời thực, không phải diễn xuất. | **ĐẠT** |
| **4\. Có Code sẵn (Open Source Code)** | Mã nguồn mở hoàn toàn trên GitHub: cung cấp kiến trúc mô hình, pipeline tính toán và các file mảng đặc trưng trích xuất sẵn (.npy) phục vụ 5-Fold Cross Validation. | **ĐẠT** |

## **3\. PHÂN TÍCH KHOẢNG TRỐNG (RESEARCH GAP) & HƯỚNG TỐI ƯU HÓA (OPTIMIZATION)**

Bản chất của nghiên cứu khoa học không phải là sao chép nguyên xi code cũ, mà là **chỉ ra điểm nghẽn của công trình gốc và đề xuất giải pháp tối ưu hơn có phương pháp luận minh bạch**.

\[Công trình gốc (CVPRW 2019)\]                   \[Hướng đề xuất Tối ưu (Nghiên cứu của bạn)\]  
• Dlib 68 điểm (chậm \~15 FPS, dễ mất mốc)  ───► • MediaPipe Face Mesh 468 điểm (30-60 FPS trên CPU)  
• Ngưỡng chung, không cá nhân hóa          ───► • AI-Assisted Calibration (GMM 2 cụm) 30s đầu  
• Mô hình HM-LSTM phức tạp, nặng nề        ───► • Bộ 7 đặc trưng Động học \+ Máy học nhẹ (SVM/Random Forest)  
• Dễ báo động giả trên mắt hẹp / một mí    ───► • Khử hoàn toàn sai lệch cơ địa nhờ EAR\_norm \= EAR / μ\_open

### **Bảng đối chiếu chi tiết giữa Baseline và Đề xuất cải tiến:**

| Thành phần kỹ thuật | Phương pháp trong Paper gốc (Baseline) | Đề xuất Cải tiến của Nhóm (Our Proposal) | Giá trị Khoa học mang lại |
| :---- | :---- | :---- | :---- |
| **Bộ trích xuất Landmark (Landmark Extraction)** | Sử dụng \*\* |  |  |

