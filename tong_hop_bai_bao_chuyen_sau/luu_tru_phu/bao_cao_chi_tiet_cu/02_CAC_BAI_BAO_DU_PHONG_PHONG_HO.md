# TỔNG HỢP CÁC BÀI BÁO DỰ PHÒNG ("PHÒNG HỜ") ĐÃ ĐỌC TOÀN VĂN (2025–2026)

> **Mục đích của nhóm bài báo dự phòng ("phòng hờ"):**
> Ngoài Top 5 bài báo sát sườn với 3 khoảng trống (Gap A, B, C), khi viết báo cáo nghiên cứu hoặc bảo vệ trước hội đồng, nhóm bạn chắc chắn sẽ gặp các câu hỏi mở rộng như:
> 1. *"Tại sao độ chính xác từng đoạn (`BSA` = 54.68%) lại thấp hơn nhiều so với độ chính xác cả video (`VA` = 65.2%)? Có phải do nhãn cấp độ video bị nhiễu không?"*
> 2. *"Nếu không dùng giai đoạn Calibration đầu giờ mà muốn mô hình tự thích nghi liên tục trong lúc lái (Calibration-Free / Online Test-Time Adaptation) thì làm thế nào?"*
> 3. *"Nếu thay mạng HM-LSTM (2019) bằng các kiến trúc hiện đại năm 2025–2026 như Đồ thị Không-Thời gian (Spatio-Temporal Graph), Mạng Tích chập Thời gian Nhân quả (Dilated Causal TCN) hay Vision Transformer (ViT/Swin) thì dùng bài nào tham khảo?"*
> 4. *"Tại sao có những bài báo năm 2025 trên MDPI Sensors hay PLOS ONE báo cáo đạt 99.9% trên UTA-RLDD mà nhóm em chỉ đạt quanh mức 65%–75%?"*
>
> Dưới đây là **8 bài báo dự phòng (2025–2026) đã được tải và đọc toàn văn 100%**, chia làm 4 nhóm chiến lược để nhóm bạn sẵn sàng trả lời mọi câu hỏi phản biện hoặc mở rộng hướng nghiên cứu bất cứ lúc nào.

---

## NHÓM 1: Các Bài Báo Về Bộ Dữ Liệu Mới & Chứng Minh Nhiễu Nhãn Cấp Độ Video (Video-Level Label Noise)

### Dự phòng #1: Mujtaba et al. (IEEE ICIP 2026 / `arXiv:2512.11446`) — **YawDD+**
- **Tiêu đề:** *YawDD+: Frame-level Annotations for Accurate Yawn Recognition on Edge Platforms*
- **Tác giả:**ibrahim Mujtaba,ihab Alzalam, et al. (University of Ottawa, Canada — chính là nhóm tác giả tạo ra bộ dữ liệu YawDD gốc nổi tiếng!).
- **Hội nghị / Mã định danh:** IEEE International Conference on Image Processing (ICIP), 2026 — `arXiv:2512.11446v1` (Công bố 12/2025) — https://arxiv.org/abs/2512.11446
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 6 trang, 771 dòng văn bản]**
- **Phát hiện cốt lõi từ Toàn văn (Mục 1 & Mục 3, Trang 1–3):**
  - Nhóm tác giả tự "bóc phốt" cách gán nhãn cấp độ video (Video-level labeling) của các bộ dữ liệu buồn ngủ truyền thống (bao gồm cả YawDD gốc và UTA-RLDD): Khi cả một đoạn video dài được gán nhãn duy nhất là `Yawning` hoặc `Drowsy`, thực tế hành vi ngáp/buồn ngủ chỉ diễn ra trong một phần rất nhỏ của video!
  - **Con số thống kê chấn động (Trang 2–3):**
    - Trong video của Đối tượng số 1 mang nhãn `Yawning` (dài 387 frames), tài xế thực sự chỉ ngáp trong **93 frames (24%)**, còn **294 frames (76%)** là trạng thái bình thường!
    - Tính trên toàn bộ 342 video của bộ dữ liệu (287,225 frames), chỉ có **22,875 frames (7.96%)** thực sự là hành động ngáp, còn **264,350 frames (92.04%)** là trạng thái bình thường hoặc đang nói chuyện!
  - Khi gán nhãn lại từng khung hình (`YawDD+`), mạng nhẹ `MNasNet` tăng độ chính xác lên **99.34%** (thời gian suy luận **12.03 ms** trên Jetson Orin AGX) và `YOLOv11` đạt **95.69% mAP**.
- **Cách Nhóm 05 dùng bài này để bảo vệ kết quả:**
  - Dùng số liệu của `YawDD+` để giải thích **tại sao trên tập UTA-RLDD (video dài 10 phút), `Blink Sequence Accuracy (BSA)` chỉ đạt ~54.68% trong khi `Video Accuracy (VA)` đạt 65.2%**: Bởi vì UTA-RLDD chỉ có 1 nhãn duy nhất cho cả video 10 phút! Một người ở trạng thái `Low Vigilant` hoặc `Drowsy` không thể chớp mắt chậm ở mọi giây trong suốt 10 phút; rất nhiều cửa sổ 30-blink trong video `Drowsy` thực chất mang đặc trưng `Alert` (nhiễu nhãn cấp độ cửa sổ con - sub-window label noise).

---

### Dự phòng #2: Bodaghi et al. (*Nature Scientific Data* 2026 / `arXiv:2507.13403`) — **Bộ dữ liệu đa phương thức UL-DD**
- **Tiêu đề:** *UL-DD: A Multimodal Drowsiness Dataset Using Video, Biometric Signals, and Behavioral Data*
- **Tác giả:** Milad Bodaghi, Majid Hosseini, et al. (University of Louisiana at Lafayette, Mỹ).
- **Tạp chí / Mã định danh:** *Scientific Data* (Nature Portfolio), 2026 — `doi:10.1038/s41597-025-06540-1` / `arXiv:2507.13403` (https://arxiv.org/abs/2507.13403)
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 29 trang, 1433 dòng văn bản]**
- **Phê bình trực tiếp tập UTA-RLDD trong Toàn văn (Mục 2 "Related Works", Trang 3–5):**
  - Tác giả phân tích chi tiết ưu/nhược điểm của `UTA-RLDD` (Ghoddoosian 2019), `NTHU-DDD`, `YawDD`, và `DROZY`.
  - Họ chỉ ra rằng mặc dù `UTA-RLDD` có thời lượng lớn (30 giờ, 60 người) và chớp mắt tự nhiên hơn `NTHU-DDD` (vốn yêu cầu diễn viên đóng kịch), nhưng `UTA-RLDD` lại được quay khi người tham gia ngồi xem điện thoại/máy tính chứ không thực sự cầm vô-lăng lái xe liên tục, và chỉ thu thập 1 nhãn KSS cho cả đoạn video 10 phút thay vì theo dõi sự tiến triển liên tục từ tỉnh sang buồn ngủ trong một chuyến đi dài.
- **Thông tin kỹ thuật bộ dữ liệu mới UL-DD (Mục 3–4, Trang 5–16):**
  - 19 tài xế lái xe mô phỏng liên tục suốt **40 phút** trên cao tốc đơn điệu; đánh giá nhãn KSS (1–9) **mỗi 4 phút một lần** kết hợp 3 chuyên gia chấm độc lập (độ đồng thuận Quadratic Cohen's Kappa $\kappa = 0.967$).
  - Đồng bộ hóa: Camera RGB + Hồng ngoại (IR) + Độ sâu 3D (Stereolabs ZED-2 ở 60 FPS) trích xuất **68 facial landmarks + 30 Facial Action Units (FAUs) + MediaPipe Pose** + Vòng tay sinh học Empatica E4 (`HR`, `EDA`, `TEMP`, `BVP`, `IBI`) + Cảm biến nhịp tim/SpO2 + 3 cảm biến lực bóp vô-lăng (FSR) + Telemetry xe tải.
  - **Kết quả Baseline 5-Fold Cross-Validation (Bảng 5, Trang 18):** Nếu chỉ dùng đặc trưng khuôn mặt đơn lẻ (`FAU` hoặc `Pose`), độ chính xác phân loại 3 mức buồn ngủ cũng chỉ đạt **52% – 68%** (rất khớp với con số **65.2%** của Ghoddoosian 2019 trên UTA-RLDD!); khi kết hợp đa phương thức (Khuôn mặt + Sinh học + Lực nắm vô lăng) với SVM thì tăng lên **84%**.
- **Cách Nhóm 05 dùng bài này:**
  - Dùng làm bằng chứng khẳng định rằng trong các điều kiện thực tế (không rò rỉ dữ liệu, chia 5-fold nghiêm ngặt), việc chỉ nhìn vào camera khuôn mặt đơn thuần đạt độ chính xác quanh ngưỡng **60%–70%** cho bài toán đa lớp là hoàn toàn phù hợp với giới hạn vật lý của tín hiệu thị giác (visual modality limit), và muốn lên >84% trong tương lai cần tích hợp thêm cảm biến sinh học/vô-lăng như `UL-DD`.

---

## NHÓM 2: Phương Pháp Thích Nghi Thời Gian Thực Không Cần Calibration (Online Test-Time Adaptation)

### Dự phòng #3: Jang et al. (*IEEE Trans. Human-Machine Systems* 2025 / `arXiv:2511.22030`) — **Calibration-Free Online TTA**
- **Tiêu đề:** *Calibration-Free EEG-based Driver Drowsiness Detection with Online Test-Time Adaptation*
- **Tác giả:** Eun-Hye Jang, et al. (Korea University).
- **Tạp chí / Mã định danh:** *IEEE Transactions on Human-Machine Systems*, 2025 — `arXiv:2511.22030v1` (Công bố 27/11/2025) — https://arxiv.org/abs/2511.22030
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 10 trang, 1739 dòng văn bản]**
- **Tại sao bài này cực kỳ hữu ích cho Gap A dù dùng tín hiệu EEG?**
  - Bài báo này giải quyết bài toán tổng quát về mặt toán học: **Làm sao để chuẩn hóa cá nhân hóa cho một tài xế mới hoàn toàn (Zero-Calibration / Calibration-Free) ngay trong lúc xe đang chạy mà không cần bất kỳ giây phút Calibration có nhãn nào trước chuyến đi?**
  - **Phát hiện lý thuyết cực hay ở Mục III-A (Trang 3–4):**
    - Trong dữ liệu chuỗi thời gian phát trực tuyến của tài xế (streaming time-series), trạng thái của tài xế có sự tương quan thời gian rất mạnh (trong 5–10 phút liền tài xế chỉ ở đúng 1 trạng thái `Alert` hoặc `Drowsy`, tức phân bố tức thời bị lệch hẳn về 1 lớp: $P_T(x, y \mid t_1) \neq P_T(x, y \mid t_2)$).
    - Nếu áp dụng chuẩn hóa thống kê trực tuyến ngây thơ (như cập nhật trực tiếp trung bình $\mu_t$ và phương sai $\sigma_t$ của Batch Normalization theo lô dữ liệu hiện tại — giống thuật toán `Tent` hoặc `CoTTA`), mô hình sẽ **xóa sạch ranh giới giữa lớp Tỉnh và lớp Buồn ngủ**, khiến F1-score sụp đổ thê thảm từ **67.23% xuống chỉ còn 6.46% – 10.47%** (Bảng I, Trang 7)!
  - **Giải pháp toán học của tác giả (Mục III-B & III-C, Trang 4–6):**
    1. **Đóng băng thống kê gốc ($\mu_c^S, \sigma_c^S$)** và chỉ cập nhật tham số affine ($\gamma_c, \beta_c$) bằng tối thiểu hóa Entropy có lọc độ tin cậy.
    2. **Bộ nhớ đệm cân bằng theo năng lượng và độ bền thời gian (Energy- & Persistence-Aware Memory Bank $\mathcal{M}$):** Lưu các mẫu có năng lượng tự do thấp $E(x; f_\theta) = -\log \sum_c \exp(f_\theta(x)_c)$ kết hợp độ bền trạng thái để cập nhật nguyên mẫu lớp (Class Prototypes) theo trung bình trượt hàm mũ (**EMA**).
    3. Giúp tăng độ chính xác độc lập đối tượng (`LOSO` trên 27 tài xế) từ **67.23% lên 81.73% (+14.5% F1-score)** mà không cần 1 giây Calibration nào trước khi lái!
- **Cách Nhóm 05 dùng bài này:**
  - Giải thích sâu sắc cho hội đồng: Tại sao chúng ta không thể lấy trung bình trượt (running mean/std) liên tục trong suốt chuyến đi để chuẩn hóa `EAR`? Bởi vì khi tài xế chuyển sang trạng thái buồn ngủ kéo dài nhiều phút, việc chuẩn hóa liên tục theo cửa sổ hiện tại sẽ biến các cái chớp mắt lờ đờ thành "mức trung bình bình thường mới" (giống hiện tượng sụp đổ xuống 6.46% mà Jang et al. 2025 đã chứng minh)! Do đó, bắt buộc phải cố định thống kê cơ sở từ trạng thái `Alert` được chọn lọc kỹ (AI-Assisted Calibration / Memory Bank).

---

## NHÓM 3: Các Kiến Trúc Học Sâu Nhẹ Mới Nhất (Graph, TCN, Vision Transformer & Tiền Xử Lý Ánh Sáng)

### Dự phòng #4: Ren et al. (Tháng 8/2025, `arXiv:2507.21756`) — **LiteFat (Spatio-Temporal Graph + Dilated Causal TCN)**
- **Tiêu đề:** *LiteFat: Lightweight Spatio-Temporal Graph Learning for Real-Time Driver Fatigue Detection*
- **Tác giả:** Jiaqi Ren, et al.
- **Mã định danh / Link:** `arXiv:2507.21756v2` (Công bố 08/2025) — https://arxiv.org/abs/2507.21756
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 8 trang, 1011 dòng văn bản]**
- **Điểm mạnh kỹ thuật từ Toàn văn (Mục II, Trang 2–5):**
  - Thay vì chỉ tính công thức `EAR` và `MAR` thủ công từ 68 điểm mốc khuôn mặt (vốn bỏ qua mối liên hệ phối hợp giữa mắt, lông mày, miệng và hàm khi ngáp/gật gù), `LiteFat` coi 68 điểm mốc là một **Đồ thị Không-Thời gian (Spatio-Temporal Graph)**.
  - **Ma trận kề tự thích nghi (Self-Adaptive Adjacency Matrix - Công thức 2, Trang 3):** Không nối cạnh đồ thị cố định bằng tay mà học hai ma trận nhúng nút $E_1, E_2 \in \mathbb{R}^{N \times d}$ từ dữ liệu:
    $$\tilde{A}_{\text{adp}} = \text{Softmax}\big(\text{ReLU}(E_1 E_2^T)\big)$$
  - Kết hợp nhánh đồ thị mốc mặt với nhánh đặc trưng ảnh từ `MobileNetV3-Small` và đưa vào mạng **Tích chập Thời gian Nhân quả Giãn nở có Cổng (Gated Dilated Causal TCN)** để nắm bắt chuỗi thời gian dài mà không bị vấn đề triệt tiêu đạo hàm hay tính toán tuần tự chậm chạp như LSTM.
  - Tổng số tham số chỉ **1.32M parameters**, đạt **97.7%** (phân loại 3 lớp hành vi: bình thường, nói chuyện, ngáp) và **99.5%** (phân loại nhị phân) trên các đoạn clip 5 giây của YawDD.
- **Cách Nhóm 05 dùng bài này:**
  - Nếu muốn thử nghiệm thay thế mạng `HM-LSTM` (vốn viết bằng TensorFlow 1.x cổ điển, khó huấn luyện do gradient estimation cho biến nhị phân $z_t^l$) bằng một kiến trúc chuỗi thời gian hiện đại, nhẹ và hội tụ cực nhanh trên PyTorch, **Gated Dilated Causal TCN** trong bài `LiteFat` là ứng cử viên số 1!

---

### Dự phòng #5 & #6: Light-VTD (*Nature Scientific Reports* 03/2026) & Hassan et al. (*Nature Scientific Reports* 05/2025) — **Vision Transformer & Khử Nhiễu Ánh Sáng CLAHE**
- **Bài #5:** *Domain-robust vision transformer with hierarchical swin encoding for explainable low-latency driver drowsiness detection (Light-VTD)* (*Scientific Reports*, Tháng 3/2026, `doi:10.1038/s41598-026-41847-y`, PMCID: `PMC13554065`). **[ĐÃ ĐỌC TOÀN VĂN 100%]**
- **Bài #6:** Hassan et al., *Real-time driver drowsiness detection using transformer architectures: a novel deep learning framework* (*Scientific Reports*, Tháng 5/2025, `doi:10.1038/s41598-025-02111-x`, PMCID: `PMC12092738`). **[ĐÃ ĐỌC TOÀN VĂN 100%]**
- **Thông tin kỹ thuật rút ra từ Toàn văn:**
  - **Tiền xử lý cân bằng sáng cục bộ `CLAHE` (Contrast Limited Adaptive Histogram Equalization):** Trong bài `Light-VTD` (Bảng Ablation, Trang 11), tác giả chứng minh việc áp dụng `CLAHE` trước khi phát hiện mặt/mắt giúp giảm độ suy giảm hiệu năng dưới điều kiện ánh sáng yếu/ngược sáng và tăng độ chính xác trên tập UTA-RLDD thêm **+2.4 điểm phần trăm**.
  - **Giải thích mô hình bằng `Grad-CAM` định lượng:** Tác giả không chỉ vẽ bản đồ nhiệt `Grad-CAM` định tính mà còn đo chỉ số giao trên hợp (**IoU > 0.71**) giữa vùng chú ý của mô hình với vùng hộp giới hạn quanh hai mắt và miệng.
  - **Cảnh báo về cách chia dữ liệu của 2 bài này:** Như đã phân tích ở File `00`, cả hai bài này đều cắt UTA-RLDD thành các khung hình rời rạc (11,787 frames), gộp thành 2 lớp nhị phân và chia ngẫu nhiên theo frame (Stratified Frame Split 80/5/15). Do đó, nhóm bạn chỉ nên trích dẫn họ về mặt **tiền xử lý `CLAHE` và kỹ thuật trực quan hóa `Grad-CAM`**, đồng thời chỉ rõ hạn chế chia dữ liệu theo frame của họ.

---

## NHÓM 4: Các Bài Báo "Làm Bia Đỡ Đạn" (Ví Dụ Điển Hình Về Data Leakage Để Phản Biện Hội Đồng)

Khi bảo vệ đồ án, nếu có giảng viên hỏi: *"Trên mạng có nhiều bài báo năm 2025 công bố độ chính xác trên tập UTA-RLDD lên tới 98.89% – 99.97%, tại sao mô hình của nhóm em đánh giá 5-fold lại chỉ đạt khoảng 65% – 75%?"*, bạn hãy mở ngay 2 bài báo dưới đây (đã đọc toàn văn) để chứng minh:

### Dự phòng #7: Essahraui et al. (MDPI *Sensors*, Tháng 2/2025, `doi:10.3390/s25030812`)
- **Tiêu đề:** *Real-Time Driver Drowsiness Detection Using Facial Analysis and Machine Learning Techniques*
- **Mã định danh:** *Sensors* 2025, 25(3), 812 — PMCID: `PMC11819803`.
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 227 đoạn văn bản dài, 70 KB]**
- **Bằng chứng "Bắt tận tay" lỗi phương pháp luận trong Toàn văn:**
  1. Ở **Bảng 7 (Trang 19)** và **Bảng 10 (Trang 23)**, nhóm tác giả báo cáo trên tập UTA-RLDD: thuật toán `KNN` với **$k = 1$ (1 láng giềng gần nhất)** trên vector đặc trưng HOG đạt độ chính xác **98.89%**, `Random Forest` đạt **99.51%**, `CNN` đạt **99.97%**, và `YOLOv5/v8` đạt **100% Precision, 100% Recall**!
  2. **Nguyên nhân (Mục 3.1.4 & 3.2):** Họ trích xuất các khung hình từ video của các tình nguyện viên, gộp tất cả thành một tập ảnh rồi chia ngẫu nhiên 80% Train / 20% Test theo từng khung hình! Với $k=1$, bộ phân loại `KNN` chỉ đơn giản tìm khung hình sát kề trước hoặc sau đó $0.03$ giây của chính tài xế đó trong tập Train (vốn có khuôn mặt và phông nền giống hệt 99.9%).
  3. **Bằng chứng cẩu thả trong biên tập (Mục 3.4.1, dòng 59 bản trích xuất):** Tác giả copy-paste nhầm đoạn mô tả từ một bài báo bắt gian lận thi cử khác của họ, để nguyên câu: *"enabling the model to successfully distinguish between cheating and non-cheating behaviors"* ngay giữa bài báo phát hiện buồn ngủ lái xe!

---

### Dự phòng #8: Essahraui et al. (*PLOS ONE*, Tháng 11/2025, `doi:10.1371/journal.pone.0332577`) — **FastKAN-DDD**
- **Tiêu đề:** *FastKAN-DDD: A novel fast Kolmogorov-Arnold network-based approach for driver drowsiness detection optimized for TinyML deployment*
- **Mã định danh:** *PLOS ONE* 20(11): e0332577 (Công bố 14/11/2025).
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 21 trang, 1390 dòng văn bản]**
- **Phân tích критический từ Toàn văn:**
  - Tác giả dùng mạng Kolmogorov-Arnold (`FastKAN`) cực nhỏ chỉ gồm 2 tầng (`W*H -> 5 nút ẩn -> 2 đầu ra`) nhận đầu vào là ảnh toàn bộ khuôn mặt đã thu nhỏ xuống chỉ còn **$32 \times 32$ hoặc $64 \times 64$ điểm ảnh** (thậm chí ở Mục 3.1.2 trang 8 tác giả ghi rõ: **không cắt vùng mắt hay miệng** vì cắt mắt làm giảm độ chính xác!).
  - Thế nhưng trong **Bảng 6 (Trang 15)**, mô hình chỉ có 5 nút ẩn trên ảnh mặt độ phân giải thấp $32 \times 32$ này lại được báo cáo đạt **99.94% accuracy** (F1 = 0.9993, AUC = 1.0000) trên tập UTA-RLDD!
  - Khi đọc kỹ **Bảng 2 (Trang 7)** và **Bảng 9 (Trang 17)**:
    1. Họ đã gộp UTA-RLDD thành bài toán **2 lớp nhị phân** và chỉ lấy mẫu đúng 20,205 khung hình tĩnh (không có chuỗi thời gian).
    2. Khi lượng tử hóa sang số nguyên 8-bit (`Full-Integer PTQ` - Bảng 9), độ chính xác trên tập UTA-RLDD lập tức **sụp đổ từ 99.94% xuống còn 48.86%** (tức đoán mò 50/50!).
- **Giá trị cho Nhóm 05:** Cặp bài #7 và #8 là minh chứng sống động nhất cho thấy: trong bài toán phát hiện buồn ngủ trên UTA-RLDD, mọi con số >98% từ việc phân loại ảnh tĩnh từng frame đều là hệ quả của việc làm biến질 bài toán (bỏ lớp `Low Vigilant`, bỏ tính chất chuỗi thời gian, hoặc rò rỉ đặc trưng nhận dạng khuôn mặt).

