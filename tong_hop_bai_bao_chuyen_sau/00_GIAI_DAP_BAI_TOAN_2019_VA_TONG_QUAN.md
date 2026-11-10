# BÁO CÁO TỔNG HỢP DUY NHẤT (MASTER REPORT): GIẢI ĐÁP BÀI TOÁN 2019, ĐỐI CHIẾU THỰC NGHIỆM R0–R2 VÀ HỒ SƠ 12 BÀI BÁO CỐT LÕI & PHẢN BIỆN (2019–2026)

> **Cấu trúc thư mục đã được tinh gọn tối đa:**
> - **File báo cáo trung tâm duy nhất:** [`00_GIAI_DAP_BAI_TOAN_2019_VA_TONG_QUAN.md`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/00_GIAI_DAP_BAI_TOAN_2019_VA_TONG_QUAN.md) *(Tích hợp toàn bộ nội dung quan trọng nhất từ các báo cáo thành phần trước đây).*
> - **Thư mục PDF chính ([`pdf_bai_bao/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao)):** Đã lọc và chỉ giữ lại **12 bài báo cốt lõi nhất** (giải thích trực tiếp các thông số, cung cấp công thức cải tiến `Gap A/B/C`, và phản biện đanh thép các con số `R0–R2` cũng như các bài báo "ảo" 99%).
> - **Thư mục lưu trữ phụ ([`luu_tru_phu/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu)):** Chứa 8 bài báo phụ tham khảo thêm ([`pdf_phu_tham_khao/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao)) và 5 file báo cáo rời cũ ([`bao_cao_chi_tiet_cu/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/bao_cao_chi_tiet_cu)) để thư mục chính hoàn toàn gọn gàng.

---

## 1. Câu Trả Lời Ngắn Gọn & Trực Diện: Bài Báo 2019 Đã Có Lời Giải Chưa?

**CHƯA CÓ LỜI GIẢI TRỌN VẸN.**

Nếu xét đúng **bài toán gốc và giao thức đánh giá nghiêm ngặt (strict benchmark protocol)** mà Ghoddoosian et al. (CVPRW 2019) đặt ra:
1. **Phân loại 3 trạng thái (3-class Early Detection):** `Alert` (Tỉnh táo - Nhãn `0`) vs. `Low Vigilant` (Giảm tỉnh táo / Chớm buồn ngủ - Nhãn `5`, giai đoạn quan trọng nhất để cảnh báo sớm) vs. `Drowsy` (Buồn ngủ - Nhãn `10`).
2. **Đánh giá độc lập đối tượng (Subject-Independent 5-Fold Cross-Validation):** Chia 60 tình nguyện viên (180 video dài ~10 phút, tổng 30 giờ) thành 5 fold (mỗi fold 12 người = 36 video), tuyệt đối không để cùng một tài xế xuất hiện ở cả tập Train và tập Test.

👉 **Bằng chứng đanh thép nhất từ việc đọc toàn văn các bài báo 2024–2026:**
- Bài báo mới nhất thực hiện **đúng giao thức 5-fold 3-class trên toàn bộ tập UTA-RLDD** là **Wolter, Berrio Perez, & Shan (Tháng 11/2025, ĐH Sydney - [`P1_ELA_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P1_ELA_2025.pdf))**. Khi chạy phân loại 3 lớp (`Alert`, `Low Vigilant`, `Drowsy`) bằng góc mí mắt 3D (`ELA`) và 9 đặc trưng chớp mắt, độ chính xác cấp độ video (`VA`) của họ chỉ đạt **52.5%** (thậm chí khớp sát mức `R1 = 53.7%` khi nhóm bạn tự train lại từ đầu!). Khi họ gộp/bỏ lớp trung gian để chuyển về **2 lớp (`Alert` vs. `Drowsy`)**, độ chính xác lập tức nhảy vọt lên **80.4%** (+27.9 điểm phần trăm).
- Thế nhưng, trên mạng hiện có hàng loạt bài báo giai đoạn 2024–2026 tuyên bố đạt **88.89% – 99.97%** trên tập UTA-RLDD. Khi đọc kỹ toàn văn mục *Dataset Preprocessing* và *Experimental Setup* của các bài đó, tất cả đều rơi vào **2 "mánh khóe" làm dễ bài toán (Methodological Shortcuts / Flaws)**:
  1. **Né tránh bài toán phát hiện sớm (Bỏ hoặc gộp lớp `Low Vigilant`):** Biến bài toán 3 lớp thành bài toán nhị phân 2 lớp (`Alert` vs. `Drowsy` hoặc `Safe` vs. `Unsafe`), tức là chỉ phát hiện khi tài xế đã ngủ gật rõ ràng hoặc gộp chung 2 lớp mệt mỏi làm một.
  2. **Rò rỉ dữ liệu nghiêm trọng (Frame-Level Random Split Data Leakage):** Cắt các video thành hàng chục ngàn khung hình (frames), gộp chung toàn bộ 60 người lại rồi chia ngẫu nhiên 80% Train / 20% Test theo từng khung hình! Vì 2 khung hình cách nhau $1/30$ giây của cùng một người có khuôn mặt, quần áo, ánh sáng và nền phòng giống hệt nhau, mô hình chỉ việc "học vẹt" (memorize) mặt tài xế thay vì học biểu hiện buồn ngủ.

---

## 2. Giải Phẫu Toàn Văn Bài Báo Gốc 2019 (Ghoddoosian et al., CVPRW 2019)

- **Tên bài báo:** *A Realistic Dataset and Baseline Temporal Model for Early Drowsiness Detection*
- **Tác giả:** Reza Ghoddoosian, Marnim Galib, Vassilis Athitsos (University of Texas at Arlington).
- **Hội nghị:** IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW), 2019.
- **Link gốc:** https://arxiv.org/abs/1904.07312 | **Bản PDF trong máy:** [`P0_Ghoddoosian_2019.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P0_Ghoddoosian_2019.pdf)

### 2.1. Đặc điểm bộ dữ liệu UTA-RLDD (Mục 3, Trang 3–4)
- **Quy mô:** 60 tình nguyện viên khỏe mạnh (51 nam, 9 nữ, độ tuổi 20–59, thuộc 5 nhóm sắc tộc: 10 Caucasian, 5 Non-white Hispanic, 30 Indo-Aryan & Dravidian, 8 Middle Eastern, 7 East Asian).
- **Điều kiện thực tế:** 21/180 video có đeo kính, 72/180 video có râu. Quay bằng điện thoại/webcam cá nhân của chính tình nguyện viên trong các phòng và điều kiện ánh sáng khác nhau, khoảng cách từ camera đến mặt từ 0.5 đến 1 mét, tốc độ khung hình $< 30\text{ fps}$ (dung lượng tổng 111.3 GB).
- **Nhãn tự đánh giá theo thang đo Karolinska Sleepiness Scale (KSS):**
  - `Alert` (Nhãn `0`): KSS 1–3.
  - `Low Vigilant` (Nhãn `5`): KSS 6–7 (Tài xế chưa ngủ gật, ngoại hình rất giống trạng thái tỉnh táo nhưng phản xạ đã chậm lại).
  - `Drowsy` (Nhãn `10`): KSS 8–9 (Ngáp liên tục, gật gù, mắt nhắm ríu lại / microsleep).
- **So sánh với khả năng con người (Human Judgment Study - Mục 5.2, Trang 7):** Tác giả thuê 20 sinh viên (chia thành 5 nhóm, mỗi nhóm 4 người chấm 1 fold sau khi được xem mẫu). Kết quả con người chỉ đoán đúng **57.8% Video Accuracy (`VA`)** với sai số `VRE = 2.01`, chứng minh bằng mắt thường con người cực kỳ khó phân biệt trạng thái `Low Vigilant`.

### 2.2. Quy trình trích xuất đặc trưng & Thuật toán tìm chớp mắt (Mục 4.1 & Supplementary Material)
1. **Tính tín hiệu `EAR` (Công thức 1):** Dùng `dlib` trích xuất 6 điểm mốc (landmarks $p_1 \dots p_6$) cho mỗi mắt:
   $$\text{EAR} = \frac{\|p_2 - p_6\| + \|p_3 - p_5\|}{2\|p_1 - p_4\|}$$
   Sau đó lấy trung bình `EAR` của 2 mắt và đưa chuỗi 13 frame liên tiếp vào bộ phân loại SVM của Soukupová & Čech (2016).
2. **Thuật toán hậu xử lý `Blink Retrieval` (Algorithm 1, Trang 11 - Supplementary Material):**
   Vì bộ SVM gốc hay bỏ sót các nhịp chớp mắt quá nhanh hoặc quá dài (microsleep), Ghoddoosian tự thiết kế `Algorithm 1`:
   - Đặt ngưỡng thích nghi ban đầu theo đoạn tín hiệu $x$:
     $$\text{THR} = 0.6 \max(x) + 0.4 \min(x)$$
   - Tính đạo hàm bậc nhất $\dot{x}[n] = x[n+1] - x[n]$ và tìm các điểm đổi dấu đạo hàm (cực trị địa phương):
     $$c[n] = (\dot{x}[n+1] \cdot \dot{x}[n]) < 0$$
   - Ghép cặp điểm cực tiểu (`bottom_point`) với 2 điểm cực đại lân cận trước và sau nó (`start_point`, `end_point`), sau đó lọc bỏ các ứng viên có biên độ nhỏ hơn ngưỡng nhiễu (`FilterBlinks`).
3. **4 Đặc trưng mỗi lần chớp mắt $i$ (Công thức 2–5, Trang 4):**
   - **Thời lượng chớp mắt (Duration - tính theo SỐ FRAME):**
     $$\text{Duration}_i = \text{end}_i - \text{start}_i + 1$$
   - **Biên độ chớp mắt (Amplitude):**
     $$\text{Amplitude}_i = \frac{\text{EAR}[\text{start}_i] - 2\text{EAR}[\text{bottom}_i] + \text{EAR}[\text{end}_i]}{2}$$
   - **Vận tốc mở mắt (Eye Opening Velocity - tính theo EAR/FRAME):**
     $$\text{Eye Opening Velocity}_i = \frac{\text{EAR}[\text{end}_i] - \text{EAR}[\text{bottom}_i]}{\text{end}_i - \text{bottom}_i}$$
   - **Tần suất chớp mắt tích lũy (Frequency):**
     $$\text{Frequency}_i = 100 \times \frac{\text{Số lần chớp mắt tính đến nhịp } i}{\text{Tổng số frame tính đến } \text{end}_i}$$

### 2.3. Chuẩn hóa cá nhân hóa (Calibration - Công thức 6, Trang 5)
Để khử sự khác biệt sinh lý giữa các tài xế, tác giả lấy **1/3 số lần chớp mắt đầu tiên trong video `Alert` của đối tượng $m$** để tính trung bình $\mu_{n,m}$ và độ lệch chuẩn $\sigma_{n,m}$ cho từng đặc trưng $n \in \{1,2,3,4\}$. Sau đó chuẩn hóa **2/3 phần còn lại của video `Alert`** cùng toàn bộ video `Low Vigilant` và `Drowsy` của người đó:
$$\tilde{\text{Feature}}_{n,m} = \frac{\text{Feature}_{n,m} - \mu_{n,m}}{\sigma_{n,m}}$$
Cuối cùng mới chuẩn hóa Z-score một lần nữa trên toàn bộ tập huấn luyện (cross-individual standardization).

### 2.4. Kiến trúc HM-LSTM & Hàm mất mát (Công thức 7–11, Trang 5–6)
- Cắt chuỗi chớp mắt của mỗi video thành các cửa sổ trượt dài **$T = 30$ lần chớp mắt liên tiếp**, bước nhảy `stride = 2` (nếu video có ít hơn 30 lần chớp mắt thì chèn số 0 - zero padding ở cuối).
- Qua tầng tuyến tính `FC1` ($4 \rightarrow 64$ với ReLU), đưa vào mạng **4-layer HM-LSTM** (mỗi tầng $L = 32$ hidden units) có biến trạng thái biên nhị phân $z_t^l \in \{0, 1\}$ quyết định thực hiện 1 trong 3 phép toán: `UPDATE`, `COPY`, hoặc `FLUSH`.
- Ghép nối (concatenate) đầu ra ở bước cuối cùng của cả 4 tầng thành vector $e_1 \in \mathbb{R}^{128}$, qua 3 tầng `FC2, FC3, FC4` rồi đưa qua hàm Sigmoid nhân 10:
  $$\text{out} = 10 \cdot \text{Sigmoid}(e_4 W_o + b_o) \in [0, 10]$$
- **Hàm mất mát vùng đệm vô cảm (Insensitive-zone regression loss - Công thức 10):**
  $$\text{Loss} = \frac{1}{N} \sum_{i=1}^{N} \max\left(0, |\text{out}_i - t_i|^2 - \Delta\right), \quad \Delta = 1.253$$
  *(Ghi chú: Trong bài báo trang 6 có một lỗi đánh máy nhỏ ghi $\Delta = 1.58$, nhưng căn bậc hai của $1.58$ mới là $1.257$, và trong code gốc `drowsiness_detection.py` của tác giả đặt cứng `delta = 1.253`, tức biên sai số cho phép khoảng $\pm 1.12$ điểm trên thang 0–10).*
- **Rời rạc hóa & Bỏ phiếu đa số (Discretization & Majority Voting):**
  - $[0, 3.3) \rightarrow \text{Alert (0)}$
  - $[3.3, 6.6] \rightarrow \text{Low Vigilant (5)}$
  - $(6.6, 10] \rightarrow \text{Drowsy (10)}$
  Kết quả dự đoán của cả video (`VA`) là nhãn chiếm đa số trong toàn bộ các cửa sổ 30-blink của video đó.

### 2.5. Kết quả chuẩn của bài báo 2019 (Bảng 2, Trang 7)

| Phương pháp | Blink Sequence Accuracy (`BSA` %) | Video Accuracy (`VA` %) | Blink Sequence Regression Error (`BSRE`) | Video Regression Error (`VRE`) |
| :--- | :---: | :---: | :---: | :---: |
| **HM-LSTM (Ghoddoosian 2019)** | **54.0%** *(code: 54.68%)* | **65.2%** | **1.90** | **1.14** |
| **LSTM (1-layer tiêu chuẩn)** | 50.8% | 61.4% | 2.18 | 1.38 |
| **Fully Connected (FC)** | 49.0% | 57.0% | 2.26 | 1.35 |
| **Con người (Human Judgment)** | — | 57.8% | — | 2.01 |

---

## 3. Giải Mã Kết Quả Thực Nghiệm `R0 – R1 – R2` Của Nhóm ([`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf)) & Đối Chiếu Với Các Bài Báo 2025–2026

Trong báo cáo sơ bộ [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf) của thành viên **Phạm Minh Tiến** (10 trang), 3 giai đoạn `R0`, `R1`, `R2` được thực hiện rất bài bản và cho ra những phát hiện khoa học cực kỳ khớp với các bài báo 2025–2026:

### 3.1. `R0`, `R1`, `R2` xuất phát từ giai đoạn nào của Pipeline?
👉 **Cả 3 giai đoạn `R0`, `R1`, `R2` đều chạy từ Giai đoạn 2 (tức là nạp trực tiếp 25 tệp ma trận `.npy` có sẵn trong thư mục `Fold1..Fold5/` để Train/Test), CHƯA chạy lại Giai đoạn 1 (từ Video thô $\rightarrow$ dlib $\rightarrow$ `.txt` $\rightarrow$ `.npy`)!**
- Cụ thể ở Trang 2 & Trang 6 của [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf), Tiến ghi rõ: đầu vào là **8,661 chuỗi chớp mắt** có kích thước `(N, 30, 4)` và **178 video** (do bộ `.npy` có sẵn của tác giả bị khuyết 2 video ở Fold 4: thiếu `Alert` của Subject `09` và `Low Vigilant` của Subject `26`).

| Ký hiệu | Bản chất thực nghiệm trong [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf) | Kết quả đạt được (`BSA` / `VA`) | Ý nghĩa & Giải thích |
| :--- | :--- | :---: | :--- |
| **`R0`** | **Pretrained Checkpoint Evaluation:** Nạp 5 bộ trọng số mạng `HM-LSTM` đã train sẵn của tác giả (`model_fold1..5`) chạy suy luận (inference) trên 25 file `.npy`. | `BSA = 54.1%` <br> **`VA = 64.9%`** <br> `BSRE = 1.92`, `VRE = 1.15` | Khớp gần như tuyệt đối với bài báo 2019 (`54.0%` và `65.2%`). Chênh lệch `0.3%` ở `VA` là do bộ `.npy` tác giả up lên GitHub có 178 video thay vì 180 video. |
| **`R1`** | **Retraining from Scratch (6 lần độc lập):** Giữ nguyên 25 file `.npy` và toàn bộ siêu tham số trong code tác giả (`80 epochs`, `batch_size=64`, `lr=0.00005`, `delta=1.253`), xóa trọng số cũ và tự train lại từ đầu 6 lần (`run1`..`run6`). | `BSA = 46.8% ± 1.6%` <br> **`VA = 53.7% ± 2.0%`** <br> `BSRE = 2.60`, `VRE = 1.71` | **Sụt giảm `-11.2%` ở `VA` và `-7.3%` ở `BSA` so với `R0`!** Nguyên nhân: Code tác giả không cố định `random seed`, không có tập Validation riêng mà chấm trực tiếp trên tập Test ở mọi epoch; checkpoint `R0` của tác giả là kết quả **cherry-pick epoch tốt nhất trên tập Test**, còn chạy đủ 80 epoch cố định (`R1`) thì mô hình bị overfit và sụt giảm. |
| **`R2`** | **Framework Migration (TF1 $\rightarrow$ Pure NumPy Forward-Pass Port):** Trích xuất toàn bộ ma trận trọng số đã train ở `R0` và `R1` ra khỏi TensorFlow 1.x và viết lại hàm suy luận (forward pass) của `HM-LSTM` bằng **NumPy thuần** (`hm_lstm_Reference.py`). | **Khớp 100% nhãn dự đoán** (`0 / 8,661` chuỗi đổi nhãn; sai số số học dấu phẩy động `< 2.13e-6`) | **Tại sao `R2` khớp 100% với `R0`/`R1`?** Vì `R2` **KHÔNG train lại mô hình**, mà lấy chính bộ trọng số (`W`, `b`) của `R0` và `R1` đem nhân ma trận lại bằng NumPy để kiểm thử xem công thức toán học `HM-LSTM` port sang môi trường Python 3 hiện đại đã đúng 100% với code TF1 cổ đại chưa! |

### 3.2. Các bài báo 2025–2026 bảo vệ và giải thích kết quả `R0 – R1 – R2` của nhóm như thế nào?
1. **Chứng minh con số `R1 (VA = 53.7% ± 2.0%)` khi tự train lại 3-class trên UTA-RLDD là HOÀN TOÀN TRUNG THỰC:**
   - Trong bài báo **Wolter et al. (11/2025 - [`P1_ELA_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P1_ELA_2025.pdf), Bảng IV, Trang 7)**, nhóm ĐH Sydney tự huấn luyện lại từ đầu trên 5-fold UTA-RLDD cho bài toán 3 lớp (`Alert`, `Low Vigilant`, `Drowsy`) và chỉ đạt **`BSA = 46.8%`, `VA = 52.5%`** — trùng khớp đến kinh ngạc với con số **`BSA = 46.8%`, `VA = 53.7%`** trong `R1` của Tiến!
   - Trong bài báo **Nakagama et al. (*IEEE IV 2025* - [`B_Nakagama_2025_Reproducibility_Leakage.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Nakagama_2025_Reproducibility_Leakage.pdf))**, các tác giả chứng minh đây là hiện tượng phổ biến toàn ngành: khi tái lập độc lập (re-train from scratch) các mô hình phát hiện buồn ngủ mà không gian lận chọn checkpoint trên tập Test, độ chính xác thực tế đều rơi về vùng **51% – 70%**.
2. **Giải thích vì sao lớp `Low Vigilant` trong Ma trận nhầm lẫn (Confusion Matrix - Hình 1, Trang 4 của [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf)) bị đoán đúng thấp nhất (`30.5%` ở R1) và vì sao `BSA` luôn thấp hơn `VA` khoảng ~10%:**
   - Bài báo **YawDD+ (Mujtaba et al., *IEEE ICIP 2026* - [`B_YawDD_Plus_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_YawDD_Plus_2025.pdf))** chứng minh rằng trong một video dài gán nhãn cấp độ video (video-level label), có tới **75% – 92% thời lượng tài xế vẫn mang biểu hiện bình thường (neutral)**. Do đó, các cửa sổ 30 lần chớp mắt lẻ (`BSA`) rất dễ rơi vào đoạn bình thường của video `Low Vigilant`, chỉ khi gom toàn bộ video lại bỏ phiếu đa số (`VA`) thì độ chính xác mới tăng thêm ~10%.

---

## 4. Ba Khoảng Trống Nghiên Cứu (3 Open Research Gaps) Còn Bỏ Ngỏ Cho Nhóm 05

Từ việc đọc toàn văn bài báo 2019 đối chiếu với các bài báo 2024–2026, **3 lỗ hổng cốt lõi của bài báo 2019** và các bài báo cung cấp "mảnh ghép" giải quyết được tóm tắt trong bảng sau:

| Khoảng trống trong bài 2019 (Ghoddoosian et al.) | Tại sao cách làm năm 2019 bị lỗi / hạn chế? | Bài báo 2024–2026 nào cung cấp cơ sở & công thức giải quyết? | Hướng giải quyết của Nhóm 05 (SC_25A01_Group05) |
| :--- | :--- | :--- | :--- |
| **GAP A: Giả định Calibration phi thực tế (Oracle Alert Calibration)** | Công thức (6) của bài 2019 lấy **1/3 đầu của video mang nhãn `Alert` (Ground-Truth)** để chuẩn hóa cho cả 3 video của người đó. Ngoài đời thực, khi tài xế mới bật máy lên lái xe, hệ thống **không hề biết trước nhãn Ground-Truth** xem tài xế đang tỉnh hay đã mệt sẵn! | - **Sobirov & Hamidov (07/2026 - [`P3_Zenodo_2026...pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P3_Zenodo_2026_Best_Vol.%203%20No.%207.%202026_591-600.pdf)):** Chứng minh `EAR` lúc tỉnh của các tài xế lệch nhau từ `0.198` đến `0.305`; chuẩn hóa 60s đầu giúp tăng **+3.9% accuracy** (88.4% $\rightarrow$ 92.3%), nhưng ở Trang 8 tác giả **thừa nhận thẳng điểm mù**: hệ thống sẽ hỏng nếu tài xế đã mệt ngay từ phút đầu! <br> - **Gaikwad (10/2026 - [`P5_ResearchSquare_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P5_ResearchSquare_2026.pdf)):** Đề xuất khung Ablation `B0–B3` nhưng mới chạy trên dữ liệu giả lập (synthetic), chưa chạy thật trên UTA-RLDD. | Thiết kế **AI-Assisted / Unsupervised Calibration** không cần nhãn Ground-Truth, và chạy thật kịch bản Ablation (`No Calibration` vs. `Oracle Alert Calibration` vs. `Faulty/Fatigued Calibration` vs. `Unsupervised Calibration`) trên UTA-RLDD. |
| **GAP B: Đặc trưng phụ thuộc FPS (Frame-based Features) & Thiếu pha đóng mắt** | Công thức (2) tính `Duration` bằng **số frame**, Công thức (4) tính `Velocity` bằng **EAR/frame**, và bỏ qua hoàn toàn pha nhắm mắt (`Closing Duration/Velocity`), độ bất đối xứng cũng như tỷ lệ thời gian mắt nhắm (`PERCLOS`). | - **Wolter et al. (11/2025 - [`P1_ELA_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P1_ELA_2025.pdf)):** Phát hiện **169/182 video trong UTA-RLDD bị biến thiên tốc độ khung hình (VFR từ 12–30 Hz)**! Tính thời lượng theo frame làm sai lệch `Closing Duration` tới **32%** khi đổi FPS, khiến độ chính xác rơi từ **98% xuống 69%**! <br> - **Akin & Kalkan (07/2024 - [`P8_Akin_Kalkan_2024_Blink_Behavior.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P8_Akin_Kalkan_2024_Blink_Behavior.pdf)):** Bảng Ablation 2 trên UTA-RLDD chứng minh thêm 3 đặc trưng nội tại pha đóng/mở (`closing`, `reopening`, `diff`) giúp tăng **+5.15% đến +9.64% accuracy**! <br> - **Goswami (11/2025 - [`B_Webcam_MediaPipe_Eye_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Webcam_MediaPipe_Eye_2025.pdf)):** Định lượng Feature Importance trên UTA-RLDD: `EAR Variance` (41%), `Blink Duration` (30%), `PERCLOS` (25%), còn `Blink Frequency` chỉ đóng góp **4%**. | Quy đổi toàn bộ `Duration` sang **giây/mili-giây (`s`/`ms`)** dựa trên FPS thực tế của từng video UTA-RLDD, tính vận tốc vật lý (`EAR/s`), bổ sung `Closing Velocity`, `Reopening/Closing Asymmetry`, `EAR Variance` và `PERCLOS` để tách lớp `Low Vigilant`. |
| **GAP C: Độ trễ quyết định quá lớn (Decision Latency ~2–3 phút)** | Mô hình 2019 đòi hỏi chuỗi cố định **$T = 30$ lần chớp mắt** (với người chớp mắt 10–15 lần/phút thì phải đợi **2–3 phút** mới có 1 dự đoán đầu tiên!), và dùng Majority Voting trên toàn bộ video 10 phút để ra nhãn `VA`. | - **Xie & Xiao (06/2026 - [`P2_CDATW_Frontiers_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P2_CDATW_Frontiers_2026.pdf)):** Đề xuất **Cửa sổ thời gian thích nghi điều khiển bằng độ tự tin (CDATW)**: co cửa sổ xuống **5–10 giây** khi tín hiệu rõ ràng (cảnh báo nhanh) và giãn ra **20–30 giây** khi tín hiệu nhập nhằng (giảm **35.2% báo động giả FAR**), kèm biên trễ hysteresis $\pm 0.05$. | Khảo sát **Đường cong đánh đổi Độ chính xác vs. Độ dài cửa sổ quan sát ($T \in \{5, 10, 15, 20, 30\}$ blinks)** và tích hợp cơ chế cửa sổ thích nghi theo độ tự tin (CDATW) để giảm độ trễ cảnh báo sớm. |

---

## 5. Hồ Sơ Chi Tiết 12 Bài Báo Cốt Lõi & Phản Biện Quan Trọng Nhất (Giữ Trong [`pdf_bai_bao/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao))

Dưới đây là hồ sơ đầy đủ (Tên bài báo, Link gốc, File PDF, Nội dung & Thông số, Phát hiện khi đọc toàn văn, và Công dụng cho Nhóm 05) của **12 bài báo quan trọng nhất** đã được lọc giữ lại trong thư mục [`pdf_bai_bao/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao):

---

### NHÓM I: BÀI BÁO GỐC & CÁC BÀI GIẢI QUYẾT ĐẶC TRƯNG CHỚP MẮT / FPS (`GAP B`)

#### Bài số 1 (`P0` / `P1` trong SC102): Bài báo gốc UTA-RLDD & HM-LSTM (2019)
- **Tên bài báo:** *A Realistic Dataset and Baseline Temporal Model for Early Drowsiness Detection*
- **Tác giả & Năm:** Reza Ghoddoosian, Marnim Galib, Vassilis Athitsos (*IEEE/CVF CVPRW*, 2019).
- **Link trên mạng:** https://arxiv.org/abs/1904.07312
- **File PDF trong máy:** [`P0_Ghoddoosian_2019.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P0_Ghoddoosian_2019.pdf) (1.42 MB)
- **Nội dung & Thông số chính:** Giới thiệu bộ dữ liệu UTA-RLDD (60 người, 180 video ~10 phút, 3 lớp `0`, `5`, `10` chia 5-fold độc lập người lái). Trích xuất 4 đặc trưng mỗi nhịp chớp mắt (`Duration`, `Amplitude`, `Opening Velocity`, `Frequency`), chuẩn hóa theo 1/3 đầu video `Alert`, cắt chuỗi $T = 30$ blinks (`stride = 2`) đưa vào mạng 4-layer HM-LSTM ($L=32$) với hàm loss vùng đệm $\Delta = 1.253$. Đạt `BSA = 54.0%` (code: `54.68%`), `VA = 65.2%`.
- **Phát hiện khi đọc toàn văn:**
  1. Thuật toán tìm chớp mắt thực sự nằm ở *Supplementary Material* (Trang 11, `Algorithm 1`) dùng ngưỡng thích nghi $\text{THR} = 0.6\max(x) + 0.4\min(x)$ và đạo hàm bậc 1.
  2. Công thức (10) trên bài báo in nhầm $\Delta = 1.58$, trong khi code thực tế dùng $\Delta = 1.253$ ($\approx \sqrt{1.58}$).
  3. Toàn bộ thời lượng và vận tốc tính theo đơn vị `frame` chứ không chia cho `FPS`.
- **Công dụng cho Nhóm 05:** Làm baseline gốc (`R0/R1/R2`) và đối tượng phân tích 3 lỗ hổng (`Gap A, B, C`).

---

#### Bài số 2 (`P1` / `A1` trong SC102): Wolter et al. (11/2025) — Góc mí mắt 3D & Phát hiện lỗi VFR trên UTA-RLDD
- **Tên bài báo:** *Eyelid Angle for Blink Detection and Drowsiness Characterization*
- **Tác giả & Năm:**Jan P. Wolter, Julie Stephany Berrio Perez, Mao Shan (University of Sydney, Tháng 11/2025).
- **Link trên mạng:** https://arxiv.org/abs/2511.19519
- **File PDF trong máy:** [`P1_ELA_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P1_ELA_2025.pdf) (1.48 MB)
- **Nội dung & Thông số chính:**
  - Thay `EAR` 2D bằng góc mở mí mắt 3D **Eyelid Angle (`ELA`, đơn vị độ $^\circ$)** từ 478 điểm mốc 3D của MediaPipe Face Mesh để bất biến với góc quay đầu ($\pm 30^\circ$ yaw, $\pm 20^\circ$ pitch).
  - Làm mượt tín hiệu bằng bộ lọc Gaussian có độ lệch chuẩn tỷ lệ theo FPS thực tế: $\sigma = \text{FPS} / 30$.
  - Trích xuất **9 đặc trưng chớp mắt theo đơn vị giây (seconds)** cho mỗi nhịp chớp mắt $i$: tách riêng thời gian đóng mắt $d_1$, thời gian nhắm kín đáy $d_2$, thời gian mở mắt $d_3$, tổng thời gian $D = d_1+d_2+d_3$, biên độ đóng/mở $a_1, a_2$, vận tốc đóng/mở cực đại $v_1, v_2$ và tần suất $f_i$.
- **Phát hiện đắt giá khi đọc toàn văn:**
  1. **Mục IV-B (Trang 5):** Tác giả kiểm tra toàn bộ metadata của UTA-RLDD và phát hiện **169 / 182 video trong UTA-RLDD có tốc độ khung hình biến thiên (Variable Frame Rate - VFR, dao động từ 12 Hz đến 30 Hz)**!
  2. **Bảng II & Hình 6 (Trang 6):** Khi đổi FPS từ 30 Hz xuống 15 Hz, việc tính thời lượng theo `frame` như Ghoddoosian 2019 làm thời gian đóng mắt (`Closing Duration`) bị **sai lệch tới 32%**, kéo độ chính xác phân loại buồn ngủ từ **98% tụt xuống 69%**!
  3. **Bảng IV (Trang 7):** Khi chạy đúng giao thức 5-fold 3-class trên UTA-RLDD với mạng HM-LSTM ($T=30$), họ đạt **`BSA = 46.8%`, `VA = 52.5%`**, nhưng khi chuyển sang 2-class (`Alert` vs `Drowsy`) thì vọt lên **`BSA = 69.5%`, `VA = 80.4%`**.
- **Công dụng cho Nhóm 05:**
  1. **Bảo vệ kết quả `R1` của Tiến (`VA = 53.7%`, `BSA = 46.8%`)** trước Hội đồng: nhóm nghiên cứu ĐH Sydney năm 2025 tự train lại 3-class cũng ra đúng `46.8% / 52.5%`!
  2. **Cơ sở toán học số 1 cho `Gap B`:** Bắt buộc phải chia cho `FPS` thực tế của từng video để đổi `Duration` sang `ms`/`s` và tách riêng pha đóng mắt ($d_1, v_1$) khỏi pha mở mắt ($d_3, v_2$).

---

#### Bài số 3 (`P8` / `A12` trong SC102): Akin & Kalkan (07/2024) — Chứng minh Ablation pha đóng/mở mắt trên UTA-RLDD
- **Tên bài báo:** *Exploring Blink Behavior carefully for Drowsiness Detection*
- **Tác giả & Năm:** Oguzhan Akin, Sinan Kalkan (Middle East Technical University - METU, Tháng 7/2024).
- **Link trên mạng:** https://arxiv.org/abs/2407.02222
- **File PDF trong máy:** [`P8_Akin_Kalkan_2024_Blink_Behavior.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P8_Akin_Kalkan_2024_Blink_Behavior.pdf) (496 KB)
- **Nội dung & Thông số chính:**
  - Thử nghiệm trực tiếp trên tập **UTA-RLDD** (dùng MediaPipe Face Mesh, chọn 21 người có khuôn mặt thẳng không bị che khuất).
  - **Chuẩn hóa cá nhân 2 phút đầu (`Gap A`):** Lấy 2 phút đầu của video `Alert` tính trung bình $\text{EAR}_{ref}$, đặt 2 ngưỡng trễ (hysteresis) $\pm 20\%$:
    $$\text{Threshold}_{high} = \text{EAR}_{ref} + 0.20 \cdot \text{EAR}_{ref}, \quad \text{Threshold}_{low} = \text{EAR}_{ref} - 0.20 \cdot \text{EAR}_{ref}$$
  - **Thí nghiệm Ablation tách 2 bộ đặc trưng chớp mắt (Bảng 2, Trang 3):**
    - Bộ cơ bản (`blink_set1` - 3 đặc trưng): Tổng thời lượng chớp mắt (`duration`), Khoảng cách giữa 2 lần chớp mắt (`interval`), Tổng số lần chớp mắt (`total_blinks`).
    - Bộ mở rộng động học nội tại (`blink_set2` - 6 đặc trưng): Thêm **Thời gian pha nhắm mắt (`closing`)**, **Thời gian pha mở mắt (`reopening`)**, và **Độ lệch bất đối xứng giữa pha mở và pha đóng (`diff = reopening - closing`)**.
- **Phát hiện đắt giá khi đọc toàn văn:**
  1. **Bảng 2 (Trang 3) là bằng chứng Ablation vàng cho `Gap B`:** Khi thêm 3 đặc trưng pha đóng/mở (`blink_set2`), độ chính xác trên UTA-RLDD tăng vọt trên **cả 4 bộ phân loại**:
     - `SVM`: tăng từ `68.00%` $\rightarrow$ **`77.64%` (+9.64%)**
     - `Decision Tree`: tăng từ `64.61%` $\rightarrow$ **`72.51%` (+7.90%)**
     - `kNN`: tăng từ `68.26%` $\rightarrow$ **`75.67%` (+7.41%)**
     - `Random Forest`: tăng từ `73.79%` $\rightarrow$ **`78.94%` (+5.15%)**
  2. **Điểm hạn chế để nhóm bạn vượt qua:** Ở Bảng 1 (Trang 2), họ vẫn đo `closing`, `reopening`, `diff` bằng **đơn vị `#frames` (số khung hình)** chứ chưa quy đổi sang mili-giây (`ms`) theo FPS, và mới chỉ dám chạy phân loại 2 lớp (`0` vs `10`).
- **Công dụng cho Nhóm 05:** Trích dẫn trực tiếp Bảng 2 của bài này để chứng minh: việc bài báo 2019 chỉ dùng `Total Duration` và `Opening Velocity` đã làm mất đi từ **5.15% đến 9.64%** độ chính xác nằm ở pha đóng mắt (`closing`) và độ lệch đóng-mở (`reopening - closing`).

---

#### Bài số 4 (`B_Webcam`): Goswami & Waghmare (11/2025) — Định lượng trọng số quan trọng (Feature Importance) của các đặc trưng mắt trên UTA-RLDD
- **Tên bài báo:** *Webcam-Based Driver Drowsiness Detection Using MediaPipe FaceMesh Eye Features*
- **Tác giả & Năm:** K. Goswami, L. M. Waghmare (IIT Roorkee, Tháng 11/2025).
- **Link trên mạng:** https://doi.org/10.21203/rs.3.rs-8036038/v1
- **File PDF trong máy:** [`B_Webcam_MediaPipe_Eye_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Webcam_MediaPipe_Eye_2025.pdf) (978 KB)
- **Nội dung & Thông số chính:** Trích xuất 4 đặc trưng mắt từ MediaPipe FaceMesh trên tập **UTA-RLDD** trong mỗi cửa sổ 5 giây (`PERCLOS` với ngưỡng $\text{EAR} < 0.21$, `Blink Rate`, `Average Blink Duration`, và `EAR Variance` $\sigma^2_{\text{EAR}}$) đưa vào Random Forest (100 cây).
- **Phát hiện đắt giá khi đọc toàn văn (Mục 5.2, Trang 6):**
  - Tác giả trích xuất **Trọng số đóng góp của từng đặc trưng (Feature Importance)** trên UTA-RLDD:
    1. **`EAR_Variance` (Phương sai/độ dao động của EAR): `0.41` (41%)** — Quan trọng số 1!
    2. **`Avg_Blink_Duration` (Thời lượng chớp mắt): `0.30` (30%)** — Quan trọng số 2!
    3. **`PERCLOS` (Tỷ lệ thời gian mắt nhắm): `0.25` (25%)** — Quan trọng số 3!
    4. **`Blink_Rate` (Tần suất chớp mắt / Frequency): chỉ `0.04` (4%)** — Gần như vô dụng!
- **Công dụng cho Nhóm 05:** Giải thích bằng con số tại sao 4 đặc trưng của Ghoddoosian 2019 bị yếu: tác giả 2019 đưa `Frequency` (chỉ có 4% tác dụng) vào làm 1 trong 4 đặc trưng chính, trong khi lại **bỏ quên hoàn toàn `EAR Variance` (41%) và `PERCLOS` (25%)**!

---

### NHÓM II: CÁC BÀI GIẢI QUYẾT BÀI TOÁN CHUẨN HÓA CÁ NHÂN (`GAP A`) & CỬA SỔ THÍCH NGHI (`GAP C`)

#### Bài số 5 (`P3`): Sobirov & Hamidov (07/2026) — Định lượng Calibration 60s, Sụt giảm Subject-Independent & Lời thú nhận ở Trang 8
- **Tên bài báo:** *Deep Learning for Real-Time Driver Drowsiness Detection from Facial Video: Architecture Comparison, Temporal Modeling, and Edge Deployment*
- **Tác giả & Năm:** Jakhongir Sobirov, Dilshod Hamidov (Tashkent University of Information Technologies, Tháng 7/2026).
- **Link trên mạng:** https://doi.org/10.5281/zenodo.21524614
- **File PDF trong máy:** [`P3_Zenodo_2026_Best_Vol. 3 No. 7. 2026_591-600.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P3_Zenodo_2026_Best_Vol.%203%20No.%207.%202026_591-600.pdf) (853 KB)
- **Nội dung & Thông số chính:**
  - Trích xuất vector 7 chiều mỗi frame từ MediaPipe Face Mesh (`EAR_L`, `EAR_R`, `EAR_mean`, `MAR`, `Pitch`, `Yaw`, `Roll`).
  - Chuẩn hóa cá nhân hóa (`Per-Driver Calibration`) bằng 60 giây đầu tiên (1800 frames ở 30 fps):
    $$\text{EAR}_{\text{norm}}(t) = \frac{\text{EAR}(t) - \mu_{\text{init}}}{\sigma_{\text{init}}}$$
  - Dùng mạng 2-layer Bi-GRU (64 hidden units) với cửa sổ 90 frames (3 giây).
- **Phát hiện đắt giá khi đọc toàn văn:**
  1. **Định lượng sự khác biệt sinh lý cơ địa (Mục 4.4, Trang 6):** Trung vị `EAR` lúc hoàn toàn tỉnh táo (`Alert`) của các tài xế khác nhau trải rộng từ **`0.198` đến `0.305`**. Do đó ngưỡng cố định (`EAR < 0.20`) báo động giả liên tục với người mắt nhỏ (`0.198`) và bỏ sót hoàn toàn người mắt to (`0.305`).
  2. **Định lượng hiệu quả Calibration:** Chuẩn hóa 60s đầu giúp tăng độ chính xác trên tài xế mới từ **88.4% lên 92.3% (+3.9 điểm phần trăm)** và giảm phương sai giữa các tài xế từ $\pm 7.8\%$ xuống $\pm 4.1\%$.
  3. **Bằng chứng vạch trần Data Leakage (Bảng 1, Trang 5):** Cùng 1 mô hình, nếu chia ngẫu nhiên theo cửa sổ (Random Split) đạt **96.1% – 97.8%**, nhưng khi chia độc lập người lái (Subject-Independent Split) thì **tụt ngay 9.4% – 11.4%** (xuống 84.7% – 88.4%).
  4. **Lời thú nhận quý giá ở Trang 8 (Mục 5.2 - Limitations):** Tác giả thừa nhận thẳng: *"Calibration assumes the opening minute is alert. That is reasonable for a freshly started trip, not for a driver who is already fatigued at the start, and a deployed system would need a check for that case."* (Nếu tài xế đã mệt sẵn từ phút đầu tiên, phép chuẩn hóa này sẽ bị hỏng!).
- **Công dụng cho Nhóm 05:** Trích dẫn trực tiếp con số `EAR 0.198–0.305`, mức tăng `+3.9%` và câu thú nhận ở trang 8 để đặt vấn đề cho **Gap A (Faulty Calibration & Unsupervised Calibration)**.

---

#### Bài số 6 (`P4` / `P2` trong SC102): Ersoy et al. (04/2026) & Xu et al. (04/2025) — Ngưỡng cá nhân hóa 75% EAR / 140% MAR
- **Tên bài báo:** *Real-Time Driver Fatigue Detection Using Personalized EAR-MAR Thresholds and Hybrid Deep Features*
- **Tác giả & Năm:** Ersoy et al. (Tháng 4/2026, kế thừa trực tiếp bài Xu et al., MDPI *Information* 2025 `doi:10.3390/info16040294`).
- **Link trên mạng:** https://arxiv.org/abs/2604.22479
- **File PDF trong máy:** [`P4_Personalized_EAR_MAR_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P4_Personalized_EAR_MAR_2026.pdf) (2.14 MB)
- **Nội dung & Thông số chính:**
  - Thiết lập quy trình hiệu chuẩn nhanh **5 giây đầu tiên ($N = 150\text{ frames}$ ở 30 fps)** để đặt ngưỡng cá nhân hóa theo tỷ lệ phần trăm:
    $$\tau_{\text{EAR}} = 0.75 \times \overline{\text{EAR}}_{\text{calib}}, \quad \tau_{\text{MAR}} = 1.40 \times \overline{\text{MAR}}_{\text{calib}}$$
- **Phát hiện đắt giá khi đọc toàn văn:**
  1. Cung cấp công thức ngưỡng đóng mắt cá nhân hóa cực kỳ đơn giản ($\tau_{\text{EAR}} = 0.75 \times \mu_{\text{EAR}}$) để tính `PERCLOS` chính xác cho từng người mà không bị lệch bởi mắt to/mắt nhỏ.
  2. Tuy nhiên, ở Mục II (Trang 2), bài này trích dẫn kết quả trên UTA-RLDD của **Xu et al. (2025)** đạt `86.88%` — thực chất Xu et al. chỉ chọn 22 người (44 video) và **bỏ hoàn toàn lớp `Low Vigilant`** cũng như lọc bỏ các đoạn video nhập nhằng!
- **Công dụng cho Nhóm 05:** Dùng công thức ngưỡng $\tau_{\text{EAR}} = 0.75 \times \overline{\text{EAR}}_{\text{calib}}$ để tính đặc trưng `PERCLOS` cá nhân hóa bổ sung vào vector đặc trưng của nhóm (`Gap A + Gap B`).

---

#### Bài số 7 (`P5` / `A2` trong SC102): Anshuman Gaikwad (10/2026) — Khung Ablation Calibration `B0–B3` (Chưa chạy thật trên UTA-RLDD)
- **Tên bài báo:** *Calibrated Multi-Cue Driver Drowsiness Detection from Facial Landmarks with Confidence-Gated Temporal Fusion*
- **Tác giả & Năm:** Anshuman Gaikwad (Manipal Institute of Technology, Tháng 10/2026).
- **Link trên mạng:** https://doi.org/10.21203/rs.3.rs-11416808/v1
- **File PDF trong máy:** [`P5_ResearchSquare_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P5_ResearchSquare_2026.pdf) (936 KB)
- **Nội dung & Thông số chính:**
  - Đề xuất chuẩn hóa Z-score cá nhân 60s đầu với tham số chống chia cho 0 ($\epsilon = 10^{-3}$), hàm điểm rủi ro liên tục $R(t) \in [0, 1]$, cổng kiểm soát chất lượng khung hình $q_{\min} = 0.7$, và bộ đếm duy trì cảnh báo $T_p = 3\text{s}$.
  - Thiết kế **4 kịch bản Ablation chuẩn mực (`B0–B3`, Mục 4.3, Trang 6)**:
    - `B0`: Ngưỡng cố định toàn cục (Un-calibrated).
    - `B1`: Có Calibration cá nhân hóa theo người lái.
    - `B2`: Có Calibration + Temporal smoothing.
    - `B3`: Đầy đủ Calibration + Confidence Gate + Persistence Timer.
- **Phát hiện đắt giá khi đọc toàn văn (Mục 5.2, Trang 7):**
  - Ở Trang 7, tác giả viết rõ: *"Public-dataset execution on NTHU-DDD and UTA-RLDD was not performed in this workspace because those datasets are not bundled here."* Toàn bộ Bảng 2 và Hình 2 trong bài chỉ chạy trên **9 chuỗi tín hiệu giả lập (synthetic traces)** tự sinh bằng code!
- **Công dụng cho Nhóm 05:** Đây là **cơ hội vàng cho Nhóm 05**: kế thừa thiết kế bảng Ablation `B0–B3` của Gaikwad nhưng **chạy thực nghiệm thật 100% trên 180 video (8,661 chuỗi) của UTA-RLDD**!

---

#### Bài số 8 (`P2` / `A13` trong SC102): Xie & Xiao (06/2026) — Cửa sổ thời gian thích nghi điều khiển bằng độ tự tin (`CDATW` cho `GAP C`)
- **Tên bài báo:** *Real-time driver fatigue detection method based on confidence-driven adaptive time window*
- **Tác giả & Năm:** Kun Xie,Degui Xiao (Hunan University, tạp chí *Frontiers in Neurorobotics*, Tháng 6/2026).
- **Link trên mạng:** https://doi.org/10.3389/fnbot.2026.1857548
- **File PDF trong máy:** [`P2_CDATW_Frontiers_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P2_CDATW_Frontiers_2026.pdf) (2.91 MB)
- **Nội dung & Thông số chính:**
  - Giải quyết trực tiếp mâu thuẫn giữa **Độ trễ phát hiện (Latency)** và **Tỷ lệ báo động giả (False Alarm Rate - FAR)** bằng cơ chế **CDATW**:
  - Ước lượng độ bất định nhận thức $u_t$ qua $N = 10$ lần chạy MC-Dropout và chất lượng tín hiệu $q_t$, suy ra độ tự tin tức thời $c_t = q_t (1 - u_t)$ và làm mượt bằng trung bình trượt hàm mũ ($\bar{c}_t = 0.8 \bar{c}_{t-1} + 0.2 c_t$).
  - **Công thức co giãn độ dài cửa sổ quan sát $W_t$ liên tục từ $W_{\min} = 5\text{s}$ đến $W_{\max} = 30\text{s}$ (Công thức 14, Trang 5):**
    $$W_t = W_{\min} + (1 - \bar{c}_t)\cdot(W_{\max} - W_{\min})$$
    *(Khi tín hiệu rõ ràng $\bar{c}_t \to 1 \Rightarrow W_t \to 5\text{s}$ để cảnh báo tức thì; khi tín hiệu nhiễu/chuyển giao $\bar{c}_t \to 0 \Rightarrow W_t \to 30\text{s}$ để tích lũy thêm bằng chứng).*
  - Áp dụng biên trễ Hysteresis $\Delta = 0.05$ và thời gian giữ tối thiểu $T_{\text{dwell}} = 2\text{s}$ để chống nhảy nhãn.
- **Phát hiện đắt giá khi đọc toàn văn:**
  1. **Bảng 4 (Trang 10):** So với cửa sổ cố định 15s (như kiểu cửa sổ 30-blink cố định của Ghoddoosian 2019), cửa sổ thích nghi CDATW giúp **giảm 35.2% tỷ lệ báo động giả (`FAR` giảm từ 14.2% xuống 9.2%)** và tăng F1-score từ 85.6% lên 89.2%.
  2. **Điểm hạn chế khi chạy trên UTA-RLDD (Mục 3.1.1, Trang 6):** Để đạt con số `89.3%` trên UTA-RLDD, họ đã **gộp chung `Low Vigilant` và `Drowsy` thành 1 lớp nhị phân `Fatigued`**, chưa giải bài toán 3 lớp.
- **Công dụng cho Nhóm 05:** Áp dụng trực tiếp công thức cửa sổ thích nghi $W_t$ của bài này lên đầu ra của mạng `HM-LSTM` để giải quyết **`Gap C` (giảm độ trễ từ 30 lần chớp mắt xuống 5–15 lần chớp mắt khi dự đoán có độ tự tin cao)**.

---

### NHÓM III: BỘ 4 BÀI BÁO PHẢN BIỆN ĐANH THÉP (VẠCH TRẦN CÁC BÀI 88.89% – 99.97% & BẢO VỆ KẾT QUẢ CỦA NHÓM)

#### Bài số 9 (`P6` / `A5` trong SC102): Chavan, Kaede, & Watanuki (07/2026) — Giải mã con số `88.89% VA` trên UTA-RLDD
- **Tên bài báo:** *Early Driver Drowsiness Detection Using Individually Normalized Ocular Dynamics and Dual-Attention Hierarchical BiLSTM*
- **Tác giả & Năm:** Pratik Chavan, Kazuma Kaede, Keiichi Watanuki (Saitama University, Nhật Bản — *AHFE 2026*, Tháng 7/2026).
- **Link trên mạng:** https://doi.org/10.54941/ahfe1007333
- **File PDF trong máy:** [`P6_AHFE_2026_Blendshapes_BiLSTM.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P6_AHFE_2026_Blendshapes_BiLSTM.pdf) (390 KB)
- **Nội dung & Thông số chính:**
  - Dùng 7 hệ số biểu cảm vùng mắt/lông mày của MediaPipe Face Landmarker (`eyeBlink`, `eyeSquint`, `eyeWide`, `browDown`, `browInnerUp`, `browOuterUp`...) thay cho `EAR`.
  - Chuẩn hóa Z-score cá nhân bằng 2 phút đầu của video `Alert`, chia cửa sổ 3600 frames (2 phút) thành 72 đoạn nhỏ (mỗi đoạn 50 frames) đưa vào mạng Dual-Attention Hierarchical BiLSTM trên tập **UTA-RLDD**. Công bố đạt **`VA = 88.89%`**.
- **Phát hiện đắt giá khi đọc toàn văn (Trang 6–8):**
  1. **Tại sao họ đạt `88.89%` trên UTA-RLDD?** Đọc kỹ Mục 2.5 & Mục 3.2 (Trang 6–7): Mặc dù hàm loss lúc train gán nhãn `Alert = 0.0`, `Low Vigilant = 0.5`, `Drowsy = 1.0`, nhưng khi chấm điểm Accuracy, họ **KHÔNG phân loại 3 lớp**, mà đặt **1 ngưỡng nhị phân duy nhất `threshold = 0.35`**: mọi video có điểm $> 0.35$ đều bị gộp chung vào lớp **`Unsafe` (`Low Vigilant + Drowsy`)**, còn $\le 0.35$ là **`Safe` (`Alert`)**! Tức là `88.89%` là **Binary Classification Accuracy (2 lớp)** chứ không phải 3 lớp!
  2. **Tiết lộ quan trọng ở Trang 8 (Mục 3.3):** Chính tác giả bài này đã kiểm tra lại bài `P2` (Xu et al., 2025 - đạt `86.88%`) và vạch trần rằng Xu et al. đã **lọc bỏ thủ công (manually filtered out) các đoạn mẫu nhập nhằng** trong UTA-RLDD nên mới có điểm cao như vậy!
- **Công dụng cho Nhóm 05:** Nếu giảng viên hoặc phản biện hỏi *"Tại sao có bài năm 2026 (Chavan et al. / Xu et al.) dùng chuẩn hóa cá nhân trên UTA-RLDD đạt 86.88% – 88.89% mà nhóm em chạy 3-class chỉ đạt ~54%–65%?"*, nhóm bạn trưng ngay Trang 6 & Trang 8 của [`P6_AHFE_2026_Blendshapes_BiLSTM.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P6_AHFE_2026_Blendshapes_BiLSTM.pdf): họ đặt ngưỡng `0.35` gộp về bài toán nhị phân 2 lớp (`Safe` vs `Unsafe`)!

---

#### Bài số 10 (`B_YawDD_Plus`): Mujtaba et al. (*IEEE ICIP 2026*) — Chứng minh >75%–92% nhiễu nhãn cấp độ Video (Giải thích vì sao `BSA < VA`)
- **Tên bài báo:** *YawDD+: Frame-Level Benchmarking and Temporal-Enhanced Fine-Grained Action Detection for Driver Yawning*
- **Tác giả & Năm:** Mujtaba et al. (*IEEE International Conference on Image Processing - ICIP*, 2026).
- **Link trên mạng:** https://arxiv.org/abs/2512.11446
- **File PDF trong máy:** [`B_YawDD_Plus_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_YawDD_Plus_2025.pdf) (2.00 MB)
- **Nội dung & Phát hiện đắt giá khi đọc toàn văn:**
  - Khi gán nhãn lại từng frame cho toàn bộ bộ dữ liệu video lái xe, các tác giả chứng minh một sự thật thống kê: trong một đoạn video dài mang nhãn cấp độ video là "Ngáp / Mệt mỏi", có tới **75% đến 92.6% số khung hình thực tế tài xế đang ở trạng thái bình thường (`Neutral`)**!
- **Công dụng cho Nhóm 05:** Giải thích trực tiếp thông số trong [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf): Tại sao trên tập UTA-RLDD (video dài 10 phút chỉ có 1 nhãn duy nhất), độ chính xác trên từng chuỗi 30-blink (`BSA = 54.1%` ở `R0` và `46.8%` ở `R1`) luôn thấp hơn độ chính xác toàn video (`VA = 64.9%` ở `R0` và `53.7%` ở `R1`) hơn 10 điểm phần trăm, và tại sao nhãn `Low Vigilant (5)` bị nhầm sang `Alert (0)` nhiều nhất!

---

#### Bài số 11 (`B_Sensors_Essahraui`): Essahraui et al. (*Sensors* 02/2025) — Bằng chứng kinh điển về ngụy tạo độ chính xác 98.89% – 99.97% trên UTA-RLDD do Data Leakage
- **Tên bài báo:** *Real-Time Driver Drowsiness Detection Using Facial Analysis and Machine Learning Techniques*
- **Tác giả & Năm:** Essahraui et al. (MDPI *Sensors*, Tập 25, Số 3, Bài 812, Tháng 2/2025).
- **Link trên mạng:** https://doi.org/10.3390/s25030812
- **File toàn văn trong máy:** [`B_Sensors_2025_Essahraui_FullText.txt`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Sensors_2025_Essahraui_FullText.txt) (51 KB - toàn văn từ PMC)
- **Nội dung & Phát hiện đắt giá khi đọc toàn văn:**
  - Công bố kết quả trên tập UTA-RLDD (Bảng 7 & Bảng 10): **`1-NN` ($k=1$) đạt 98.89%**, `Random Forest` đạt **99.51%**, `CNN` đạt **99.97%**, `YOLOv5/v8` đạt **100% Precision & Recall**!
  - **Sự thật ở Mục 3.1.4 & 3.2:** Trích xuất các khung hình từ video, cắt mặt rồi trộn chung toàn bộ các khung hình của cả 60 người lại và chia Train/Test ngẫu nhiên theo frame! Việc thuật toán `1-NN` ($k=1$, chỉ tìm 1 tấm ảnh giống nhất trong tập Train) đạt **98.89%** là bằng chứng toán học không thể chối cãi rằng với mọi ảnh trong tập Test, luôn có một ảnh cách đó vài phần mười giây của **cùng người đó** nằm trong tập Train (Mô hình nhận diện khuôn mặt chứ không phải nhận diện buồn ngủ!).
  - *(Thậm chí ở dòng 59 mục 3.4.1, tác giả còn copy-paste nhầm câu "distinguish between cheating and non-cheating behaviors" từ bài báo gian lận thi cử sang bài báo buồn ngủ).*
- **Công dụng cho Nhóm 05:** Làm "bia đỡ đạn" phản biện mạnh nhất trong báo cáo và slide bảo vệ để bác bỏ mọi bài báo tuyên bố đạt 98%–99.9% trên UTA-RLDD.

---

#### Bài số 12 (`B_Nakagama`): Nakagama et al. (*IEEE IV 2025*) — Nghiên cứu tái lập (Reproducibility Study) bảo vệ trực tiếp khoảng cách `R0` vs. `R1`
- **Tên bài báo:** *Evaluating the Generalization of Driver Drowsiness Detection Models Across Datasets*
- **Tác giả & Năm:** Ryo Nakagama et al. (*IEEE Intelligent Vehicles Symposium - IV 2025*, Tháng 6/2025).
- **Link trên mạng:** https://arxiv.org/abs/2506.07014
- **File PDF trong máy:** [`B_Nakagama_2025_Reproducibility_Leakage.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Nakagama_2025_Reproducibility_Leakage.pdf) (487 KB)
- **Nội dung & Phát hiện đắt giá khi đọc toàn văn:**
  - Nhóm tác giả Nhật Bản tiến hành tái lập (reproduce from scratch) các mô hình phát hiện buồn ngủ nổi tiếng vốn công bố đạt **91% – 98% accuracy** trong bài báo gốc.
  - Khi huấn luyện lại một cách trung thực (không chọn checkpoint trên tập Test và tách biệt tập đánh giá), độ chính xác của tất cả các mô hình này đều **sụt giảm mạnh xuống còn 51% – 70%** (AUC chỉ đạt `0.52 – 0.53`).
- **Công dụng cho Nhóm 05:** Bảo vệ trực tiếp hiện tượng trong [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf) của Tiến: tại sao checkpoint chọn lọc của tác giả (`R0`) đạt `64.9%`, còn khi tự train lại trung thực 6 lần (`R1`) thì đạt `53.7% ± 2.0%`.

---

## 6. Danh Mục 8 Bài Báo Phụ Đã Lọc Sang Thư Mục Lưu Trữ ([`luu_tru_phu/pdf_phu_tham_khao/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao))

Để thư mục chính không bị loãng, 8 bài báo mở rộng dưới đây đã được chuyển gọn vào [`luu_tru_phu/pdf_phu_tham_khao/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao) (nhóm chỉ cần lấy ra khi muốn đọc thêm về kiến trúc mạng mới, tiền xử lý ánh sáng hoặc tổng quan hệ thống):

1. [`B_Survey_AI_Review_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_Survey_AI_Review_2026.pdf) (`A15` trong SC102 — Hassan et al., *Artificial Intelligence Review* Q1 05/2026, `doi:10.1007/s10462-026-11505-w`): Bài tổng quan PRISMA 83 trang quy định chuẩn thước đo đánh giá (`PR-AUC`, `TPR@FAR`, `ECE`, `Latency`).
2. [`P7_Leakage_Resistant_Calibrated_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/P7_Leakage_Resistant_Calibrated_2026.pdf) (Theivadas et al., 08/2026, `doi:10.21203/rs.3.rs-10574400/v1`): Giao thức chia 3 tập tách biệt `I_fit`, `I_cal`, `I_test` chống rò rỉ dữ liệu khi chọn ngưỡng và Platt scaling.
3. [`B_TTA_CalibrationFree_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_TTA_CalibrationFree_2025.pdf) (Jang et al., 11/2025, `arXiv:2511.22030`): Chứng minh nếu cập nhật trung bình chuẩn hóa liên tục (running mean/variance) khi tài xế đang buồn ngủ dần thì F1-score sập từ `67.23%` xuống `6.46%` (cần cơ chế Selective Test-Time Adaptation).
4. [`B_UL_DD_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_UL_DD_2026.pdf) (Bodaghi et al., *Nature Scientific Data* 2026, `doi:10.1038/s41597-025-06540-1`): Bộ dữ liệu mới thu thập 40 phút liên tục, chấm KSS mỗi 4 phút; 5-fold CV chỉ dùng hình ảnh cũng chỉ đạt `52%–68%`.
5. [`B_LiteFat_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_LiteFat_2025.pdf) (Ren et al., 08/2025, `arXiv:2507.21756`): Kiến trúc Spatio-Temporal Graph + Dilated Causal TCN siêu nhẹ (0.296M tham số) thay thế RNN/LSTM.
6. [`B_LightVTD_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_LightVTD_2026.pdf) (*Nature Scientific Reports* 03/2026, `doi:10.1038/s41598-026-41847-y`): Tiền xử lý cân bằng sáng CLAHE (+2.4% trên UTA-RLDD), nhưng bị lỗi chia 11,787 frames ngẫu nhiên 2 lớp.
7. [`B_FastKAN_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_FastKAN_2025.pdf) (Essahraui et al., *PLOS ONE* 11/2025, `doi:10.1371/journal.pone.0332577`): Ví dụ bài báo bị lỗi chia frame ngẫu nhiên trên UTA-RLDD khiến mô hình overfit nặng (khi nén 8-bit PTQ độ chính xác rơi từ 99.94% xuống 48.86%).
8. [`B_ViT_SciRep_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_ViT_SciRep_2025.pdf) (Hassan et al., *Nature Scientific Reports* 05/2025, `doi:10.1038/s41598-025-02111-x`): Phân loại ảnh vùng mắt tĩnh bằng Vision Transformer (bỏ qua động học chuỗi thời gian).

---

## 7. Cẩm Nang Ngắn Gọn: Keyword Tìm Kiếm & Quy Trình 5 Bước Kiểm Định Nhanh 1 Bài Báo

Khi cần tìm kiếm thêm bài báo mới trên Google Scholar / Semantic Scholar / arXiv, hãy dùng các cụm truy vấn sau và kiểm tra theo 5 bước:

### 7.1. Các câu lệnh tìm kiếm (Search Queries) hiệu quả nhất
- **Tìm các bài trích dẫn bài 2019 và làm về chuỗi chớp mắt / Calibration:**
  ```text
  "UTA-RLDD" AND ("blink" OR "EAR" OR "eyelid") AND ("calibration" OR "personalized" OR "normalization")
  ```
- **Tìm các bài giải quyết lỗi biến thiên FPS (`Gap B`) và động học pha đóng/mở mắt:**
  ```text
  ("UTA-RLDD" OR "Ghoddoosian") AND ("closing velocity" OR "opening velocity" OR "variable frame rate" OR "blink duration")
  ```
- **Tìm các bài giải quyết độ trễ cửa sổ quan sát (`Gap C`):**
  ```text
  "drowsiness detection" AND ("adaptive time window" OR "early detection" OR "decision latency") AND ("LSTM" OR "GRU" OR "TCN")
  ```
- **Tìm các bài phản biện về Data Leakage / Subject-Independent Split:**
  ```text
  "drowsiness detection" AND ("subject-independent" OR "cross-subject" OR "data leakage") AND ("UTA-RLDD" OR "NTHU-DDD")
  ```

### 7.2. Quy trình 5 bước kiểm định toàn văn (Full-Text Audit) trong 3 phút
Mỗi khi tải một bài báo mới về UTA-RLDD, hãy bấm `Ctrl + F` kiểm tra ngay 5 điểm sau:
1. **Bước 1 — Kiểm tra cách chia Train/Test (`fold`, `subject`, `split`):** Có chia theo đúng 5 folds (60 người: 48 Train / 12 Test) không? Nếu thấy *"frames were extracted and split 80/20"* $\rightarrow$ **Rò rỉ dữ liệu cấp độ frame (Data Leakage)**.
2. **Bước 2 — Kiểm tra số lượng lớp (`Low Vigilant`, `3-class`, `binary`, `merged`):** Có giữ nguyên 3 lớp (`0, 5, 10`) không, hay đã xóa lớp `Low Vigilant` / gộp `Low Vigilant + Drowsy` thành 1 lớp `Fatigued/Unsafe`?
3. **Bước 3 — Kiểm tra đơn vị đặc trưng (`frames` vs. `seconds` / `ms` / `FPS`):** Thời lượng chớp mắt tính bằng số frame hay đã chia cho FPS thực tế của video?
4. **Bước 4 — Kiểm tra giả định Calibration (`first`, `initial`, `alert`, `calibration`):** Có giả sử lấy dữ liệu từ video mang nhãn `Alert` có sẵn không, và có kiểm tra trường hợp tài xế mệt ngay từ đầu không?
5. **Bước 5 — Đọc mục `Limitations` và bảng `Ablation Study` ở cuối bài:** Đây luôn là nơi tác giả thú nhận các điểm yếu thật sự (như trang 8 của Sobirov 2026 hay trang 7 của Gaikwad 2026).
