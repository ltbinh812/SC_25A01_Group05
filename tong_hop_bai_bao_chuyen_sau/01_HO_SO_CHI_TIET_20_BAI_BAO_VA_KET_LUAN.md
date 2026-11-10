# HỒ SƠ TRA CỨU NHANH & CHI TIẾT TOÀN BỘ 20 BÀI BÁO (12 BÀI CHÍNH TRONG `pdf_bai_bao` + 8 BÀI PHỤ TRONG `luu_tru_phu`)

> **Mục đích tài liệu này:** Giúp bạn tra cứu nhanh nhưng đầy đủ chi tiết từng bài báo đã tải về máy (từ **Bài 1 đến Bài 12** trong thư mục [`pdf_bai_bao/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao) và từ **Bài 13 đến Bài 20** trong thư mục [`luu_tru_phu/pdf_phu_tham_khao/`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao)).
> Mỗi bài đều được trình bày theo 5 mục cố định:
> 1. **Thông tin định danh:** Tên bài báo, Tác giả, Năm, Nơi công bố, Mã ký hiệu trong `SC102` (nếu có), Link gốc & Link PDF trong máy.
> 2. **Tóm tắt phương pháp & Công thức / Thông số kỹ thuật:** Họ dùng dữ liệu gì, tiền xử lý ra sao, trích xuất đặc trưng nào, công thức toán học và kiến trúc mô hình là gì.
> 3. **Kết quả thực nghiệm công bố:** Các con số chính trong các bảng (Tables) của bài báo.
> 4. **Phát hiện đắt giá khi đọc toàn văn (Full-Text Audit):** Những sự thật ẩn ở mục *Preprocessing*, *Ablation Study* hoặc *Limitations* mà chỉ đọc kỹ toàn văn mới thấy.
> 5. **KẾT LUẬN & Cách Nhóm 05 sử dụng bài báo này:** Dùng để làm gì (cải tiến code `Gap A/B/C`, giải thích kết quả `R0–R2`, hay làm vũ khí phản biện Hội đồng).

---

## BẢNG MỤC LỤC TRA CỨU NHANH 20 BÀI BÁO

| STT | File PDF trong máy | Năm | Tác giả / Mã SC102 | Chủ đề cốt lõi | Vai trò với Nhóm 05 |
| :---: | :--- | :---: | :--- | :--- | :--- |
| **01** | [`P0_Ghoddoosian_2019.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P0_Ghoddoosian_2019.pdf) | 2019 | Ghoddoosian et al. (`P1`) | Bộ dữ liệu UTA-RLDD, 4 đặc trưng chớp mắt, Calibration 1/3 `Alert`, mạng HM-LSTM. | **Baseline gốc (`R0/R1/R2`)** & nguồn gốc 3 lỗ hổng `Gap A, B, C`. |
| **02** | [`P1_ELA_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P1_ELA_2025.pdf) | 11/2025 | Wolter et al. (`A1`) | Góc mí mắt 3D (`ELA`), lọc Gaussian theo FPS, 9 đặc trưng giây (`s`), phát hiện lỗi VFR trên UTA-RLDD. | **Giải quyết `Gap B` (FPS)** & **Bảo vệ kết quả `R1` (`VA = 52.5%` 3-class vs `80.4%` 2-class)**. |
| **03** | [`P8_Akin_Kalkan_2024_Blink_Behavior.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P8_Akin_Kalkan_2024_Blink_Behavior.pdf) | 07/2024 | Akin & Kalkan (`A12`) | Chuẩn hóa 2 phút $\text{EAR}_{ref} \pm 20\%$ & Bảng Ablation pha đóng (`closing`), mở (`reopening`), độ lệch (`diff`). | **Bằng chứng Ablation cho `Gap B`**: Thêm pha đóng/mở giúp tăng **+5.15% đến +9.64%** trên UTA-RLDD. |
| **04** | [`B_Webcam_MediaPipe_Eye_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Webcam_MediaPipe_Eye_2025.pdf) | 11/2025 | Goswami & Waghmare | MediaPipe + Random Forest trên UTA-RLDD; đánh giá độ quan trọng đặc trưng (Feature Importance). | **Giải thích thông số `Gap B`**: `EAR Variance` (41%), `Duration` (30%), `PERCLOS` (25%), còn `Frequency` chỉ **4%**. |
| **05** | [`P3_Zenodo_2026_Best_Vol. 3 No. 7. 2026_591-600.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P3_Zenodo_2026_Best_Vol.%203%20No.%207.%202026_591-600.pdf) | 07/2026 | Sobirov & Hamidov | Bi-GRU, Calibration 60s đầu (+3.9%), đối chứng Random Split vs Subject-Independent Split (-9.4% đến -11.4%). | **Giải quyết `Gap A`** (EAR tỉnh lệch từ `0.198–0.305` & lời thú nhận ở trang 8 về lỗi khi tài xế mệt từ đầu). |
| **06** | [`P4_Personalized_EAR_MAR_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P4_Personalized_EAR_MAR_2026.pdf) | 04/2026 | Ersoy et al. (kế thừa `P2` Xu 2025) | Hiệu chuẩn 5s đầu đặt ngưỡng cá nhân hóa $\tau_{\text{EAR}} = 0.75\overline{\text{EAR}}$, $\tau_{\text{MAR}} = 1.40\overline{\text{MAR}}$. | **Công thức tính `PERCLOS` cá nhân hóa (`Gap A + B`)** & làm rõ bài Xu 2025 chỉ chạy 2 lớp. |
| **07** | [`P5_ResearchSquare_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P5_ResearchSquare_2026.pdf) | 10/2026 | Anshuman Gaikwad (`A2`) | Chuẩn hóa Z-score 60s, điểm rủi ro $R(t)$, cổng chất lượng $q_{\min}=0.7$, khung Ablation `B0–B3`. | **Khung thực nghiệm Ablation `B0–B3` cho `Gap A`** (Tác giả mới chạy giả lập, chưa chạy thật trên UTA-RLDD). |
| **08** | [`P2_CDATW_Frontiers_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P2_CDATW_Frontiers_2026.pdf) | 06/2026 | Xie & Xiao (`A13`) | Cửa sổ thời gian thích nghi điều khiển bằng độ tự tin (`CDATW` co giãn 5s–30s), giảm 35.2% báo động giả (`FAR`). | **Giải quyết trực tiếp `Gap C` (Độ trễ quyết định)** bằng công thức co giãn cửa sổ theo độ tự tin. |
| **09** | [`P6_AHFE_2026_Blendshapes_BiLSTM.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P6_AHFE_2026_Blendshapes_BiLSTM.pdf) | 07/2026 | Chavan et al. (`A5`) | 7 MediaPipe Blendshapes + Calibration 2 phút + Dual-Attention Hierarchical BiLSTM trên UTA-RLDD (`88.89%`). | **Vũ khí phản biện số 1**: Chứng minh `88.89%` là do đặt ngưỡng `0.35` gộp về **2 lớp (`Safe` vs `Unsafe`)** & vạch trần Xu 2025 lọc mẫu. |
| **10** | [`B_YawDD_Plus_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_YawDD_Plus_2025.pdf) | 12/2025 | Mujtaba et al. (*ICIP 2026*) | Gán nhãn lại cấp độ frame, chứng minh video buồn ngủ/ngáp có tới **75%–92.6% frame bình thường**. | **Giải thích thông số `R0/R1`**: Tại sao `BSA` luôn thấp hơn `VA` ~10% và tại sao `Low Vigilant` hay nhầm sang `Alert`. |
| **11** | [`B_Sensors_2025_Essahraui_FullText.txt`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Sensors_2025_Essahraui_FullText.txt) | 02/2025 | Essahraui et al. | Chia ngẫu nhiên theo frame trên UTA-RLDD khiến `1-NN` đạt **98.89%** và `CNN` đạt **99.97%**. | **Bằng chứng kinh điển vạch trần Frame-Level Data Leakage** (học vẹt khuôn mặt) của các bài 99%. |
| **12** | [`B_Nakagama_2025_Reproducibility_Leakage.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Nakagama_2025_Reproducibility_Leakage.pdf) | 06/2025 | Nakagama et al. (*IEEE IV*) | Tái lập các mô hình công bố 91%–98% trên tập dữ liệu chuẩn mà không rò rỉ dữ liệu. | **Bảo vệ trực tiếp kết quả `R1` (`53.7%`) so với `R0` (`64.9%`)**: Khi train lại trung thực, các mô hình đều rơi về **51%–70%**. |
| **13** | [`B_Survey_AI_Review_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_Survey_AI_Review_2026.pdf) | 05/2026 | Hassan et al. (`A15`) | Bài tổng quan hệ thống PRISMA Q1 (83 trang) về các hệ thống phát hiện buồn ngủ 2018–2025. | Định nghĩa chuẩn bộ thước đo đánh giá (`PR-AUC`, `TPR@FAR`, `ECE`, `Latency`, `LOSO CI`). |
| **14** | [`P7_Leakage_Resistant_Calibrated_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/P7_Leakage_Resistant_Calibrated_2026.pdf) | 08/2026 | Theivadas et al. | Giao thức chia 3 tập độc lập `I_fit`, `I_cal`, `I_test`, hiệu chuẩn xác suất Platt Scaling và chọn ngưỡng theo `MCC`. | Giải pháp chống lỗi chọn checkpoint / chọn ngưỡng trực tiếp trên tập Test (lỗi của code 2019). |
| **15** | [`B_TTA_CalibrationFree_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_TTA_CalibrationFree_2025.pdf) | 11/2025 | Jang et al. | Thích nghi thời gian thực (Selective Test-Time Adaptation - TTA) không cần giai đoạn Calibration riêng. | Chứng minh cập nhật trung bình trượt ngây thơ khi tài xế đang buồn ngủ làm sập F1 từ `67.23%` xuống `6.46%`. |
| **16** | [`B_UL_DD_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_UL_DD_2026.pdf) | 01/2026 | Bodaghi et al. (*Nature Sci Data*) | Bộ dữ liệu mới UL-DD quay 40 phút liên tục, chấm KSS mỗi 4 phút (khắc phục lỗi 1 nhãn cho cả video 10 phút). | Chứng minh 5-fold CV chỉ dùng hình ảnh (Unimodal Visual) có trần thực tế là **52%–68%**. |
| **17** | [`B_LiteFat_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_LiteFat_2025.pdf) | 08/2025 | Ren et al. | Mạng đồ thị không-thời gian (ST-GNN) + Mạng tích chập nhân quả giãn nở (Dilated Causal TCN) siêu nhẹ (0.296M params). | Gợi ý kiến trúc `Dilated Causal TCN` nhẹ hơn và hội tụ ổn định hơn `HM-LSTM`. |
| **18** | [`B_LightVTD_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_LightVTD_2026.pdf) | 03/2026 | *Nature Sci Reports* | Tiền xử lý cân bằng sáng thích nghi `CLAHE` + Swin ViT trên UTA-RLDD (`97.6%`). | Dùng kỹ thuật `CLAHE` (+2.4%) để chống tối/ngược sáng; đồng thời là ví dụ lỗi chia 11,787 frame 2 lớp. |
| **19** | [`B_FastKAN_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_FastKAN_2025.pdf) | 11/2025 | Essahraui et al. (*PLOS ONE*) | MobileNetV2 + FastKAN trên các frame cắt từ UTA-RLDD (`99.94%`), thử nghiệm nén lượng tử hóa 8-bit (`PTQ`). | Bằng chứng mô hình học vẹt biên quyết định sắc nhọn: nén 8-bit `PTQ` làm accuracy sập từ **99.94% xuống 48.86%**. |
| **20** | [`B_ViT_SciRep_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_ViT_SciRep_2025.pdf) | 05/2025 | Hassan et al. (*Nature Sci Reports*) | Huấn luyện Swin Transformer / ViT trên từng bức ảnh vùng mắt tĩnh lẻ tẻ (Static Eye ROI). | Phản biện hướng tiếp cận ảnh tĩnh: không thể phân biệt chớp mắt bình thường với nhắm mắt ngủ gật nếu thiếu chuỗi thời gian. |

---

# PHẦN I: CHI TIẾT 12 BÀI BÁO CỐT LÕI & PHẢN BIỆN TRONG THƯ MỤC `pdf_bai_bao/`

---

## BÀI 01: Bài Báo Gốc UTA-RLDD & Mạng HM-LSTM (Ghoddoosian et al., 2019)

1. **Thông tin định danh:**
   - **Tên bài báo:** *A Realistic Dataset and Baseline Temporal Model for Early Drowsiness Detection*
   - **Tác giả & Năm:** Reza Ghoddoosian, Marnim Galib, Vassilis Athitsos (ĐH Texas tại Arlington — *IEEE/CVF CVPRW 2019*).
   - **Mã trong SC102:** `P1` (Baseline chính của đồ án).
   - **Link gốc:** https://arxiv.org/abs/1904.07312
   - **File trong máy:** [`P0_Ghoddoosian_2019.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P0_Ghoddoosian_2019.pdf)
2. **Tóm tắt phương pháp & Công thức kỹ thuật:**
   - **Dữ liệu UTA-RLDD:** 60 người, mỗi người 3 video dài ~10 phút tương ứng 3 lớp: `Alert (0)`, `Low Vigilant (5)`, `Drowsy (10)`. Chia thành 5 folds độc lập người lái (mỗi fold 12 người = 36 video).
   - **Phát hiện chớp mắt (`Algorithm 1` ở Supplementary Trang 11):** Tính `EAR` mỗi frame qua `dlib`, đưa chuỗi 13 frame qua SVM của Soukupová & Čech (2016), sau đó hậu xử lý bằng ngưỡng thích nghi $\text{THR} = 0.6\max(x) + 0.4\min(x)$ và tìm điểm đổi dấu đạo hàm bậc 1 $\dot{x}[n]\cdot\dot{x}[n+1] < 0$ để xác định `start`, `bottom`, `end` của mỗi nhịp chớp mắt.
   - **4 Đặc trưng mỗi lần chớp mắt $i$:**
     - $\text{Duration}_i = \text{end}_i - \text{start}_i + 1$ *(tính bằng số frame)*
     - $\text{Amplitude}_i = \frac{\text{EAR}[\text{start}_i] - 2\text{EAR}[\text{bottom}_i] + \text{EAR}[\text{end}_i]}{2}$
     - $\text{Opening Velocity}_i = \frac{\text{EAR}[\text{end}_i] - \text{EAR}[\text{bottom}_i]}{\text{end}_i - \text{bottom}_i}$ *(tính bằng EAR/frame)*
     - $\text{Frequency}_i = 100 \times \frac{\text{Số lần chớp mắt tính đến } i}{\text{Tổng số frame tính đến } \text{end}_i}$
   - **Chuẩn hóa cá nhân (Công thức 6):** Dùng **1/3 số lần chớp mắt đầu tiên của video `Alert`** để tính $\mu_{n,m}, \sigma_{n,m}$ và chuẩn hóa Z-score cho 2/3 phần còn lại của video `Alert` cùng toàn bộ video `Low Vigilant` và `Drowsy` của người đó.
   - **Mô hình & Loss:** Cắt cửa sổ trượt $T = 30$ lần chớp mắt (`stride = 2`), đưa vào mạng 4-layer HM-LSTM ($L = 32$ hidden units/tầng), hàm loss hồi quy vùng đệm $\text{Loss} = \frac{1}{N}\sum \max(0, |\text{out}_i - t_i|^2 - \Delta)$ với $\Delta = 1.253$. Chia ngưỡng dự đoán $[0, 3.3) \to 0$; $[3.3, 6.6] \to 5$; $(6.6, 10] \to 10$ và bỏ phiếu đa số (Majority Voting) trên toàn video.
3. **Kết quả thực nghiệm công bố:**
   - **HM-LSTM:** `BSA = 54.0%` (trong code đạt `54.68%`), `VA = 65.2%`, `BSRE = 1.90`, `VRE = 1.14`.
   - **1-layer LSTM thường:** `BSA = 50.8%`, `VA = 61.4%`.
   - **Con người chấm (20 sinh viên):** `VA = 57.8%`, `VRE = 2.01`.
4. **Phát hiện đắt giá khi đọc toàn văn:**
   - Công thức (10) trong bài in nhầm $\Delta = 1.58$, trong khi code thực tế dùng `delta = 1.253` ($\sqrt{1.58} \approx 1.257$).
   - Code huấn luyện không có tập Validation riêng mà chấm trực tiếp trên tập Test ở mỗi epoch và không cố định `random seed`.
5. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Đây là bài báo đặt nền móng chuẩn mực nhất cho bài toán **Phát hiện sớm 3 lớp độc lập người lái**, nhưng để lại 3 lỗ hổng lớn: **(Gap A)** Giả định biết trước nhãn `Alert` để lấy 1/3 đầu làm Calibration; **(Gap B)** Tính thời lượng và vận tốc theo số `frame` trên bộ video có FPS biến thiên, đồng thời thiếu pha nhắm mắt và `PERCLOS`; **(Gap C)** Đòi hỏi cửa sổ cố định 30 lần chớp mắt (trễ 2–3 phút).

---

## BÀI 02: Góc Mí Mắt 3D (`ELA`) & Phát Hiện Lỗi Biến Thiên FPS Trên UTA-RLDD (Wolter et al., 11/2025)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Eyelid Angle for Blink Detection and Drowsiness Characterization*
   - **Tác giả & Năm:** Jan P. Wolter, Julie Stephany Berrio Perez, Mao Shan (University of Sydney, Úc — Tháng 11/2025).
   - **Mã trong SC102:** `A1`.
   - **Link gốc:** https://arxiv.org/abs/2511.19519
   - **File trong máy:** [`P1_ELA_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P1_ELA_2025.pdf)
2. **Tóm tắt phương pháp & Công thức kỹ thuật:**
   - Thay `EAR` 2D bằng góc mở mí mắt 3D **Eyelid Angle (`ELA`, đơn vị độ $^\circ$)** dựng từ các mặt phẳng giải phẫu mắt của MediaPipe Face Mesh (478 điểm 3D).
   - Lọc mượt tín hiệu theo tốc độ khung hình thực tế: dùng bộ lọc Gaussian với $\sigma = \text{FPS} / 30$.
   - Phát hiện cực tiểu nhịp chớp mắt bằng ngưỡng độ nổi (Prominence $P_{\min} = 5^\circ$) và trích xuất **9 đặc trưng vật lý theo đơn vị giây (`s`)**: thời gian đóng mắt $d_1$, thời gian nhắm kín $d_2$, thời gian mở mắt $d_3$, tổng thời gian $D = d_1+d_2+d_3$, biên độ đóng/mở $a_1, a_2$ ($^\circ$), vận tốc góc đóng/mở cực đại $v_1, v_2$ ($^\circ/\text{s}$), và tần suất $f_i$ (blinks/phút).
3. **Kết quả thực nghiệm công bố:**
   - Khi đổi FPS từ 30 Hz xuống 15 Hz, phương pháp tính theo `frame` của Ghoddoosian 2019 bị sai lệch `Closing Duration` tới **32%**, làm độ chính xác phân loại buồn ngủ trên tập mô phỏng rơi từ **98% xuống 69%**, trong khi phương pháp tính theo giây (`s`) của Wolter giữ nguyên **98%**.
   - **Trên tập UTA-RLDD (Bảng IV, Trang 7 - chạy đúng 5-fold CV với HM-LSTM $T=30$):**
     - **Bài toán 3 lớp (`Alert`, `Low Vigilant`, `Drowsy`):** `BSA = 46.8%`, **`VA = 52.5%`**, `BSRE = 2.66`, `VRE = 2.13`.
     - **Bài toán 2 lớp (`Alert` vs. `Drowsy`):** `BSA = 69.5%`, **`VA = 80.4%`**, `BSRE = 2.66`, `VRE = 2.02`.
4. **Phát hiện đắt giá khi đọc toàn văn:**
   - **Mục IV-B (Trang 5):** Tác giả quét toàn bộ 182 video của UTA-RLDD và phát hiện **169 / 182 video bị biến thiên tốc độ khung hình (Variable Frame Rate - VFR, từ 12 Hz đến 30 Hz)**!
   - Con số `BSA = 46.8%`, `VA = 52.5%` khi nhóm ĐH Sydney tự train lại mạng HM-LSTM 3-class từ đầu trùng khớp gần như tuyệt đối với kết quả `R1` trong [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf) của Tiến (`BSA = 46.8%`, `VA = 53.7%`)!
5. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Đây là bài báo **quan trọng số 1** để nhóm bạn vừa **bảo vệ kết quả `R1 = 53.7%`** trước Hội đồng, vừa làm **căn cứ khoa học trực tiếp cho `Gap B`** (bắt buộc phải chia đặc trưng thời lượng/vận tốc cho FPS thực tế của từng video và tách riêng pha đóng mắt $d_1, v_1$ khỏi pha mở mắt $d_3, v_2$).

---

## BÀI 03: Chứng Minh Ablation Động Học Pha Đóng / Mở Mắt Trên UTA-RLDD (Akin & Kalkan, 07/2024)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Exploring Blink Behavior carefully for Drowsiness Detection*
   - **Tác giả & Năm:** Oguzhan Akin, Sinan Kalkan (Middle East Technical University - METU, Thổ Nhĩ Kỳ — Tháng 7/2024).
   - **Mã trong SC102:** `A12`.
   - **Link gốc:** https://arxiv.org/abs/2407.02222
   - **File trong máy:** [`P8_Akin_Kalkan_2024_Blink_Behavior.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P8_Akin_Kalkan_2024_Blink_Behavior.pdf)
2. **Tóm tắt phương pháp & Công thức kỹ thuật:**
   - Chạy trên tập **UTA-RLDD** (dùng MediaPipe Face Mesh trích xuất `EAR` cho 21 đối tượng có góc mặt thẳng).
   - **Chuẩn hóa cá nhân 2 phút đầu (`Gap A`):** Lấy 2 phút đầu của video `Alert` tính $\text{EAR}_{ref}$, đặt 2 ngưỡng trễ (hysteresis) $\pm 20\%$: $\text{THR}_{high} = 1.20\,\text{EAR}_{ref}$, $\text{THR}_{low} = 0.80\,\text{EAR}_{ref}$.
   - **So sánh 2 bộ đặc trưng chớp mắt:**
     - `blink_set1` (3 đặc trưng cơ bản): Tổng thời lượng chớp mắt (`duration`), Khoảng cách giữa 2 nhịp chớp (`interval`), Tổng số nhịp chớp (`total_blinks`).
     - `blink_set2` (6 đặc trưng chi tiết): Thêm **Thời lượng pha nhắm mắt (`closing`)**, **Thời lượng pha mở mắt (`reopening`)**, và **Hiệu số bất đối xứng (`diff = reopening - closing`)**.
3. **Kết quả thực nghiệm công bố (Bảng 2, Trang 3 - Ablation trên UTA-RLDD):**
   - `SVM`: từ `68.00%` (`blink_set1`) $\rightarrow$ **`77.64%`** (`blink_set2`) — **tăng +9.64%**.
   - `Decision Tree`: từ `64.61%` $\rightarrow$ **`72.51%`** — **tăng +7.90%**.
   - `kNN`: từ `68.26%` $\rightarrow$ **`75.67%`** — **tăng +7.41%**.
   - `Random Forest`: từ `73.79%` $\rightarrow$ **`78.94%`** — **tăng +5.15%**.
4. **Phát hiện đắt giá khi đọc toàn văn:**
   - Ở Bảng 1 (Trang 2), tác giả vẫn tính `closing`, `reopening`, `diff` theo **số khung hình (`#frames`)** chứ chưa chia cho FPS để quy về mili-giây (`ms`), và chỉ mới chạy phân loại 2 lớp (`0` vs `10`).
5. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Cung cấp bảng số liệu đối chứng (Ablation) trực tiếp trên UTA-RLDD chứng minh rằng: việc Ghoddoosian 2019 gộp chung `Total Duration` và bỏ qua pha nhắm mắt (`closing`) cũng như độ bất đối xứng (`reopening - closing`) đã làm đánh mất từ **5.15% đến 9.64% độ chính xác**. Nhóm 05 sẽ kết hợp bài này với Bài 02 (Wolter 2025) để tính các đại lượng này theo đơn vị `ms` chuẩn FPS!

---

## BÀI 04: Định Lượng Độ Quan Trọng Của Các Đặc Trưng Mắt Trên UTA-RLDD (Goswami & Waghmare, 11/2025)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Webcam-Based Driver Drowsiness Detection Using MediaPipe FaceMesh Eye Features*
   - **Tác giả & Năm:** K. Goswami, L. M. Waghmare (IIT Roorkee, Ấn Độ — Tháng 11/2025).
   - **Link gốc:** https://doi.org/10.21203/rs.3.rs-8036038/v1
   - **File trong máy:** [`B_Webcam_MediaPipe_Eye_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Webcam_MediaPipe_Eye_2025.pdf)
2. **Tóm tắt phương pháp & Công thức kỹ thuật:**
   - Dùng MediaPipe FaceMesh trích xuất 6 điểm mỗi mắt trên tập **UTA-RLDD**.
   - Trong mỗi cửa sổ 5 giây, tính 4 đặc trưng: `PERCLOS` (tỷ lệ frame có $\text{EAR} < 0.21$), `Blink Rate` (số lần chớp mắt/phút), `Avg_Blink_Duration` (thời lượng chớp mắt trung bình), và **`EAR_Variance`** ($\sigma^2_{\text{EAR}} = \frac{1}{N}\sum (\text{EAR}_t - \mu_{\text{EAR}})^2$). Phân loại bằng Random Forest (100 cây).
3. **Kết quả thực nghiệm công bố (Mục 5.2, Trang 6 - Feature Importance trên UTA-RLDD):**
   - **`EAR_Variance` (Phương sai độ mở mắt): `0.41` (41%)** — Đóng góp lớn nhất!
   - **`Avg_Blink_Duration` (Thời lượng chớp mắt): `0.30` (30%)** — Đóng góp thứ hai.
   - **`PERCLOS` (Tỷ lệ thời gian nhắm mắt): `0.25` (25%)** — Đóng góp thứ ba.
   - **`Blink_Rate` (Tần suất chớp mắt / Frequency): `0.04` (4%)** — Thấp nhất, gần như nhiễu!
4. **Phát hiện đắt giá khi đọc toàn văn:**
   - Chỉ ra chính xác điểm yếu trong 4 đặc trưng của bài báo 2019: Ghoddoosian 2019 đưa `Frequency` (chỉ có 4% giá trị phân loại) vào làm 1 trong 4 đặc trưng chính, nhưng lại không có `EAR Variance` (41%) và `PERCLOS` (25%).
5. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Dùng trực tiếp con số `41% - 30% - 25% - 4%` này để giải thích trong báo cáo vì sao Nhóm 05 quyết định bổ sung `PERCLOS` và độ biến thiên mở mắt vào bộ đặc trưng chớp mắt (`Gap B`).

---

## BÀI 05: Định Lượng Calibration 60s, Sụt Giảm Subject-Independent & Lời Thú Nhận Trang 8 (Sobirov & Hamidov, 07/2026)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Deep Learning for Real-Time Driver Drowsiness Detection from Facial Video: Architecture Comparison, Temporal Modeling, and Edge Deployment*
   - **Tác giả & Năm:** Jakhongir Sobirov, Dilshod Hamidov (Tashkent University of Information Technologies — Tháng 7/2026).
   - **Link gốc:** https://doi.org/10.5281/zenodo.21524614
   - **File trong máy:** [`P3_Zenodo_2026_Best_Vol. 3 No. 7. 2026_591-600.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P3_Zenodo_2026_Best_Vol.%203%20No.%207.%202026_591-600.pdf)
2. **Tóm tắt phương pháp & Công thức kỹ thuật:**
   - Trích xuất 7 đặc trưng hình học mỗi frame từ MediaPipe (`EAR_L`, `EAR_R`, `EAR_mean`, `MAR`, `Pitch`, `Yaw`, `Roll`).
   - **Chuẩn hóa cá nhân 60s đầu (`Per-Driver Calibration`):** Lấy 1800 frames đầu (60s ở 30 fps) tính $\mu_{\text{init}}, \sigma_{\text{init}}$ để chuẩn hóa Z-score cho toàn bộ phiên lái: $\text{EAR}_{\text{norm}}(t) = (\text{EAR}(t) - \mu_{\text{init}})/\sigma_{\text{init}}$.
   - Đưa cửa sổ 90 frames (3s) vào mạng 2-layer Bi-GRU (64 units).
3. **Kết quả thực nghiệm công bố:**
   - **Bảng 1 (Trang 5 - So sánh cách chia dữ liệu):**
     - Nếu chia ngẫu nhiên theo cửa sổ (`Random Window Split`): 1D-CNN đạt `96.1%`, LSTM đạt `97.4%`, Bi-GRU đạt `97.8%`.
     - Khi chia độc lập người lái (`Subject-Independent Split`): 1D-CNN tụt xuống **`84.7%` (-11.4%)**, LSTM tụt xuống **`87.9%` (-9.5%)**, Bi-GRU tụt xuống **`88.4%` (-9.4%)**.
   - **Mục 4.4 (Trang 6 - Hiệu quả Calibration):** Trung vị `EAR` lúc tỉnh táo (`Alert`) của các tài xế khác nhau trải rộng từ **`0.198` đến `0.305`**. Nhờ Calibration 60s đầu, độ chính xác Bi-GRU trên tài xế mới tăng từ **`88.4%` lên `92.3%` (+3.9%)**, giảm độ lệch chuẩn giữa các tài xế từ $\pm 7.8\%$ xuống $\pm 4.1\%$.
4. **Phát hiện đắt giá khi đọc toàn văn:**
   - **Trang 8 (Mục 5.2 - Limitations):** Tác giả thú nhận trực tiếp lỗ hổng của Calibration: *"Calibration assumes the opening minute is alert. That is reasonable for a freshly started trip, not for a driver who is already fatigued at the start, and a deployed system would need a check for that case."*
5. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Cung cấp cả **con số chứng minh tầm quan trọng của Calibration** (`EAR` lệch từ `0.198–0.305`, tăng `+3.9%`), **con số chứng minh tác hại của Data Leakage** (`-9.4% đến -11.4%`), lẫn **lời thú nhận mở đường cho `Gap A`** (kiểm định và xử lý trường hợp tài xế đã mệt ngay từ đầu phiên lái).

---

## BÀI 06: Ngưỡng Cá Nhân Hóa 75% EAR / 140% MAR (Ersoy et al., 04/2026 & Xu et al., 04/2025)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Real-Time Driver Fatigue Detection Using Personalized EAR-MAR Thresholds and Hybrid Deep Features*
   - **Tác giả & Năm:** Ersoy et al. (Tháng 4/2026 — kế thừa trực tiếp bài `P2` của Xu et al., MDPI *Information* 2025, `doi:10.3390/info16040294`).
   - **Mã trong SC102:** Liên kết trực tiếp với `P2`.
   - **Link gốc:** https://arxiv.org/abs/2604.22479
   - **File trong máy:** [`P4_Personalized_EAR_MAR_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P4_Personalized_EAR_MAR_2026.pdf)
2. **Tóm tắt phương pháp & Công thức kỹ thuật:**
   - Thu thập $N = 150\text{ frames}$ đầu tiên (5 giây ở 30 fps) khi tài xế nhìn thẳng để tính trung bình cơ sở $\overline{\text{EAR}}_{\text{calib}}$ và $\overline{\text{MAR}}_{\text{calib}}$.
   - Đặt ngưỡng đóng mắt và ngáp cá nhân hóa theo tỷ lệ:
     $$\tau_{\text{EAR}} = 0.75 \times \overline{\text{EAR}}_{\text{calib}}, \quad \tau_{\text{MAR}} = 1.40 \times \overline{\text{MAR}}_{\text{calib}}$$
   - Kết hợp điểm ngưỡng hình học với xác suất từ mạng MobileNetV2-LSTM để tính `PERCLOS` trong cửa sổ trượt.
3. **Kết quả thực nghiệm công bố:**
   - Giảm tỷ lệ báo động giả trên các tài xế có mắt nhỏ bẩm sinh và đạt `94.2%` trên tập kết hợp YawDD/NTHU-DDD; trích dẫn kết quả của Xu et al. (2025) đạt `86.88%` trên 22 đối tượng UTA-RLDD.
4. **Phát hiện đắt giá khi đọc toàn văn:**
   - Làm sáng tỏ rằng bài Xu et al. (2025) khi thử nghiệm trên UTA-RLDD đã **bỏ hoàn toàn lớp `Low Vigilant`**, chỉ lấy 44 video của 22 người (`Alert` vs `Drowsy`) để phân loại nhị phân.
5. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Nhóm 05 có thể lấy trực tiếp công thức $\tau_{\text{EAR}} = 0.75 \times \overline{\text{EAR}}_{\text{calib}}$ để tính đặc trưng **`PERCLOS` cá nhân hóa** cho từng tài xế trên UTA-RLDD mà không sợ bị lệch do mắt to hay mắt nhỏ (`Gap A + Gap B`).

---

## BÀI 07: Khung Ablation Calibration `B0–B3` & Cổng Chất Lượng (Anshuman Gaikwad, 10/2026)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Calibrated Multi-Cue Driver Drowsiness Detection from Facial Landmarks with Confidence-Gated Temporal Fusion*
   - **Tác giả & Năm:** Anshuman Gaikwad (Manipal Institute of Technology, Ấn Độ — Tháng 10/2026).
   - **Mã trong SC102:** `A2`.
   - **Link gốc:** https://doi.org/10.21203/rs.3.rs-11416808/v1
   - **File trong máy:** [`P5_ResearchSquare_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P5_ResearchSquare_2026.pdf)
2. **Tóm tắt phương pháp & Công thức kỹ thuật:**
   - Chuẩn hóa Z-score cá nhân trong $T_{\text{cal}} = 60\text{s}$ đầu tiên: $z_{\text{EAR}}(t) = \frac{\mu_{\text{EAR}} - \text{EAR}(t)}{\sigma_{\text{EAR}} + \epsilon}$ ($\epsilon = 10^{-3}$).
   - Đặt cổng kiểm soát chất lượng khung hình $q(t) \ge q_{\min} = 0.7$ (nếu mặt bị che khuất hoặc quay đi quá góc cho phép thì đóng băng việc cập nhật điểm rủi ro để tránh báo động giả).
   - Thiết kế **4 kịch bản Ablation chuẩn mực (`B0–B3`, Mục 4.3, Trang 6)**:
     - `B0`: Ngưỡng cố định toàn cục (Không có Calibration).
     - `B1`: Có Calibration cá nhân hóa theo người lái.
     - `B2`: Có Calibration + Làm mượt chuỗi thời gian.
     - `B3`: Đầy đủ Calibration + Confidence Gate + Persistence Timer ($T_p = 3\text{s}$).
3. **Kết quả thực nghiệm công bố:**
   - Trên tập dữ liệu mô phỏng, `B3` đạt `F1 = 0.91` so với `B0` đạt `F1 = 0.68`.
4. **Phát hiện đắt giá khi đọc toàn văn (Mục 5.2, Trang 7):**
   - Tác giả thú nhận ở Trang 7: *"Public-dataset execution on NTHU-DDD and UTA-RLDD was not performed in this workspace because those datasets are not bundled here."* Toàn bộ số liệu trong bài chỉ chạy trên **9 chuỗi tín hiệu giả lập (synthetic traces)** tự viết bằng code!
5. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Thiết kế bảng Ablation `B0–B3` của bài này rất bài bản về mặt phương pháp luận khoa học, nhưng tác giả chưa chạy thật trên UTA-RLDD. Nhóm 05 sẽ kế thừa cấu trúc Ablation này và **chạy thực nghiệm thật trên 180 video UTA-RLDD**!

---

## BÀI 08: Cửa Sổ Thời Gian Thích Nghi Điều Khiển Bằng Độ Tự Tin `CDATW` (Xie & Xiao, 06/2026)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Real-time driver fatigue detection method based on confidence-driven adaptive time window*
   - **Tác giả & Năm:** Kun Xie, Degui Xiao (Hunan University, Trung Quốc — tạp chí *Frontiers in Neurorobotics*, Tháng 6/2026).
   - **Mã trong SC102:** `A13`.
   - **Link gốc:** https://doi.org/10.3389/fnbot.2026.1857548
   - **File trong máy:** [`P2_CDATW_Frontiers_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P2_CDATW_Frontiers_2026.pdf)
2. **Tóm tắt phương pháp & Công thức kỹ thuật:**
   - Giải quyết bài toán đánh đổi giữa **Độ trễ cảnh báo (Latency)** và **Tỷ lệ báo động giả (FAR)** bằng cơ chế **Confidence-Driven Adaptive Time Window (`CDATW`)**:
   - Tính độ tự tin tức thời $c_t = q_t (1 - u_t)$ (trong đó $q_t$ là chất lượng điểm mốc khuôn mặt và $u_t$ là phương sai dự đoán qua $N=10$ lần chạy MC-Dropout), làm mượt bằng trung bình trượt hàm mũ: $\bar{c}_t = 0.8\bar{c}_{t-1} + 0.2 c_t$.
   - **Công thức điều chỉnh độ dài cửa sổ quan sát $W_t$ liên tục từ $W_{\min} = 5\text{s}$ đến $W_{\max} = 30\text{s}$ (Công thức 14, Trang 5):**
     $$W_t = W_{\min} + (1 - \bar{c}_t)\cdot(W_{\max} - W_{\min})$$
   - Kết hợp biên trễ Hysteresis $\Delta = 0.05$ quanh ngưỡng quyết định và thời gian giữ trạng thái tối thiểu $T_{\text{dwell}} = 2\text{s}$.
3. **Kết quả thực nghiệm công bố:**
   - **Bảng 4 (Trang 10):** So với cửa sổ cố định 15s, cửa sổ thích nghi `CDATW` giúp **giảm 35.2% tỷ lệ báo động giả (`FAR` giảm từ 14.2% xuống 9.2%)** và tăng F1-score từ `85.6%` lên `89.2%`.
   - Đạt `89.3%` trên tập UTA-RLDD (khi gộp 2 lớp).
4. **Phát hiện đắt giá khi đọc toàn văn:**
   - **Mục 3.1.1 (Trang 6):** Để đạt con số `89.3%` trên UTA-RLDD, tác giả đã **gộp chung `Low Vigilant` và `Drowsy` thành 1 lớp nhị phân `Fatigued`** (*"low vigilant and drowsy videos were merged into the fatigued class"*).
5. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Cung cấp công thức toán học hoàn chỉnh để Nhóm 05 giải quyết **`Gap C` (rút ngắn cửa sổ 30 lần chớp mắt cố định của Ghoddoosian 2019 thành cửa sổ thích nghi từ 5 đến 30 lần chớp mắt tùy theo độ tự tin dự đoán của mạng HM-LSTM)**.

---

## BÀI 09: Giải Mã Con Số `88.89% VA` Trên UTA-RLDD (Chavan, Kaede, & Watanuki, 07/2026)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Early Driver Drowsiness Detection Using Individually Normalized Ocular Dynamics and Dual-Attention Hierarchical BiLSTM*
   - **Tác giả & Năm:** Pratik Chavan, Kazuma Kaede, Keiichi Watanuki (Saitama University, Nhật Bản — Hội nghị *AHFE 2026*, Tháng 7/2026).
   - **Mã trong SC102:** `A5`.
   - **Link gốc:** https://doi.org/10.54941/ahfe1007333
   - **File trong máy:** [`P6_AHFE_2026_Blendshapes_BiLSTM.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P6_AHFE_2026_Blendshapes_BiLSTM.pdf)
2. **Tóm tắt phương pháp & Công thức kỹ thuật:**
   - Thay `EAR` bằng 7 hệ số biểu cảm vùng mắt và lông mày của MediaPipe Face Landmarker (`eyeBlink`, `eyeSquint`, `eyeWide`, `browDown`, `browInnerUp`, `browOuterUp`...).
   - Chuẩn hóa Z-score cá nhân bằng 2 phút đầu của video `Alert`, chia cửa sổ 3600 frames (2 phút) thành 72 đoạn nhỏ (mỗi đoạn 50 frames) đưa vào mạng **Dual-Attention Hierarchical BiLSTM** trên tập **UTA-RLDD**.
3. **Kết quả thực nghiệm công bố:**
   - Tuyên bố đạt **`Video Accuracy (VA) = 88.89%`**, `Macro F1 = 87.2%`, `AUROC = 0.903` trên 5-fold CV của UTA-RLDD.
4. **Phát hiện đắt giá khi đọc toàn văn (Trang 6–8):**
   - **Mục 2.5 & 3.2 (Trang 6–7):** Mặc dù lúc huấn luyện hàm Smooth L1 Loss họ gán nhãn `Alert = 0.0`, `Low Vigilant = 0.5`, `Drowsy = 1.0`, nhưng khi đánh giá độ chính xác (`VA = 88.89%`), họ **KHÔNG phân loại 3 lớp**, mà đặt **1 ngưỡng cắt nhị phân duy nhất `threshold = 0.35`**: mọi video có điểm dự đoán $> 0.35$ đều được gom vào lớp **`Unsafe` (`Low Vigilant + Drowsy`)**, còn $\le 0.35$ là **`Safe` (`Alert`)**! Tức là `88.89%` là độ chính xác của **bài toán 2 lớp nhị phân**!
   - **Mục 3.3 (Trang 8):** Chính nhóm tác giả này đã kiểm tra lại bài `P2` (Xu et al., 2025 - đạt `86.88%`) và vạch trần rằng Xu et al. đã **lọc bỏ thủ công (manually filtered out) các mẫu nhập nhằng** trong UTA-RLDD!
5. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Đây là **vũ khí phản biện sắc bén nhất** của Nhóm 05: giúp giải thích rõ ràng vì sao các bài báo năm 2025–2026 dùng chuẩn hóa cá nhân trên UTA-RLDD lại báo cáo con số ~87%–89% (do họ gom `Low Vigilant` và `Drowsy` thành 1 lớp nhị phân `Unsafe` với ngưỡng `0.35`, chứ không tách 3 lớp độc lập như bài gốc 2019).

---

## BÀI 10: Chứng Minh >75%–92% Nhiễu Nhãn Cấp Độ Video (Mujtaba et al. — YawDD+, *IEEE ICIP 2026*)

1. **Thông tin định danh:**
   - **Tên bài báo:** *YawDD+: Frame-Level Benchmarking and Temporal-Enhanced Fine-Grained Action Detection for Driver Yawning*
   - **Tác giả & Năm:** Mujtaba et al. (*IEEE International Conference on Image Processing - ICIP 2026* / Tháng 12/2025).
   - **Link gốc:** https://arxiv.org/abs/2512.11446
   - **File trong máy:** [`B_YawDD_Plus_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_YawDD_Plus_2025.pdf)
2. **Tóm tắt phương pháp & Nội dung:**
   - Các tác giả tiến hành gán nhãn lại từng khung hình (frame-level annotation) cho toàn bộ các video lái xe vốn trước đây chỉ có 1 nhãn chung cho cả đoạn video dài (video-level label).
3. **Kết quả & Phát hiện đắt giá khi đọc toàn văn:**
   - Thống kê định lượng cho thấy trong các video mang nhãn "Ngáp / Buồn ngủ", có tới **75% đến 92.6% tổng số khung hình thực tế tài xế đang ở trạng thái bình thường (`Neutral`)**!
   - Khi huấn luyện mô hình bằng nhãn cấp độ video, các cửa sổ trượt ngắn rơi vào vùng bình thường nhưng vẫn bị ép mang nhãn "Mệt mỏi", gây ra nhiễu nhãn khổng lồ (severe label noise).
4. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Giải thích hoàn hảo 2 hiện tượng trong [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf) của Tiến:
     1. Tại sao độ chính xác trên từng chuỗi 30 lần chớp mắt (`BSA = 54.1%` ở `R0` và `46.8%` ở `R1`) luôn thấp hơn độ chính xác bỏ phiếu toàn video (`VA = 64.9%` ở `R0` và `53.7%` ở `R1`) hơn 10 điểm phần trăm.
     2. Tại sao các chuỗi chớp mắt của lớp `Low Vigilant (5)` trong video dài 10 phút lại bị dự đoán nhầm sang `Alert (0)` nhiều nhất (vì phần lớn thời gian trong 10 phút đó tài xế vẫn chớp mắt tỉnh táo bình thường).

---

## BÀI 11: Bằng Chứng Kinh Điển Về Ngụy Tạo Độ Chính Xác 98.89% – 99.97% Trên UTA-RLDD Do Rò Rỉ Dữ Liệu (Essahraui et al., *Sensors* 02/2025)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Real-Time Driver Drowsiness Detection Using Facial Analysis and Machine Learning Techniques*
   - **Tác giả & Năm:** Essahraui et al. (MDPI *Sensors*, Tập 25, Số 3, Bài 812 — Tháng 2/2025).
   - **Link gốc:** https://doi.org/10.3390/s25030812
   - **File trong máy:** [`B_Sensors_2025_Essahraui_FullText.txt`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Sensors_2025_Essahraui_FullText.txt)
2. **Tóm tắt phương pháp & Kết quả công bố:**
   - Cắt các khung hình từ video của bộ dữ liệu **UTA-RLDD**, dùng Haar Cascade cắt khuôn mặt rồi đưa vào các bộ phân loại học máy và học sâu.
   - **Bảng 7 & Bảng 10:** Công bố đạt **`1-NN` ($k=1$) = `98.89%`**, `Random Forest` = **`99.51%`**, `CNN` = **`99.97%`**, `YOLOv5/v8` = **`100% Precision & Recall`** trên UTA-RLDD!
3. **Phát hiện đắt giá khi đọc toàn văn:**
   - **Mục 3.1.4 & 3.2:** Họ gộp chung toàn bộ các khung hình cắt từ video của cả 60 người lại rồi **chia Train/Test ngẫu nhiên theo từng frame**!
   - Việc thuật toán láng giềng gần nhất **`1-NN` ($k=1$, chỉ so khoảng cách pixel với 1 tấm ảnh giống nhất trong tập Train) đạt 98.89%** là bằng chứng toán học tuyệt đối rằng: đối với mọi bức ảnh trong tập Test, luôn có một bức ảnh cách đó vài phần mười giây của **cùng người đó, trong cùng căn phòng đó** nằm ở tập Train! Mô hình thực chất đang **nhận diện khuôn mặt (Face Recognition)** chứ không phải nhận diện buồn ngủ!
   - *(Ở dòng 59 mục 3.4.1, tác giả còn copy-paste nhầm nguyên câu "distinguish between cheating and non-cheating behaviors" từ bài báo phát hiện gian lận thi cử sang bài báo buồn ngủ).*
4. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Dùng làm ví dụ phản chứng điển hình nhất trong phần *Related Work / Discussion* để bác bỏ toàn bộ các bài báo tuyên bố đạt 98%–99.9% trên UTA-RLDD nhờ chia dữ liệu sai nguyên tắc.

---

## BÀI 12: Nghiên Cứu Tái Lập (Reproducibility Study) Bảo Vệ Khoảng Cách `R0` vs. `R1` (Nakagama et al., *IEEE IV 2025*)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Evaluating the Generalization of Driver Drowsiness Detection Models Across Datasets*
   - **Tác giả & Năm:** Ryo Nakagama et al. (*IEEE Intelligent Vehicles Symposium - IV 2025*, Tháng 6/2025).
   - **Link gốc:** https://arxiv.org/abs/2506.07014
   - **File trong máy:** [`B_Nakagama_2025_Reproducibility_Leakage.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Nakagama_2025_Reproducibility_Leakage.pdf)
2. **Tóm tắt phương pháp & Kết quả công bố:**
   - Nhóm tác giả Nhật Bản tiến hành cài đặt và huấn luyện lại từ đầu (re-train from scratch) các kiến trúc phát hiện buồn ngủ nổi tiếng vốn công bố đạt **91% – 98% accuracy** trong bài báo gốc.
   - Khi huấn luyện lại một cách trung thực (chia độc lập người lái và không chọn checkpoint trên tập Test), độ chính xác của tất cả các mô hình này đều **sụt giảm mạnh xuống vùng 51% – 70%** (AUC chỉ đạt `0.52 – 0.53`).
3. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - **Kết luận:** Bài báo từ hội nghị hàng đầu *IEEE IV 2025* này là lá chắn vững chắc bảo vệ kết quả trong [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf) của Tiến: giải thích vì sao checkpoint chọn lọc của tác giả (`R0`) đạt `64.9%`, còn khi tự train lại trung thực 6 lần (`R1`) thì đạt `53.7% ± 2.0%`.

---

# PHẦN II: CHI TIẾT 8 BÀI BÁO PHỤ THAM KHẢO TRONG THƯ MỤC `luu_tru_phu/pdf_phu_tham_khao/`

---

## BÀI 13: Bài Tổng Quan Hệ Thống PRISMA Q1 83 Trang (Hassan et al., *AI Review* 05/2026)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Driver drowsiness detection using machine learning and deep learning: a systematic review*
   - **Tác giả & Năm:** Hassan et al. (*Artificial Intelligence Review* - Springer Nature Q1, Tháng 5/2026).
   - **Mã trong SC102:** `A15`.
   - **Link gốc:** https://doi.org/10.1007/s10462-026-11505-w
   - **File trong máy:** [`B_Survey_AI_Review_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_Survey_AI_Review_2026.pdf)
2. **Nội dung & Phát hiện chính:**
   - Rà soát hệ thống 185 bài báo giai đoạn 2018–2025 theo chuẩn PRISMA.
   - Chỉ ra rằng hơn 70% các bài báo dùng thị giác máy tính hiện nay đánh giá sai giao thức (thiếu kiểm định độc lập người lái LOSO/Subject-Independent CV) và chỉ báo cáo mỗi Accuracy.
   - Đề xuất **Bảng tiêu chuẩn đánh giá bắt buộc** cho các nghiên cứu mới: phải báo cáo `Macro-F1`, `PR-AUC`, `TPR@FAR` (tỷ lệ phát hiện đúng tại mức báo động giả cố định), sai số hiệu chuẩn xác suất (`ECE` / `Brier Score`), độ trễ phát hiện (`Latency`) và khoảng tin cậy (`mean ± std` qua các lần chạy/folds).
3. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - Dùng để trích dẫn trong phần mở đầu (*Introduction*) và thiết lập bộ chỉ số đánh giá chuyên nghiệp của nhóm.

---

## BÀI 14: Giao Thức Đánh Giá Chống Rò Rỉ `I_fit / I_cal / I_test` (Theivadas et al., 08/2026)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Leakage-Resistant Calibrated Vision-Based Driver Drowsiness Detection Under Cross-Subject Evaluation*
   - **Tác giả & Năm:** Theivadas et al. (Tháng 8/2026).
   - **Link gốc:** https://doi.org/10.21203/rs.3.rs-10574400/v1
   - **File trong máy:** [`P7_Leakage_Resistant_Calibrated_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/P7_Leakage_Resistant_Calibrated_2026.pdf)
2. **Nội dung & Phát hiện chính:**
   - Chỉ ra lỗi phổ biến trong code của các bài báo cũ (bao gồm cả code `drowsiness_detection.py` của Ghoddoosian 2019): vừa dùng tập Test để theo dõi epoch tốt nhất, vừa chọn ngưỡng phân loại trên tập Test.
   - Đề xuất chia dữ liệu nghiêm ngặt thành 3 tập độc lập hoàn toàn về mặt đối tượng: **`I_fit`** (huấn luyện trọng số mạng), **`I_cal`** (hiệu chuẩn xác suất Platt Scaling / Temperature Scaling và chọn ngưỡng tối ưu theo hệ số tương quan Matthews `MCC` hoặc chọn epoch dừng sớm), và **`I_test`** (chỉ chạy đúng 1 lần duy nhất để báo cáo kết quả cuối cùng).
3. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - Dùng làm căn cứ lý thuyết để sửa lỗi chọn epoch trên tập Test của code gốc 2019 (tách 1 phần tập Train làm tập Validation `I_cal` để lưu best checkpoint một cách trung thực).

---

## BÀI 15: Thích Nghi Thời Gian Thực Không Cần Calibration Riêng (Jang et al., 11/2025)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Calibration-Free Online Test-Time Adaptation for Electroencephalogram-Based Driver Drowsiness Detection*
   - **Tác giả & Năm:** Jang et al. (Tháng 11/2025).
   - **Link gốc:** https://arxiv.org/abs/2511.22030
   - **File trong máy:** [`B_TTA_CalibrationFree_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_TTA_CalibrationFree_2025.pdf)
2. **Nội dung & Phát hiện chính:**
   - Giải thích một bẫy toán học cực kỳ quan trọng khi muốn bỏ giai đoạn Calibration đầu phiên lái: Nếu ta dùng chuẩn hóa trực tuyến liên tục (cập nhật trung bình trượt $\mu_t, \sigma_t$ ở mọi thời điểm $t$), thì khi tài xế chuyển sang trạng thái buồn ngủ kéo dài, bộ chuẩn hóa sẽ **tự động dịch chuyển $\mu_t$ theo trạng thái buồn ngủ đó**, làm xóa sạch tín hiệu buồn ngủ và khiến **F1-score sập từ `67.23%` xuống chỉ còn `6.46%`**!
   - Để khắc phục, chỉ được phép cập nhật thống kê chuẩn hóa ở những mẫu có độ tự tin/entropy thỏa mãn điều kiện chọn lọc (Selective Updating).
3. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - Giải thích vì sao trong **`Gap A`**, ta không thể thay thế Calibration bằng phép chuẩn hóa trượt ngây thơ (naive running normalization), mà phải dùng bộ lọc kiểm định trạng thái hoặc phân cụm chọn lọc.

---

## BÀI 16: Bộ Dữ Liệu Mới UL-DD Chấm KSS Mỗi 4 Phút (Bodaghi et al., *Nature Scientific Data* 2026)

1. **Thông tin định danh:**
   - **Tên bài báo:** *UL-DD: A Multimodal Dataset for Driver Drowsiness Detection During Extended Driving Sessions*
   - **Tác giả & Năm:** Bodaghi et al. (University of Ljubljana — tạp chí *Nature Scientific Data*, Tháng 1/2026).
   - **Link gốc:** https://doi.org/10.1038/s41597-025-06540-1
   - **File trong máy:** [`B_UL_DD_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_UL_DD_2026.pdf)
2. **Nội dung & Phát hiện chính:**
   - Khắc phục nhược điểm của UTA-RLDD (quay 3 đoạn 10 phút rời rạc và gán 1 nhãn cho cả 10 phút) bằng cách quay phiên lái liên tục 40 phút và yêu cầu tài xế báo cáo mức độ buồn ngủ KSS **mỗi 4 phút một lần**.
   - **Kết quả kiểm chứng kỹ thuật (Technical Validation):** Khi đánh giá 5-fold Cross-Validation độc lập người lái, nếu **chỉ dùng camera hình ảnh khuôn mặt (Unimodal Visual)** thì độ chính xác chỉ đạt **52% – 68%**; chỉ khi kết hợp đa phương thức (camera + sinh lý + thông số vô lăng/chân ga) mới tăng lên **84%**.
3. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - Khẳng định thêm một lần nữa (từ tạp chí danh tiếng *Nature Scientific Data* 2026) rằng với bài toán chỉ dùng hình ảnh khuôn mặt và đánh giá 5-fold độc lập người lái, trần độ chính xác thực tế của ngành hiện nay nằm ở vùng **52% – 68%** (hoàn toàn khớp với `R0 = 64.9%` và `R1 = 53.7%` của nhóm).

---

## BÀI 17: Mạng Đồ Thị Không-Thời Gian & Tích Chập Nhân Quả Giãn Nở Siêu Nhẹ (Ren et al. — LiteFat, 08/2025)

1. **Thông tin định danh:**
   - **Tên bài báo:** *LiteFat: A Lightweight Spatio-Temporal Graph and Temporal Convolutional Network for Driver Fatigue Detection*
   - **Tác giả & Năm:** Ren et al. (Tháng 8/2025).
   - **Link gốc:** https://arxiv.org/abs/2507.21756
   - **File trong máy:** [`B_LiteFat_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_LiteFat_2025.pdf)
2. **Nội dung & Phát hiện chính:**
   - Thay thế các mạng hồi quy tuần tự nặng nề (như LSTM / HM-LSTM vốn khó hội tụ và dễ overfit khi dữ liệu ít) bằng mạng **Dilated Causal Temporal Convolutional Network (TCN)** kết hợp Graph Convolution trên các điểm mốc vùng mắt và miệng.
   - Mô hình chỉ nặng **0.296 triệu tham số**, suy luận thời gian thực trên CPU mà vẫn nắm bắt được trường tiếp nhận thời gian dài (long receptive field) nhờ hệ số giãn nở $d = 1, 2, 4, 8$.
3. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - Nếu nhóm muốn thử nghiệm thêm một kiến trúc mạng hiện đại thay thế cho `HM-LSTM` trên chuỗi đặc trưng chớp mắt `(N, 30, D)`, kiến trúc **1D Dilated Causal TCN** hoặc **Bi-GRU nhẹ** là lựa chọn tốt nhất.

---

## BÀI 18: Tiền Xử Lý Cân Bằng Sáng Thích Nghi `CLAHE` & Lỗi Chia Frame Trên UTA-RLDD (*Light-VTD*, *Nature Sci Reports* 03/2026)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Light-VTD: A lightweight vision transformer for real-time driver drowsiness detection*
   - **Tác giả & Năm:** *Nature Scientific Reports* (Tháng 3/2026).
   - **Link gốc:** https://doi.org/10.1038/s41598-026-41847-y
   - **File trong máy:** [`B_LightVTD_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_LightVTD_2026.pdf)
2. **Nội dung & Phát hiện chính:**
   - **Điểm mạnh kỹ thuật:** Áp dụng thuật toán cân bằng biểu đồ sáng thích nghi có giới hạn độ tương phản (**`CLAHE`** với `clipLimit = 2.0, tileGridSize = (8,8)`) trước khi phát hiện khuôn mặt, giúp tăng **+2.4% độ chính xác** trên các video UTA-RLDD bị tối hoặc ngược sáng.
   - **Điểm yếu phương pháp khi đọc toàn văn (Trang 8):** Công bố đạt `97.6%` trên UTA-RLDD, nhưng thực chất chỉ trích xuất **11,787 frames**, gộp thành **2 lớp nhị phân** (`Active` = 7,230 frames vs `Fatigue` = 4,557 frames) và chia ngẫu nhiên **80% / 5% / 15% theo từng frame**!
3. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - Dùng hai mặt: **(1)** Áp dụng bước tiền xử lý `CLAHE` của bài này nếu chạy lại Giai đoạn 1 (Video $\to$ Landmarks) để giảm số frame bị mất mặt; **(2)** Dùng Trang 8 của bài này để phản biện con số `97.6%` trên UTA-RLDD.

---

## BÀI 19: Bằng Chứng Sập Độ Chính Xác Từ 99.94% Xuống 48.86% Khi Lượng Tử Hóa Do Học Vẹt Frame (Essahraui et al. — FastKAN, *PLOS ONE* 11/2025)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Lightweight and accurate driver drowsiness detection using MobileNetV2 and FastKAN*
   - **Tác giả & Năm:** Essahraui et al. (*PLOS ONE*, Tháng 11/2025).
   - **Link gốc:** https://doi.org/10.1371/journal.pone.0332577
   - **File trong máy:** [`B_FastKAN_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_FastKAN_2025.pdf)
2. **Nội dung & Phát hiện chính:**
   - Cùng nhóm tác giả với Bài 11: tiếp tục chia ngẫu nhiên theo frame trên UTA-RLDD và công bố mạng MobileNetV2 + FastKAN đạt **99.94% accuracy** ở độ chính xác dấu phẩy động `FP32`.
   - Tuy nhiên, ở bảng thử nghiệm nén mô hình sang số nguyên 8-bit (**Post-Training Quantization - `PTQ` int8**), độ chính xác của mô hình trên UTA-RLDD **sập thẳng đứng từ `99.94%` xuống chỉ còn `48.86%`** (tức là ngang đoán mò ngẫu nhiên)!
3. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - Đây là bằng chứng kỹ thuật cực hay: một mô hình học đặc trưng sinh lý thật sự sẽ không bao giờ mất 51% độ chính xác chỉ vì làm tròn trọng số sang 8-bit; việc sập từ `99.94%` xuống `48.86%` chứng tỏ mạng `FP32` đã tạo ra các biên quyết định cực kỳ sắc nhọn và mong manh để **nhớ vẹt từng pixel nền/khuôn mặt** của các frame bị rò rỉ giữa tập Train và tập Test!

---

## BÀI 20: Hạn Chế Của Hướng Tiếp Cận Ảnh Vùng Mắt Tĩnh (Hassan et al., *Nature Sci Reports* 05/2025)

1. **Thông tin định danh:**
   - **Tên bài báo:** *Vision transformer based driver drowsiness detection from eye region images*
   - **Tác giả & Năm:** Hassan et al. (*Nature Scientific Reports*, Tháng 5/2025).
   - **Link gốc:** https://doi.org/10.1038/s41598-025-02111-x
   - **File trong máy:** [`B_ViT_SciRep_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_ViT_SciRep_2025.pdf)
2. **Nội dung & Phát hiện chính:**
   - Huấn luyện các mạng Vision Transformer (ViT / Swin) nặng hàng chục triệu tham số chỉ để phân loại từng bức ảnh cắt vùng mắt đơn lẻ (`Open Eye` vs `Closed Eye`).
   - Toàn bộ phần kết luận và hạn chế của bài báo thừa nhận: một bức ảnh mắt đang nhắm ở 1 thời điểm tĩnh không thể cho biết tài xế đang **chớp mắt bình thường (kéo dài 100–200 ms)** hay đang **ngủ gật / microsleep (kéo dài >500 ms)**, và càng không thể nhận biết giai đoạn chớm buồn ngủ (`Low Vigilant`).
3. **KẾT LUẬN & Cách Nhóm 05 sử dụng:**
   - Dùng để khẳng định tính đúng đắn của hướng tiếp cận **Phân tích động học chuỗi thời gian của nhịp chớp mắt (Temporal Blink Dynamics)** mà bài báo gốc 2019 và Nhóm 05 đang theo đuổi: chỉ có chuỗi thời gian mới tách biệt được sự thay đổi dần dần của vận tốc đóng/mở mắt ở giai đoạn `Low Vigilant`.
