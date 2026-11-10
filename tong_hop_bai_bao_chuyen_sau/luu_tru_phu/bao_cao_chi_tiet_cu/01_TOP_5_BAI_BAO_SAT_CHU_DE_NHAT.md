# PHÂN TÍCH TOÀN VĂN TOP 5 BÀI BÁO SÁT CHỦ ĐỀ NHẤT (2025–2026)

> **Cam kết chất lượng:** Cả 5 cụm công trình dưới đây đều đã được tải bản PDF gốc và **đọc toàn văn 100% từ trang đầu đến trang cuối** (không đọc lướt Abstract). Mọi công thức toán học, số hiệu bảng biểu, siêu tham số và cả những điểm yếu/thừa nhận của chính tác giả ở cuối bài đều được trích xuất chính xác tuyệt đối để nhóm bạn sử dụng làm cơ sở lý thuyết và đối chứng thực nghiệm.

---

## Bảng Tổng Hợp Nhanh Top 5 Bài Báo Trọng Tâm

| STT | Bài báo & Năm công bố | Mảnh ghép giải quyết cho Đề tài Nhóm 05 | Bộ dữ liệu & Giao thức đánh giá | Kết quả chính (Trích từ Toàn văn) | Giá trị cốt lõi mang lại cho Nhóm 05 |
| :-: | :--- | :--- | :--- | :--- | :--- |
| **#1** | **Wolter, Berrio Perez, & Shan (11/2025)**<br>*Blinking Beyond EAR: A Stable Eyelid Angle Metric...*<br>(`arXiv:2511.19519`, ĐH Sydney) | **Gap B:** Động học chớp mắt (`Blink Kinematics`), xử lý biến thiên tốc độ khung hình (`VFR`), và bằng chứng 3-class vs. 2-class trên UTA-RLDD. | **UTA-RLDD** (đúng 5-fold Subject-Independent của Ghoddoosian) + **3D Blender Synthetic Benchmark** | • UTA-RLDD 3-class `VA`: **52.5%**<br>• UTA-RLDD 2-class `VA`: **80.4%**<br>• Khác FPS làm lệch `Closing Duration` **32%**, tụt Acc từ **98% $\rightarrow$ 69%** | Phát hiện **169/182 video UTA-RLDD bị biến thiên FPS (12–30 Hz)**! Cung cấp bộ lọc Gaussian tỷ lệ theo FPS ($\sigma=\text{FPS}/30$) và 9 đặc trưng tách pha đóng ($d_1$), nhắm ($d_2$), mở ($d_3$). |
| **#2** | **Sobirov & Hamidov (07/2026)**<br>*Subject-Independent Model and Individual Calibration Algorithms...*<br>(`doi:10.5281/zenodo.21524614`) | **Gap A:** Định lượng mức tụt giảm khi chia Subject-Independent và hiệu quả của **Individual Calibration 60s** + Điểm mù khi tài xế mệt sẵn từ đầu. | **NTHU-DDD** (36 tài xế, 32,412 cửa sổ 5s; so sánh Random Split vs. Subject-Independent 22/6/8) | • Random Split GRU: **97.8%**<br>• Subject-Indep GRU: **88.4%** (-9.4 pp)<br>• **+Calibration 60s: 92.3%** (+3.9 pp, F1 = 91.4%) | Đo được `EAR` trung vị lúc tỉnh dao động từ **0.198 đến 0.305** (>50%). Tác giả **thừa nhận ở trang 8** rằng Calibration 60s đầu sẽ hỏng nếu tài xế đã mệt sẵn khi bắt đầu lái $\rightarrow$ Mở đường trực tiếp cho **AI-Assisted Calibration** của nhóm! |
| **#3** | **Xie & Xiao (06/2026)**<br>*Confidence-driven adaptive time window (CDATW) for real-time driver fatigue detection...*<br>(*Frontiers in Neurorobotics*, `10.3389/fnbot.2026.1857548`) | **Gap C:** Giải quyết bài toán đánh đổi **Độ chính xác vs. Độ trễ quyết định (Decision Latency)** bằng cửa sổ thời gian thích nghi theo độ tự tin (5s–30s). | **NTHU-DDD**, **DROZY**, **UTA-RLDD** (60 người, gộp 2 lớp), **YawDD** (5-fold Subject-Independent + Cross-dataset) | • NTHU-DDD: **91.8%** (+3.3 pp nhờ CDATW)<br>• UTA-RLDD (2-class): **89.3%**<br>• Giảm **35.2% Báo động giả (FAR)** (từ 12.8% xuống 8.3%) | Cung cấp thuật toán hoàn chỉnh điều chỉnh cửa sổ trung bình trượt hàm mũ (`EWMA`) từ **5s đến 30s** dựa trên độ tự tin $c_t$ (MC-Dropout $N=10$), kèm biên trễ hysteresis $\pm 0.05$ và thời gian giữ tối thiểu 2 giây. |
| **#4** | **Xu et al. (04/2025, MDPI *Information*)** & **Ersoy et al. (04/2026, `arXiv:2604.22479`)**<br>*Hybrid Facial Features & Personalized EAR/MAR Thresholds* | **Gap A & B:** Kết hợp đặc trưng hình học (`EAR`, `MAR`) với mô hình học sâu và hiệu chuẩn ngưỡng tỷ lệ phần trăm cá nhân hóa (**75% EAR, 140% MAR**). | **NTHU-DDD** & **UTA-RLDD** (44 video 2-class ở bài Xu) + **YawDD / MRL Eye** (ở bài Ersoy) | • Xu 2025: **86.88%** trên UTA-RLDD (2-class), **31.34 FPS** trên CPU<br>• Ersoy 2026: Tăng nhận diện mắt mở từ **89.0% $\rightarrow$ 98.9%**, ngáp từ **92.5% $\rightarrow$ 98.4%** | Cung cấp công thức ngưỡng tỷ lệ $\text{EAR}_{thresh} = 0.75 \times \overline{\text{EAR}}_{cal}$ trong 5s đầu và chứng minh dùng đặc trưng mốc mặt nhẹ chạy đạt >31 FPS trên CPU không cần GPU. |
| **#5** | **Anshuman Gaikwad (10/2026)**<br>*Personalized Temporal Fatigue Analysis and Adaptive Risk Scoring...*<br>(`doi:10.21203/rs.3.rs-11416808/v1`) & **FEM-PDNet (10/2026)** | **Gap A, B & C:** Khung toán học tổng thể kết hợp Calibration Z-score + Điểm rủi ro liên tục $R(t) \in [0, 100]$ + Thiết kế **4 kịch bản Ablation `B0–B3`**. | Thiết kế cho NTHU-DDD, YawDD, DROZY, UTA-RLDD nhưng **mới chỉ chạy trên 9 chuỗi giả lập (Synthetic Gaussian traces)** | • Cung cấp trọn bộ công thức Calibration $\theta_e = \mu_e - k_e \sigma_e$, cổng chất lượng $q_{\min}=0.7$, bộ đếm bền bỉ $T_p=3\text{s}$ và kịch bản `B0–B3` | **Phát hiện vàng khi đọc Full-Text (Mục VII-D, trang 7):** Tác giả thú nhận **chưa từng chạy thực nghiệm trên tập dữ liệu thật**! Nhóm 05 sẽ là nhóm đầu tiên hiện thực hóa và kiểm chứng kịch bản Ablation Calibration này trên video thật của UTA-RLDD! |

---

## 2. Đi Sâu Từng Bài Báo (Chi Tiết Từ Bản Full-Text)

---

### BÀI BÁO #1: Wolter, Berrio Perez, & Shan (Tháng 11/2025)
- **Tiêu đề:** *Blinking Beyond EAR: A Stable Eyelid Angle Metric for Driver Drowsiness Detection and Data Augmentation*
- **Tác giả:**annis Wolter, Julie Stephany Berrio Perez, Mao Shan (Australian Centre for Robotics, The University of Sydney, Úc).
- **Mã định danh / Link:** `arXiv:2511.19519v1` (Công bố ngày 24/11/2025) — https://arxiv.org/abs/2511.19519
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 8 trang, 874 dòng văn bản]**

#### A. Bài báo này giải quyết vấn đề gì của Ghoddoosian (2019)?
Ghoddoosian (2019) dùng chỉ số `EAR` 2D từ `dlib` và tính các đặc trưng chớp mắt theo **số khung hình (frames)**. Wolter et al. (2025) chứng minh 3 hạn chế chí mạng của cách làm năm 2019:
1. **Sai số do góc quay đầu 3D (Head Pose Sensitivity):** Khi tài xế quay đầu (góc yaw $\beta$) hoặc cúi/ngửa đầu (góc pitch $\alpha$), khoảng cách chiếu 2D của `EAR` bị biến dạng mạnh dù độ mở mí mắt thực tế không đổi.
2. **Sự hỗn loạn tốc độ khung hình (Variable Frame Rate - VFR) trong tập UTA-RLDD:** Ở **Mục IV-B (Trang 5)**, khi phân tích siêu dữ liệu của toàn bộ tập UTA-RLDD, nhóm tác giả phát hiện một sự thật gây sốc: **169 trên tổng số 182 video của UTA-RLDD có tốc độ khung hình biến thiên (VFR) dao động từ 12 Hz đến 30 Hz** (và đối tượng số 23 có kích thước vùng mặt quá nhỏ không trích xuất được mốc mặt ổn định).
3. **Bộ lọc làm mượt cố định gây méo pha đóng mắt:** Các phương pháp dùng bộ lọc Savitzky–Golay hoặc cửa sổ trượt cố định theo số frame sẽ tạo ra một "đỉnh giả" (false positive spike) ngay trước khi mắt nhắm xuống ở các video FPS thấp, làm sai lệch hoàn toàn điểm bắt đầu chớp mắt (`start_point`).

#### B. Công thức toán học & Thuật toán cốt lõi (Mục III, Trang 2–4)
1. **Góc mở mí mắt 3D (`Eyelid Angle - ELA`):**
   - Dùng `MediaPipe Face Mesh V2` lấy 7 điểm mốc 3D cho mí trên và 7 điểm mốc 3D cho mí dưới (hiệu chỉnh trục sâu $z = 1.7 \cdot z_{\text{raw}} \cdot T_{2,2}$ theo ma trận pose $T$).
   - Khớp một mặt phẳng 3D đi qua 7 điểm mí trên và một mặt phẳng 3D đi qua 7 điểm mí dưới bằng phân rã giá trị kỳ dị (**SVD**):
     $$A = L - \frac{1}{n} L J_n = U \Sigma V^T$$
     Vector pháp tuyến của mặt phẳng mí mắt chính là cột thứ 3 của ma trận $V$: $\vec{n} = V_{\cdot, 3}$.
   - Góc mở mí mắt thô giữa pháp tuyến mí dưới $\vec{n}_l$ và mí trên $\vec{n}_u$:
     $$\text{ELA}_{\text{raw}} = \arccos(\vec{n}_l \cdot \vec{n}_u)$$
   - **Tích hợp trọng số góc quay đầu ngang (Yaw-weighted fusion - Công thức 4, Trang 3):** Để mắt nào quay về phía camera nhiều hơn sẽ có trọng số lớn hơn theo hàm Sigmoid $\sigma(x)$ của góc yaw $\beta$:
     $$\text{ELA}_{\text{combined}} = \sigma(-4\beta)\text{ELA}_{\text{left}} + \sigma(4\beta)\text{ELA}_{\text{right}}$$
2. **Bộ lọc Gaussian thích nghi theo tốc độ khung hình (FPS-Adaptive Smoothing - Mục III-C, Trang 3):**
   Thay vì dùng bộ lọc cố định theo số frame, tác giả dùng bộ lọc Gaussian 1 chiều có độ lệch chuẩn $\sigma$ tỷ lệ thuận với tốc độ khung hình thực tế của đoạn video:
   $$\sigma = \frac{\text{FPS}}{30}$$
3. **Trích xuất 9 đặc trưng động học chớp mắt bằng giao điểm tiếp tuyến (Bảng I, Trang 4):**
   Từ đạo hàm bậc nhất $\frac{d}{dt}\text{ELA}_{\text{filtered}}$, tìm cực tiểu $m_1$ (vận tốc nhắm mắt cực đại) và cực đại $m_2$ (vận tốc mở mắt cực đại), kẻ các đường tiếp tuyến cắt đường cơ sở để xác định chính xác 4 mốc thời gian vật lý (tính bằng **giây/mili-giây**): $t_1$ (bắt đầu nhắm), $t_2$ (nhắm kín hoàn toàn), $t_3$ (bắt đầu mở), $t_4$ (mở hoàn toàn). Từ đó tính 9 đặc trưng:
   - $d_1 = t_2 - t_1$: **Closing duration** (Thời gian pha nhắm mắt).
   - $d_2 = t_3 - t_2$: **Closed duration** (Thời gian mắt nhắm kín ở đáy).
   - $d_3 = t_4 - t_3$: **Reopening duration** (Thời gian pha mở mắt).
   - $d_{b,k} = t_{1,k} - t_{1,k-1}$: Khoảng cách giữa 2 lần chớp mắt (Inter-blink interval).
   - $A_{\text{rel}}$: Biên độ tương đối (%).
   - $\text{AVR} = \left|\frac{A_{\text{rel}}}{\text{ELA}'(m_1)}\right|$: Tỷ số Biên độ / Vận tốc nhắm cực đại (Amplitude-Velocity Ratio).
   - $A_N$: Diện tích vùng chớp mắt chuẩn hóa (Normal Area).
   - $\text{PERCLOS}$: Tỷ lệ thời gian mắt nhắm ($\text{ELA} < 20^\circ$) trong cửa sổ 3 phút.
   - $\text{PEROPENING} = \frac{d_3}{d_1 + d_2 + d_3}$: **Tỷ lệ thời gian pha mở mắt trên tổng thời gian chớp mắt** (Đặc trưng cực kỳ nhạy khi buồn ngủ vì pha mở mắt bị kéo dài rõ rệt).

#### C. Kết quả thực nghiệm quan trọng (Mục IV, Trang 4–7)
- **Chứng minh tác hại của khác biệt FPS (Bảng III & Mục IV-E):**
  - Khi đo cùng một nhịp chớp mắt ở 30 Hz so với 50 Hz bằng phương pháp cũ, thời gian nhắm mắt `Closing Duration` ($d_1$) bị **sai lệch tới 32%** (từ $0.088\text{ s}$ xuống $0.060\text{ s}$).
  - Nếu huấn luyện bộ phân loại ở 30 Hz rồi kiểm thử ở 15–50 Hz (kịch bản `AC2`), độ chính xác phân loại chớp mắt của phương pháp cũ (Soukupová/Ghoddoosian) **sụt từ 98% xuống 69%** (và ở 50 Hz sụt từ **92% xuống 46%**), trong khi phương pháp chuẩn hóa theo FPS của Wolter giữ vững ở mức **87%–98%**!
- **Kết quả trên tập UTA-RLDD đúng giao thức 5-fold của Ghoddoosian (Bảng IV, Trang 7):**
  - Tác giả dùng đúng 30 lần chớp mắt liên tiếp, chuẩn hóa theo 1/3 đầu video `Alert`, giảm chiều bằng `PCA` xuống 5 thành phần và phân loại bằng `kNN` ($k=10$) + Majority Voting:
    - **Phân loại 3 lớp (`Alert`, `Low Vigilant`, `Drowsy`):** Đạt **52.5% Video Accuracy (`VA`)** (so với 65.2% của HM-LSTM Ghoddoosian 2019).
    - **Phân loại 2 lớp (`Alert` vs. `Drowsy`):** Nhảy vọt lên **80.4% Video Accuracy (`VA`)**!

#### D. Nhóm 05 lấy được gì từ bài báo này?
1. **Trích dẫn "vàng" cho Gap B:** Trích dẫn con số **169/182 video UTA-RLDD bị biến thiên FPS (12–30 Hz)** và con số **sai lệch 32% thời lượng pha đóng mắt** của Wolter et al. (2025) để giải thích tại sao việc Ghoddoosian (2019) tính `Duration` theo số frame và `Velocity` theo `EAR/frame` là lỗi nghiêm trọng.
2. **Công thức cải tiến trực tiếp:** Áp dụng bộ lọc làm mượt tỷ lệ với FPS ($\sigma = \text{FPS}/30$), đổi toàn bộ đơn vị sang thời gian vật lý (`ms`), và bổ sung đặc trưng tỷ lệ pha mở mắt $\text{PEROPENING} = \frac{d_{\text{open}}}{d_{\text{total}}}$ cùng tỷ số $\text{AVR}$ vào mô hình chuỗi thời gian (LSTM / HM-LSTM / GRU).
3. **Giải thích tại sao Wolter (2025) chỉ đạt 52.5% ở 3-class:** Vì Wolter gom trung bình đặc trưng rồi chỉ dùng bộ phân loại phi thời gian đơn giản là `PCA(5) + kNN(k=10)`, làm mất cấu trúc chuỗi thời gian từng bước mà `HM-LSTM` của Ghoddoosian (65.2%) nắm bắt được! Nếu nhóm bạn kết hợp **Đặc trưng chuẩn hóa FPS vật lý của Wolter (2025) + Mô hình chuỗi thời gian sâu của Ghoddoosian (2019)**, kết quả sẽ vượt qua cả hai!

---

### BÀI BÁO #2: Sobirov & Hamidov (Tháng 7/2026)
- **Tiêu đề:** *Subject-Independent Model and Individual Calibration Algorithms for Determining Driver Drowsiness Based on Facial Landmarks*
- **Tác giả:** J. Sobirov, V. Hamidov (Tashkent State Transport University).
- **Tạp chí / Mã định danh:** *BEST Journal of Innovation in Science, Research and Development*, Vol. 3, No. 7, pp. 591–600, Tháng 7/2026 — `doi:10.5281/zenodo.21524614` (https://zenodo.org/records/21524614)
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 10 trang, 492 dòng văn bản]**

#### A. Bài báo này giải quyết vấn đề gì?
Bài báo này tấn công trực diện vào **2 vấn đề cốt lõi của đề tài Nhóm 05**:
1. Tại sao các bài báo chia dữ liệu ngẫu nhiên (Random Split) lại báo cáo độ chính xác ảo (>96%), và khi đưa sang người lái mới (Subject-Independent) thì mô hình sụp đổ như thế nào?
2. Sự khác biệt cấu trúc giải phẫu mắt giữa các cá nhân lớn đến mức nào, và thuật toán **Hiệu chuẩn cá nhân (Individual Calibration)** cải thiện được bao nhiêu phần trăm?

#### B. Phương pháp & Công thức (Mục 2, Trang 2–4)
- **Trích xuất đặc trưng:** Dùng `MediaPipe Face Mesh` (468 landmarks) trích xuất vector 4 chiều ở mỗi khung hình:
  $$\mathbf{x}_t = [\text{EAR}_t, \text{MAR}_t, \text{Pitch}_t, \text{Yaw}_t]^T$$
  Trong đó `Pitch` và `Yaw` được ước lượng từ bài toán `Perspective-n-Point (solvePnP)` khớp mô hình mặt 3D chuẩn với 6 điểm mốc 2D (chóp mũi, cằm, khóe mắt trái/phải, khóe miệng trái/phải).
- **Cửa sổ thời gian:** Cắt chuỗi thành các cửa sổ trượt dài **5 giây (150 frames ở 30 FPS)** với bước trượt **1 giây (30 frames)**, thu được tổng cộng 32,412 cửa sổ trên tập NTHU-DDD (36 tài xế).
- **Thuật toán Individual Calibration 60 giây (Mục 2.4, Trang 4):**
  Khi một tài xế mới bắt đầu phiên lái, hệ thống thu thập **60 giây đầu tiên** để tính vector trung bình $\boldsymbol{\mu}_{\text{cal}}$ và độ lệch chuẩn $\boldsymbol{\sigma}_{\text{cal}}$ của riêng tài xế đó, sau đó chuẩn hóa Z-score mọi khung hình tiếp theo:
  $$\tilde{\mathbf{x}}_t = \frac{\mathbf{x}_t - \boldsymbol{\mu}_{\text{cal}}}{\boldsymbol{\sigma}_{\text{cal}}}$$

#### C. Kết quả định lượng đắt giá từ Toàn văn (Mục 3, Trang 4–8)
1. **Định lượng mức độ sụt giảm do Data Leakage (Bảng 1, Trang 5):**

| Kiến trúc mô hình | Random Window Split (Trộn chung người lái) | Subject-Independent Split (22 Train / 6 Val / 8 Test) | Mức sụt giảm thực tế ($\Delta$) |
| :--- | :---: | :---: | :---: |
| **1D-CNN** | 96.1% | 84.7% | **-11.4%** |
| **LSTM** | 97.4% | 87.9% | **-9.5%** |
| **GRU** | **97.8%** | **88.4%** | **-9.4%** |

2. **Bằng chứng về sự khác biệt giải phẫu mắt giữa các tài xế (Mục 3.2, Trang 5–6):**
   - Trên 8 tài xế thuộc tập Test độc lập, độ chính xác của mô hình GRU khi chưa có Calibration dao động cực mạnh từ **74.5% đến 96.1%** (chênh lệch tới **21.6 điểm phần trăm** giữa các cá nhân!).
   - Khi đo giá trị `EAR` trung vị ở trạng thái hoàn toàn tỉnh táo (`Alert`) của các tài xế này, tác giả phát hiện nó trải dài từ **0.198 (người mắt hẹp tự nhiên) đến 0.305 (người mắt to)** — tức biến thiên sinh lý lên tới **hơn 50%**! Nếu dùng ngưỡng cố định $\text{EAR} = 0.21$ như các bài báo truyền thống, người có $\text{EAR}_{\text{alert}} = 0.198$ sẽ bị báo động giả 100% thời gian dù đang hoàn toàn tỉnh táo!
3. **Hiệu quả của Individual Calibration (Mục 3.3, Trang 6–7):**
   - Nhờ chuẩn hóa Z-score bằng 60 giây đầu, độ chính xác Subject-Independent của GRU tăng từ **88.4% lên 92.3% (+3.9 điểm phần trăm)**, F1-score đạt **91.4%**, và khoảng dao động giữa các tài xế thu hẹp lại còn **84.2% – 96.8%** (không còn tài xế nào bị dưới 80%).
4. **Điểm mù chí mạng được chính tác giả thừa nhận (Trang 8, dòng 446):**
   Ở cuối bài báo, Sobirov & Hamidov viết nguyên văn:
   > *"The calibration step uses the first 60 seconds of each test driver's recording, which in NTHU-DDD is annotated as alert... Calibration assumes the opening minute is alert. This holds for most journeys but not for a driver who is already fatigued at the start, and a deployed system would need a check for that case."*
   *(Tạm dịch: "Bước hiệu chuẩn sử dụng 60 giây đầu tiên của mỗi bản ghi tài xế test, vốn được gán nhãn sẵn là tỉnh táo trong NTHU-DDD... Thuật toán hiệu chuẩn giả định phút mở đầu luôn tỉnh táo. Điều này đúng với đa số hành trình nhưng SAI đối với một tài xế đã mệt mỏi sẵn ngay từ lúc bắt đầu, và một hệ thống triển khai thực tế sẽ cần một cơ chế kiểm tra cho trường hợp đó.")*

#### D. Nhóm 05 lấy được gì từ bài báo này?
- Câu trích dẫn ở Trang 8 của Sobirov & Hamidov (2026) chính là **"giấy thông hành" hoàn hảo nhất cho Gap A (AI-Assisted Calibration)** của nhóm bạn! Trong file `CLAUDE.md` của nhóm, thầy hướng dẫn đã hỏi: *"Nếu giai đoạn đầu người lái mệt sẵn hoặc cố tình giả vờ thì Calibration sẽ sai — giải quyết thế nào?"*. Giờ đây bạn có thể trích dẫn thẳng bài báo tháng 7/2026 này để chứng minh: ngay cả các công trình năm 2026 vẫn đang bỏ ngỏ bài toán kiểm định chất lượng dữ liệu Calibration khi không có nhãn `Alert` cho trước!

---

### BÀI BÁO #3: Xie & Xiao (Tháng 6/2026)
- **Tiêu đề:** *Confidence-driven adaptive time window for real-time driver fatigue detection in Level 2-3 autonomous vehicles: a multi-dataset validation study*
- **Tác giả:** Kunlun Xie,ahui Xiao (School of Mechanical Engineering, University of Science and Technology Beijing).
- **Tạp chí / Mã định danh:** *Frontiers in Neurorobotics*, xuất bản ngày 18/06/2026 — `doi:10.3389/fnbot.2026.1857548`
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 14 trang, 1056 dòng văn bản]**

#### A. Bài báo này giải quyết vấn đề gì?
Giải quyết trực tiếp **Gap C (Đánh đổi giữa Độ chính xác và Độ trễ quyết định / Observation Window Length)**:
- Nếu dùng cửa sổ thời gian ngắn (ví dụ 3–5 giây): Hệ thống phản ứng nhanh nhưng cực kỳ nhạy với nhiễu (tài xế nhìn gương chiếu hậu, nói chuyện, cười hoặc chớp mắt sinh lý bình thường cũng bị báo động giả - False Alarm cao).
- Nếu dùng cửa sổ thời gian dài cố định (ví dụ 30–60 giây hoặc 30 lần chớp mắt ~ 2–3 phút như Ghoddoosian 2019): Độ chính xác tăng lên nhưng **độ trễ cảnh báo quá lớn**, tài xế đã gặp tai nạn trước khi cửa sổ kịp tích lũy đủ dữ liệu!

#### B. Kiến trúc 2 tầng & Thuật toán CDATW (Mục 2, Trang 3–6)
1. **Tầng 1 (Cửa sổ cơ sở 1 giây + Ước lượng độ bất định bằng Monte Carlo Dropout):**
   - Trích xuất khung hình ở 30 FPS, cắt thành các đoạn ngắn **1 giây (30 frames)**.
   - Đưa qua backbone nhẹ `MobileNetV3-Small + CBAM` (Channel & Spatial Attention) kết hợp `BiLSTM` (128 hidden units) với tổng tham số chỉ **2.78M parameters** (328M FLOPs, chạy đạt **38–45 FPS / độ trễ $42 \pm 5\text{ ms}$** trên thiết bị nhúng NVIDIA Jetson Xavier NX).
   - Ở mỗi giây $t$, thực hiện **$N = 10$ lượt truyền thẳng ngẫu nhiên (Monte Carlo Dropout forward passes)** với dropout rate $p = 0.2$ để thu được xác suất mệt mỏi trung bình $p_t$ và **độ tự tin nhận thức (epistemic confidence) $c_t \in [0, 1]$** dựa trên phương sai dự đoán (Expected Calibration Error $\text{ECE} = 0.078$).
2. **Tầng 2 (Bộ điều khiển cửa sổ thời gian thích nghi CDATW - Mục 2.4, Trang 5):**
   Thay vì dùng cửa sổ cố định, hệ thống tích lũy điểm mệt mỏi bằng trung bình trượt hàm mũ (**EWMA**) trên một độ dài cửa sổ hiệu dụng $W(c_t) \in [5\text{ s}, 30\text{ s}]$ biến thiên liên tục theo độ tự tin $c_t$:
   - **Khi độ tự tin cao ($c_t > 0.85$):** Tín hiệu khuôn mặt rất rõ ràng (hoặc đang hoàn toàn tỉnh táo, hoặc đang ngủ gật/nhắm mắt kéo dài rõ rệt) $\rightarrow$ **Co ngắn cửa sổ xuống $W \in [5\text{ s}, 10\text{ s}]$** (thực tế trung bình $8.7 \pm 2.3\text{ s}$) để phát cảnh báo khẩn cấp với độ trễ thấp nhất!
   - **Khi độ tự tin trung bình ($0.60 \le c_t \le 0.85$):** Giữ cửa sổ ở mức trung bình **$W \in [10\text{ s}, 20\text{ s}]$**.
   - **Khi độ tự tin thấp ($c_t < 0.60$):** Khuôn mặt bị che khuất một phần, ánh sáng yếu, hoặc tài xế đang ở trạng thái chuyển tiếp nhập nhằng (`Low Vigilant`) $\rightarrow$ **Giãn rộng cửa sổ ra $W \in [20\text{ s}, 30\text{ s}]$** (thực tế trung bình $19.2 \pm 3.8\text{ s}$) để tích lũy thêm bằng chứng lịch sử trước khi kết luận.
   - **Cơ chế chống dao động (Anti-Oscillation):** Áp dụng **biên trễ Hysteresis $\pm 0.05$** tại các ngưỡng chuyển vùng (0.60 và 0.85) và **thời gian giữ tối thiểu (minimum dwell time) $\tau_{\text{dwell}} = 2\text{ giây}$** trước khi cho phép đổi chế độ cửa sổ.

#### C. Kết quả thực nghiệm & Ablation (Mục 3, Trang 6–11)
- **Bảng Ablation trên NTHU-DDD (5-fold Subject-Independent - Bảng 1, Trang 7):**
  - `MobileNetV3-Small` cơ sở: **83.2%**
  - `+ CBAM Attention`: **84.5%** (+1.3%)
  - `+ BiLSTM` (cửa sổ cố định 15s): **88.5%** (+4.0%)
  - **`+ CDATW` (cửa sổ thích nghi 5s–30s): 91.8% (+3.3%, F1 = 91.5%, AUC = 0.956)**.
- **Đánh giá trên 4 bộ dữ liệu độc lập đối tượng (Bảng 2, Trang 8):**
  - `NTHU-DDD`: **91.8%**
  - `DROZY`: **90.5%**
  - **`UTA-RLDD` (60 đối tượng, chia 70%/15%/15% theo người lái, gộp 2 lớp): 89.3%** (F1 = 88.9%, AUC = 0.938).
  - `YawDD`: **88.6%**
- **Giảm báo động giả (Mục 3.4, Trang 9):** So với cửa sổ cố định 15 giây, cơ chế cửa sổ thích nghi CDATW **giảm tỷ lệ báo động giả (False Alarm Rate - FAR) tới 35.2%** (từ **12.8% xuống 8.3%**, $p < 0.001$) trong khi tỷ lệ bỏ sót (False Negative Rate - FNR) không bị ảnh hưởng (17.6% vs. 18.1%, $p = 0.34$).
- **Đánh giá chéo bộ dữ liệu (Cross-Dataset Generalization - Bảng 3, Trang 9):** Khi train trên NTHU-DDD và đem sang test trực tiếp trên UTA-RLDD mà không hiệu chuẩn, độ chính xác tụt từ 89.3% xuống **76.8%** (trung bình cross-dataset tụt **12.8 điểm phần trăm** do lệch phân bố góc máy và đặc điểm đối tượng).

#### D. Nhóm 05 lấy được gì từ bài báo này?
- Đây là **bản thiết kế mẫu cho Gap C**: Nhóm bạn không cần phải thay đổi kiến trúc mạng nặng nề; ngay trên chuỗi dự đoán từng nhịp chớp mắt của mô hình LSTM/HM-LSTM (vốn xuất ra điểm số $\text{out}_t \in [0, 10]$ sau mỗi lần chớp mắt), nhóm có thể định nghĩa độ tự tin $c_t$ dựa trên khoảng cách từ $\text{out}_t$ đến các ngưỡng phân lớp ($3.3$ và $6.6$) hoặc dùng MC-Dropout, từ đó áp dụng quy tắc co/giãn cửa sổ tích lũy `EWMA` (từ $T=5$ blinks đến $T=30$ blinks) giống hệt Xie & Xiao (2026)!

---

### BÀI BÁO #4: Xu et al. (Tháng 4/2025) & Ersoy et al. (Tháng 4/2026)
- **Bài 4A:** Xu, Huang, Liu, & Li (2025) — *Detecting Driver Drowsiness Using Hybrid Facial Features and Ensemble Learning*, MDPI *Information*, 16(4), 294 (`doi:10.3390/info16040294` — bài báo nằm trong danh sách gốc của nhóm).
- **Bài 4B (Bản phát triển trực tiếp năm 2026):** Ersoy, Tatar, Tonbul, & Kırbız (Tháng 4/2026) — *Improving Driver Drowsiness Detection via Personalized EAR/MAR Thresholds and CNN-Based Classification* (`arXiv:2604.22479v1`, công bố 24/04/2026 — https://arxiv.org/abs/2604.22479).
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100%]**

#### A. Cách tiếp cận & Công thức toán học
1. **Xu et al. (2025):**
   - Kết hợp 3 mạng CNN không gian (trích xuất đặc trưng ảnh mặt, mắt, miệng) với các đặc trưng hình học thời gian (`EAR`, `MAR` từ MediaPipe Face Mesh) qua cơ chế **Soft Voting Ensemble**:
     $$\hat{y} = \arg\max_c \sum_{m=1}^{M} w_m P_m(y = c \mid \mathbf{x})$$
   - Đạt **86.88%** trên UTA-RLDD và tốc độ thực thi **31.34 FPS trên CPU**.
   - **Điểm yếu cốt lõi khi đối chiếu với bài toán của Nhóm 05:** Xu et al. (2025) chỉ lấy 22 người (44 video) của UTA-RLDD ở **2 lớp `Alert` và `Drowsy`, bỏ qua hoàn toàn lớp `Low Vigilant`**, đồng thời dùng ngưỡng cố định tìm bằng Grid Search chứ chưa có thuật toán Calibration thích nghi cho từng cá nhân.
2. **Ersoy et al. (Tháng 4/2026 - Trích dẫn trực tiếp Xu et al. [10] để giải quyết vấn đề ngưỡng cố định):**
   - Dùng `MediaPipe Face Mesh` (468 landmarks) tính `EAR` (trung bình 2 mắt) và `MAR` (tỷ số khoảng cách môi trên-dưới chia cho chiều rộng miệng).
   - **Giao thức Calibration 5 giây trước khi lái (Mục III-B, Trang 2):**
     Yêu cầu tài xế nhìn thẳng ở tư thế tự nhiên trong **5 giây đầu tiên**, tính trung bình cơ sở $\overline{\text{EAR}}_{\text{cal}}$ và $\overline{\text{MAR}}_{\text{cal}}$, sau đó thiết lập ngưỡng cá nhân hóa theo tỷ lệ phần trăm:
     $$\text{EAR}_{\text{thresh}} = 0.75 \times \overline{\text{EAR}}_{\text{cal}}$$
     $$\text{MAR}_{\text{thresh}} = 1.40 \times \overline{\text{MAR}}_{\text{cal}}$$
   - Kết hợp bộ đệm làm mượt 15 khung hình (`15-frame temporal buffer`) và mạng CNN 3 tầng tích chập ($32 \rightarrow 64 \rightarrow 128$ filters, вход $64 \times 64 \times 3$, huấn luyện 15 epochs với Adam).

#### B. Kết quả thực nghiệm từ Toàn văn Ersoy et al. (Bảng II & III, Trang 3–4)
- **So sánh Ngưỡng cố định (Fixed Threshold) vs. Ngưỡng cá nhân hóa (Personalized Threshold):**
  - Nhận diện mắt mở (`Open Eye`): Tăng từ **89.0% lên 98.9% (+9.9%)** nhờ không còn bắt nhầm những người có mắt nhỏ tự nhiên! Độ chính xác tổng thể `EAR` tăng từ **91.70% lên 93.23%**.
  - Nhận diện ngáp (`Yawn`): Tăng từ **92.5% lên 98.4% (+5.9%)**, độ chính xác tổng thể `MAR` tăng từ **95.90% lên 97.23%**.
- **Hạn chế mà tác giả tự thừa nhận ở Mục IV-A (Trang 4):**
  - Nếu trong 5 giây Calibration đầu tiên mà tài xế vô tình chớp mắt nhiều hoặc ngáp, giá trị trung bình $\overline{\text{EAR}}_{\text{cal}}$ sẽ bị kéo tụt xuống, làm hỏng ngưỡng $75\%$!
  - Hệ thống mới chỉ phân loại trạng thái từng khung hình/đoạn ngắn mà chưa mô hình hóa chuỗi động học chớp mắt dài hạn để bắt trạng thái `Low Vigilant`.

#### C. Nhóm 05 lấy được gì từ cặp bài báo này?
- Công thức ngưỡng tỷ lệ $\text{EAR}_{\text{thresh}} = 0.75 \times \overline{\text{EAR}}_{\text{cal}}$ của Ersoy et al. (2026) có thể dùng để cải tiến trực tiếp bước tìm ngưỡng `THR` trong `Algorithm 1 (Blink Retrieval)` của Ghoddoosian (vốn đang gán cứng $\text{THR} = 0.6 \max(x) + 0.4 \min(x)$, rất dễ bị nhiễu bởi 1 điểm cực đại/cực tiểu dị biệt!).

---

### BÀI BÁO #5: Anshuman Gaikwad (Tháng 10/2026) & FEM-PDNet (Tháng 10/2026)
- **Tiêu đề:** *Personalized Temporal Fatigue Analysis and Adaptive Risk Scoring for Camera-Based Driver Monitoring: Prototype and Evaluation Framework*
- **Tác giả:** Anshuman Gaikwad.
- **Mã định danh / Link:** Research Square Preprint `doi:10.21203/rs.3.rs-11416808/v1` (Công bố ngày 20/10/2026) — https://doi.org/10.21203/rs.3.rs-11416808/v1
- **Bài song hành:** *FEM-PDNet: Profile-Driven Adaptive Calibration* (MDPI *Electronics*, Vol. 15, Issue 20, 4838, Tháng 10/2026 — `doi:10.3390/electronics15204838`).
- **Trạng thái đọc:** **[ĐÃ ĐỌC TOÀN VĂN 100% - 9 trang, 780 dòng văn bản]**

#### A. Tại sao việc đọc Toàn văn (Full-Text) bài báo này lại mang lại "Mỏ vàng" cho Nhóm 05?
Nếu chỉ đọc tiêu đề và Abstract của bài báo Gaikwad (Tháng 10/2026), bất kỳ ai cũng sẽ tưởng rằng tác giả đã giải quyết xong toàn bộ bài toán *Personalized Temporal Fatigue Analysis + Calibration + Ablation B0–B3* trên 4 bộ dữ liệu lớn (`NTHU-DDD`, `YawDD`, `DROZY`, `UTA-RLDD`).

**NHƯNG khi đọc toàn văn đến Mục VII-D (Trang 7, dòng 573–585), chúng tôi phát hiện sự thật bất ngờ:**
> *"D. Placeholders for Real Benchmark Results: Quantitative tables for NTHU-DDD, YawDD, DROZY, and UTA-RLDD are not yet available: those runs have not been performed. The synthetic trace results in Section VII-A validate pipeline mechanics only; they do not substitute for evaluation on real driver video."*
*(Tạm dịch: "D. Chỗ trống giữ chỗ cho kết quả Benchmark thực tế: Các bảng định lượng cho NTHU-DDD, YawDD, DROZY và UTA-RLDD hiện chưa có: các lượt chạy đó chưa được thực hiện. Kết quả trên chuỗi dữ liệu giả lập ở Mục VII-A chỉ xác nhận cơ chế hoạt động của pipeline chứ không thay thế cho việc đánh giá trên video tài xế thật.")*

👉 **Ý nghĩa chiến lược cho Nhóm 05:** Bài báo này đã xây dựng sẵn một **khung lý thuyết toán học và kịch bản thí nghiệm Ablation (`B0–B3`) cực kỳ bài bản**, nhưng tác giả mới chỉ chạy thử trên **9 chuỗi số giả lập dài 210 giây (Synthetic Gaussian traces)**! Bằng việc kế thừa hệ thống công thức và thiết kế Ablation `B0–B3` này rồi **chạy thực nghiệm thật 100% trên 180 video của tập dữ liệu UTA-RLDD**, đồ án của Nhóm 05 sẽ trở thành công trình thực nghiệm hoàn chỉnh đầu tiên lấp đầy khoảng trống mà bài báo tháng 10/2026 này để lại!

#### B. Hệ thống Công thức Toán học & Thiết kế Ablation `B0–B3` từ Toàn văn (Mục III–VI, Trang 2–6)
1. **Hiệu chuẩn cá nhân hóa 60 giây có Cổng kiểm soát chất lượng (Quality-Gated Calibration):**
   - Chỉ thu thập các khung hình đạt độ tự tin mốc mặt $q_t \ge q_{\min}$ (với $q_{\min} = 0.7$) trong khoảng thời gian hiệu chuẩn $T_{\text{cal}} = 60\text{ s}$ để tính trung bình và độ lệch chuẩn cá nhân cho `EAR` ($\mu_e, \sigma_e$), tần suất chớp mắt ($\mu_b, \sigma_b$), `MAR` ($\mu_m, \sigma_m$) và góc cúi đầu `Pitch` ($\mu_p, \sigma_p$).
   - Ngưỡng nhắm mắt cá nhân hóa thích nghi theo độ lệch chuẩn:
     $$\theta_e = \mu_e - k_e \sigma_e \quad (\text{với } k_e = 2.0)$$
   - Độ lệch chuẩn hóa Z-score cho từng tín hiệu ở thời điểm $t$:
     $$z_x(t) = \frac{x(t) - \mu_x}{\sigma_x + \epsilon}$$
2. **Tích hợp Điểm rủi ro liên tục $R(t) \in [0, 100]$ trên cửa sổ trượt $W = 30\text{ s}$:**
   - Tính $\text{PERCLOS}_W(t)$ dựa trên ngưỡng cá nhân $\theta_e$:
     $$\text{PERCLOS}_W(t) = \frac{1}{|W|} \sum_{\tau \in W} \mathbb{I}\big(\text{EAR}(\tau) < \theta_e\big)$$
   - Điểm rủi ro thô là tổ hợp tuyến tính có trọng số:
     $$R_{\text{raw}}(t) = 100 \times \text{clip}\Big(0.50 \cdot S_{\text{PERCLOS}}(t) + 0.20 \cdot S_{\text{blink}}(t) + 0.15 \cdot S_{\text{yawn}}(t) + 0.15 \cdot S_{\text{pitch}}(t),\ 0,\ 1\Big)$$
   - Làm mượt bằng trung bình trượt hàm mũ (**EMA**) với hệ số $\lambda = 0.3$:
     $$R(t) = \lambda R_{\text{raw}}(t) + (1 - \lambda) R(t-1)$$
   - **Bộ đếm bền bỉ chống báo động giả (Persistence Timer $T_p = 3\text{ s}$):** Chỉ phát cảnh báo khi $R(t)$ vượt ngưỡng liên tục trong ít nhất $T_p = 3\text{ giây}$ và chất lượng mốc mặt $q_t \ge 0.7$.
3. **Thiết kế 4 Kịch bản Ablation (`B0` $\rightarrow$ `B3` - Mục VI-B, Trang 6) mà Nhóm 05 có thể áp dụng ngay:**
   - **`B0` (Fixed-Threshold / Uncalibrated Baseline):** Dùng ngưỡng/đặc trưng cố định chung cho mọi tài xế, không có Calibration cá nhân hóa, không làm mượt thời gian.
   - **`B1` (Standard Calibrated Baseline):** Có Calibration chuẩn (dùng đoạn đầu tỉnh táo chuẩn như Ghoddoosian 2019 / Sobirov 2026).
   - **`B2` (Faulty / Corrupted Calibration vs. AI-Assisted Calibration):** Kiểm thử khi giai đoạn đầu bị nhiễu (tài xế mệt sẵn / chớp mắt bất thường) để so sánh Calibration ngây thơ (Naive Calibration) với Calibration thông minh có lọc nhiễu (AI-Assisted / GMM / Quality-Gated Calibration).
   - **`B3` (Full System: AI-Assisted Calibration + Physical-Time Kinematics + Adaptive Temporal Window):** Kết hợp toàn bộ cải tiến (Gap A + Gap B + Gap C).

---

## 3. Sơ Đồ Kết Nối Top 5 Bài Báo Vào Đề Tài Của Nhóm 05

```mermaid
flowchart TD
    P0["Bài gốc: Ghoddoosian et al. (CVPRW 2019)<br/>UTA-RLDD 3-class, 5-fold CV: 65.2% VA, 54.68% BSA"]
    
    P0 --> GapA["GAP A: Calibration giả định 1/3 đầu luôn Alert"]
    P0 --> GapB["GAP B: Đặc trưng tính theo Frame & thiếu pha đóng mắt"]
    P0 --> GapC["GAP C: Cửa sổ cố định T=30 blinks (trễ 2-3 phút)"]

    GapA --> S1["Sobirov & Hamidov (07/2026)<br/>Chứng minh Calibration +3.9% Acc<br/>nhưng thừa nhận hỏng nếu đầu giờ đã mệt"]
    GapA --> S4["Ersoy et al. (04/2026) & Gaikwad (10/2026)<br/>Ngưỡng cá nhân 75% EAR / Z-score k-sigma<br/>+ Kịch bản Ablation B0-B3"]

    GapB --> S2["Wolter et al. (11/2025)<br/>Phát hiện 169/182 video UTA-RLDD bị VFR (12-30 Hz)<br/>Lọc Gaussian theo FPS + 9 đặc trưng đóng/mở (ms)"]

    GapC --> S3["Xie & Xiao (06/2026)<br/>Cửa sổ thích nghi CDATW (5s-30s) theo độ tự tin<br/>Giảm 35.2% báo động giả (FAR)"]

    S1 & S4 & S2 & S3 --> G05["ĐỀ TÀI NHÓM 05 (SC_25A01_Group05)<br/>Tích hợp AI-Assisted Calibration + Động học chuẩn hóa ms/FPS<br/>+ Cửa sổ thích nghi trên tập UTA-RLDD thực tế"]
```

