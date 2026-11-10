# CẨM NANG ĐỌC PAPER: MỖI BÀI BÁO ĐÓNG GÓP & PHÁT HIỆN ĐƯỢC GÌ SO VỚI BÀI BÁO TRUNG TÂM 2019 (GHODDOOSIAN ET AL.)?

> **Trọng tâm của tài liệu này:** Đặt **bài báo gốc năm 2019 (Ghoddoosian et al., CVPRW 2019)** làm **Tâm Điểm Quy Chiếu**.
> Không bàn chuyện kế hoạch xa xôi — với từng bài báo trong tổng số 20 bài đã tải về, tài liệu này trả lời thẳng 4 câu hỏi cốt lõi để bạn quyết định có cần mở PDF đó ra đọc hay không và đọc đúng chỗ nào:
> 1. **🎯 ĐÚC KẾT 1 CÂU:** Bài báo này đóng góp hoặc làm sáng tỏ điều gì mà bài báo 2019 chưa biết, làm sai, hoặc bỏ sót?
> 2. **⚖️ ĐỐI CHIẾU TRỰC DIỆN VỚI BÀI 2019:** Bài 2019 làm gì $\leftrightarrow$ Bài này làm khác đi ở điểm nào?
> 3. **🔬 PHÁT HIỆN KHOA HỌC ĐẮT GIÁ NHẤT:** Con số, định lý hoặc sự thật thực nghiệm nào trong bài này chứng minh cho các hiện tượng trên bộ dữ liệu UTA-RLDD?
> 4. **📖 CHỈ DẪN ĐỌC NHANH TRONG PDF (Đọc trang nào, bảng nào?):** Mở PDF lên thì lật ngay tới trang mấy, bảng/hình nào để xem phần tinh túy nhất (và cảnh báo phần nào trong bài đó làm chưa chuẩn).

---

## BẢNG TỔNG QUAN CÔ ĐỌNG: 20 BÀI BÁO SOI CHIẾU VÀO 5 MẶT CỦA BÀI BÁO 2019

Bài báo gốc 2019 gồm **5 mắt xích chính**. Toàn bộ 19 bài báo còn lại thực chất chỉ xoay quanh việc **kiểm chứng, vạch lỗi hoặc nâng cấp 5 mắt xích này**:

| Mắt xích trong Bài 2019 (Ghoddoosian et al.) | Điểm mù / Nghi vấn trong Bài 2019 | Các bài báo nào làm sáng tỏ mắt xích này? | Phát hiện cốt lõi nhất khi đặt cạnh Bài 2019 |
| :--- | :--- | :--- | :--- |
| **1. Bộ dữ liệu UTA-RLDD & Cách lấy mẫu khung hình** | Bài 2019 nói video quay bằng điện thoại/webcam `< 30 fps`, nhưng lại tính `Duration` và `Velocity` theo **số frame** (coi như mọi video có cùng FPS). | - **Bài 02 (`P1_ELA_2025.pdf`)** <br> - **Bài 10 (`B_YawDD_Plus_2025.pdf`)** <br> - **Bài 16 (`B_UL_DD_2026.pdf`)** | - **Bài 02** phát hiện **169/182 video trong UTA-RLDD bị biến thiên FPS (12–30 Hz)**! Tính theo số frame như bài 2019 làm thời lượng chớp mắt sai lệch tới **32%**. <br> - **Bài 10 & 16** chứng minh gán 1 nhãn cho cả video 10 phút làm **>75%–92% frame bị nhiễu nhãn** (vì tài xế không buồn ngủ ở mọi giây), giải thích vì sao `BSA` (54%) luôn thấp hơn `VA` (65.2%). |
| **2. Bộ 4 đặc trưng chớp mắt (`Duration`, `Amplitude`, `Opening Velocity`, `Frequency`)** | Tại sao bài 2019 chỉ lấy vận tốc mở mắt mà bỏ qua vận tốc nhắm mắt, độ lệch đóng/mở và `PERCLOS`? `Frequency` có thực sự tốt không? | - **Bài 03 (`P8_Akin_Kalkan_2024.pdf`)** <br> - **Bài 04 (`B_Webcam_2025.pdf`)** <br> - **Bài 02 (`P1_ELA_2025.pdf`)** | - **Bài 04** chạy trên UTA-RLDD chứng minh đặc trưng `Frequency` của bài 2019 chỉ đóng góp **4%** độ quan trọng, trong khi `EAR Variance` (41%) và `PERCLOS` (25%) bị bài 2019 bỏ quên! <br> - **Bài 03** chứng minh trên UTA-RLDD rằng tách riêng **pha đóng (`closing`)**, **pha mở (`reopening`)** và **độ lệch (`reopening - closing`)** giúp tăng ngay **+5.15% đến +9.64% accuracy**. |
| **3. Phép chuẩn hóa cá nhân (Công thức 6: Lấy 1/3 đầu video `Alert`)** | Phép chuẩn hóa cá nhân của bài 2019 đóng góp bao nhiêu % độ chính xác? Và chuyện gì xảy ra nếu đầu phiên lái tài xế không ở trạng thái `Alert`? | - **Bài 05 (`P3_Zenodo_2026.pdf`)** <br> - **Bài 06 (`P4_Personalized_2026.pdf`)** <br> - **Bài 07 (`P5_ResearchSquare_2026.pdf`)** <br> - **Bài 15 (`B_TTA_2025.pdf`)** | - **Bài 05** đo đạc thực tế: `EAR` lúc tỉnh của các tài xế lệch nhau từ **`0.198` đến `0.305`**; chuẩn hóa 60s đầu giúp tăng **+3.9% accuracy**, nhưng tác giả thừa nhận nếu tài xế mệt ngay từ đầu thì phép chuẩn hóa này sẽ làm hỏng mô hình. <br> - **Bài 15** chứng minh nếu cập nhật trung bình trượt liên tục lúc tài xế đang buồn ngủ thì F1-score sập từ **67.23% xuống 6.46%**. |
| **4. Cửa sổ 30 lần chớp mắt cố định & Kiến trúc HM-LSTM** | Đợi đủ 30 lần chớp mắt (~2–3 phút) mới dự đoán là quá trễ; nếu rút ngắn cửa sổ xuống thì báo động giả (`FAR`) tăng bao nhiêu? | - **Bài 08 (`P2_CDATW_2026.pdf`)** <br> - **Bài 17 (`B_LiteFat_2025.pdf`)** <br> - **Bài 20 (`B_ViT_SciRep_2025.pdf`)** | - **Bài 08** chứng minh dùng cửa sổ cố định luôn bị kẹt giữa Độ trễ và Báo động giả; nếu co giãn cửa sổ từ **5s đến 30s theo độ tự tin dự đoán**, tỷ lệ báo động giả **giảm 35.2%**. |
| **5. Giao thức đánh giá 5-Fold 3-Class & Con số `VA = 65.2%`** | Tại sao bài 2019 chỉ đạt `65.2%` (và train lại `R1` chỉ đạt `53.7%`), trong khi nhiều bài 2024–2026 khoe đạt `88.89% – 99.97%` trên UTA-RLDD? | - **Bài 02 (`P1_ELA_2025.pdf`)** <br> - **Bài 09 (`P6_AHFE_2026.pdf`)** <br> - **Bài 11 (`B_Sensors_2025.txt`)** <br> - **Bài 12 (`B_Nakagama_2025.pdf`)** <br> - **Bài 14, 18, 19** | - **Bài 02 & 12** chứng minh nếu giữ đúng **3 lớp + 5-fold độc lập người lái** và train lại trung thực từ đầu, độ chính xác thực tế chỉ là **52.5% – 53.7%**! <br> - **Bài 09** đạt `88.89%` vì đặt ngưỡng `0.35` gộp `Low Vigilant + Drowsy` thành **bài toán 2 lớp**. <br> - **Bài 11, 18, 19** đạt `97.6% – 99.97%` vì **trộn chung các frame của 60 người rồi chia ngẫu nhiên** (mô hình nhớ mặt tài xế chứ không học buồn ngủ). |

---

# PHẦN I: 12 BÀI BÁO TRONG THƯ MỤC `pdf_bai_bao/` (ĐỌC ĐỂ HIỂU SÂU & BỔ KHUYẾT BÀI 2019)

---

## BÀI 01: Bài Báo Trung Tâm (Ghoddoosian et al., CVPRW 2019)
- **File PDF:** [`P0_Ghoddoosian_2019.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P0_Ghoddoosian_2019.pdf) | **Link gốc:** https://arxiv.org/abs/1904.07312
- **🎯 Đúc kết 1 câu:** Bài báo đặt nền móng cho bộ dữ liệu **UTA-RLDD (30 giờ, 60 người, 3 lớp)** và đề xuất dùng **chuỗi 30 lần chớp mắt liên tiếp (4 đặc trưng/nhịp)** đưa vào mạng **HM-LSTM** để phát hiện sớm giai đoạn chớm buồn ngủ (`Low Vigilant`).
- **🔬 Những thông số & điểm mù cốt lõi trong bài báo gốc mà bạn cần nắm chắc:**
  1. **Tại sao con người cũng chỉ đoán đúng 57.8% trên UTA-RLDD?** (Mục 5.2, Trang 7): Tác giả cho 20 người xem các video UTA-RLDD và tự phân loại 3 lớp; con người chỉ đạt `VA = 57.8%` vì trạng thái `Low Vigilant (5)` hầu như không có biểu hiện ngáp hay gật đầu rõ rệt trên từng khung hình lẻ, mà chỉ thay đổi tinh vi ở **động học chớp mắt qua thời gian**.
  2. **Thuật toán tìm chớp mắt thực sự nằm ở đâu?** Không nằm ở phần chính mà nằm ở **Trang 11 (Supplementary Material - `Algorithm 1`)**: Dùng ngưỡng thích nghi $\text{THR} = 0.6\max(x) + 0.4\min(x)$ và điểm đổi dấu đạo hàm bậc 1 $\dot{x}[n]\cdot\dot{x}[n+1] < 0$ để sửa lỗi cho bộ SVM của Soukupová & Čech (2016) vốn bị mù trước các nhịp nhắm mắt dài (microsleep).
  3. **Bốn điểm yếu kỹ thuật ngay trong công thức của bài 2019:**
     - **Điểm yếu 1 (Công thức 2 & 4, Trang 4):** Tính `Duration` bằng số frame ($\text{end}_i - \text{start}_i + 1$) và `Opening Velocity` bằng $\Delta\text{EAR}/\text{frame}$ mà quên mất rằng các video trong UTA-RLDD được quay bằng điện thoại/webcam khác nhau có **FPS khác nhau**.
     - **Điểm yếu 2 (Trang 4):** Chỉ lấy `Opening Velocity` mà bỏ qua hoàn toàn pha nhắm mắt (`Closing Duration/Velocity`), tỷ lệ nhắm mắt `PERCLOS`, và phương sai độ mở mắt.
     - **Điểm yếu 3 (Công thức 6, Trang 5):** Để chuẩn hóa cá nhân, tác giả lấy **1/3 đầu của video mang nhãn `Alert` có sẵn** để khử cơ địa cho cả 3 video (`Alert`, `Low Vigilant`, `Drowsy`) của người đó — một giả định "biết trước tương lai" (Oracle assumption).
     - **Điểm yếu 4 (Hình 3, Trang 7 - Confusion Matrix):** Mô hình HM-LSTM đạt `VA = 65.2%` tổng thể, nhưng riêng lớp `Low Vigilant` có độ chính xác thấp nhất (bị nhầm lẫn nặng sang `Alert` và `Drowsy`).
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Đọc **Trang 4–5 (Mục 4.1 & 4.2)**: Công thức (1) đến (6) về trích xuất 4 đặc trưng và chuẩn hóa cá nhân.
  - Đọc **Trang 7 (Bảng 2 & Hình 3)**: Kết quả chuẩn (`BSA = 54.0%`, `VA = 65.2%`) và Ma trận nhầm lẫn 3 lớp.
  - Đọc **Trang 11 (`Algorithm 1` & `Algorithm 2`)**: Mã giả thuật toán tìm `start`, `bottom`, `end` của nhịp chớp mắt.

---

## BÀI 02: Wolter, Berrio Perez, & Shan (ĐH Sydney, Tháng 11/2025)
- **Tên bài báo:** *Eyelid Angle for Blink Detection and Drowsiness Characterization*
- **File PDF:** [`P1_ELA_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P1_ELA_2025.pdf) | **Link gốc:** https://arxiv.org/abs/2511.19519
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Đây là bài báo **duy nhất giai đoạn 2025–2026 chạy lại đúng giao thức 5-fold 3-class của bài 2019 trên toàn bộ UTA-RLDD**, đồng thời **phát hiện ra lỗi chí mạng của bài 2019**: 169/182 video trong UTA-RLDD có tốc độ khung hình biến thiên (VFR 12–30 Hz), khiến công thức tính theo `frame` của năm 2019 bị sai lệch tới 32%!
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  | Tiêu chí | Bài báo gốc 2019 (Ghoddoosian) | Bài báo 2025 này (Wolter et al.) |
  | :--- | :--- | :--- |
  | **Tín hiệu mở mắt** | `EAR` 2D từ 68 điểm `dlib` (nhạy cảm khi quay đầu). | Góc mở mí mắt 3D **`ELA` (độ $^\circ$)** từ 478 điểm 3D MediaPipe (chịu được quay đầu $\pm 30^\circ$). |
  | **Xử lý biến thiên FPS** | Không xử lý (tính thẳng bằng số `frame`). | Lọc mượt Gaussian theo FPS ($\sigma = \text{FPS}/30$) và đổi mọi thời lượng sang **giây (`s`)**, vận tốc sang **độ/giây ($^\circ/\text{s}$)**. |
  | **Số đặc trưng / nhịp chớp** | **4 đặc trưng** (gộp chung tổng Duration, chỉ có Opening Velocity). | **9 đặc trưng** (tách riêng pha đóng $d_1$, nhắm kín $d_2$, mở $d_3$, tổng $D$, biên độ đóng/mở $a_1, a_2$, vận tốc đóng/mở $v_1, v_2$, tần suất $f_i$). |
  | **Kết quả 5-fold UTA-RLDD** | Báo cáo `BSA = 54.0%`, `VA = 65.2%` (3-class). | Tự train lại HM-LSTM đạt **`BSA = 46.8%`, `VA = 52.5%` (3-class)** và **`BSA = 69.5%`, `VA = 80.4%` (2-class)**. |
- **🔬 Phát hiện khoa học đắt giá nhất (Vì sao bạn bắt buộc phải đọc bài này):**
  1. **Bằng chứng về lỗi FPS của UTA-RLDD (Mục IV-B, Trang 5):** Tác giả kiểm tra từng video của bộ UTA-RLDD và chỉ ra **169 trên tổng số 182 video có tốc độ khung hình không cố định (Variable Frame Rate - VFR, dao động từ 12 đến 30 fps)**. Khi FPS giảm từ 30 xuống 15 Hz, cách tính theo `frame` của Ghoddoosian 2019 làm thời gian đóng mắt (`Closing Duration`) bị **sai lệch 32%**, kéo độ chính xác phân loại buồn ngủ từ **98% sụt xuống 69%** (Bảng II & Hình 6, Trang 6).
  2. **Sự thật về độ chính xác 3-class vs. 2-class trên UTA-RLDD (Bảng IV, Trang 7):** Khi huấn luyện lại mạng HM-LSTM ($T=30$) trên đúng 5-fold của UTA-RLDD, độ chính xác 3 lớp đạt **`BSA = 46.8%`, `VA = 52.5%`** (trùng khớp với kết quả tự train `R1` của nhóm bạn: `BSA = 46.8%`, `VA = 53.7%`!). Nhưng chỉ cần bỏ lớp `Low Vigilant` để đánh giá 2 lớp (`Alert` vs `Drowsy`), độ chính xác lập tức tăng vọt thêm **+27.9%** (lên **`80.4%`**).
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Đọc **Trang 3–4 (Mục III-C, Hình 3 & 4)**: Cách định nghĩa 9 đặc trưng chớp mắt tách biệt pha đóng ($d_1$), nhắm kín ($d_2$) và pha mở ($d_3$).
  - Đọc **Trang 5–6 (Mục IV-B, Hình 5, Hình 6, Bảng II)**: Phát hiện 169/182 video UTA-RLDD bị VFR và chứng minh sai số 32% khi tính theo `frame`.
  - Đọc **Trang 7 (Mục IV-C, Bảng IV)**: Bảng kết quả đối chiếu trực tiếp với Ghoddoosian 2019 trên UTA-RLDD (3-class vs 2-class).

---

## BÀI 03: Akin & Kalkan (METU, Tháng 7/2024)
- **Tên bài báo:** *Exploring Blink Behavior carefully for Drowsiness Detection*
- **File PDF:** [`P8_Akin_Kalkan_2024_Blink_Behavior.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P8_Akin_Kalkan_2024_Blink_Behavior.pdf) | **Link gốc:** https://arxiv.org/abs/2407.02222
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Chứng minh bằng thực nghiệm Ablation trực tiếp trên bộ dữ liệu UTA-RLDD rằng: việc bài báo 2019 chỉ dùng tổng thời lượng chớp mắt (`Total Duration`) mà bỏ qua **thời lượng pha nhắm mắt (`closing`)**, **pha mở mắt (`reopening`)** và **độ bất đối xứng giữa hai pha (`reopening - closing`)** đã làm mất đi từ **5.15% đến 9.64% độ chính xác**!
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  - Bài 2019 coi cả nhịp chớp mắt là 1 khoảng thời gian tổng $\text{Duration}_i = \text{end}_i - \text{start}_i + 1$ và chỉ tính vận tốc lúc mở mắt.
  - Bài 2024 này lập luận rằng khi con người bắt đầu mệt mỏi, **tương quan thời gian giữa pha sập mí mắt xuống (`closing`) và pha kéo mí mắt lên (`reopening`) bị biến dạng mạnh**. Họ tách bộ đặc trưng thành 2 tập để chạy đối chứng trên UTA-RLDD:
    - `blink_set1` (chỉ có tổng `duration`, khoảng cách giữa 2 lần chớp `interval`, và tổng số lần chớp `total_blinks`).
    - `blink_set2` (thêm 3 đặc trưng nội tại: `closing`, `reopening`, và hiệu số `diff = reopening - closing`).
- **🔬 Phát hiện khoa học đắt giá nhất:**
  1. **Bảng 2 (Trang 3) — Kết quả Ablation trên UTA-RLDD:** Khi bổ sung `closing`, `reopening` và `diff = reopening - closing` (`blink_set2`), độ chính xác phân loại trên UTA-RLDD tăng vọt trên **cả 4 thuật toán học máy**:
     - `SVM`: từ `68.00%` $\rightarrow$ **`77.64%` (+9.64%)**
     - `Decision Tree`: từ `64.61%` $\rightarrow$ **`72.51%` (+7.90%)**
     - `kNN`: từ `68.26%` $\rightarrow$ **`75.67%` (+7.41%)**
     - `Random Forest`: từ `73.79%` $\rightarrow$ **`78.94%` (+5.15%)**
  2. **Quy tắc ngưỡng trễ Hysteresis $\pm 20\%$ theo cơ địa (Trang 2):** Lấy 2 phút đầu của video `Alert` tính $\text{EAR}_{ref}$, đặt ngưỡng bắt đầu nhắm mắt tại $0.80\,\text{EAR}_{ref}$ và ngưỡng mở mắt tại $1.20\,\text{EAR}_{ref}$ để chống nhiễu rung mí mắt.
  3. **Điểm hạn chế của chính bài này:** Bảng 1 (Trang 2) cho thấy tác giả vẫn đo `closing` và `reopening` bằng **số frame (`#frames`)** (mắc cùng lỗi VFR như bài 2019) và mới chỉ kiểm nghiệm trên 21 người với 2 lớp (`0` vs `10`).
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Bài báo chỉ dài 4 trang, cực kỳ cô đọng: lật ngay **Trang 2 (Bảng 1 & Hình 2)** để xem định nghĩa 6 đặc trưng chớp mắt, và **Trang 3 (Bảng 2)** để xem bảng đối chứng `blink_set1` vs `blink_set2` trên UTA-RLDD.

---

## BÀI 04: Goswami & Waghmare (IIT Roorkee, Tháng 11/2025)
- **Tên bài báo:** *Webcam-Based Driver Drowsiness Detection Using MediaPipe FaceMesh Eye Features*
- **File PDF:** [`B_Webcam_MediaPipe_Eye_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Webcam_MediaPipe_Eye_2025.pdf) | **Link gốc:** https://doi.org/10.21203/rs.3.rs-8036038/v1
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Giải thích bằng con số định lượng trên tập UTA-RLDD vì sao đặc trưng thứ 4 của bài báo 2019 (`Blink Frequency` / `Blink Rate`) hoạt động kém hiệu quả, và chỉ ra 2 đặc trưng có sức mạnh phân loại lớn nhất mà bài 2019 đã bỏ sót (`EAR Variance` và `PERCLOS`).
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  - Bài 2019 chọn 4 đặc trưng với vai trò ngang nhau: `Duration`, `Amplitude`, `Opening Velocity`, và **`Frequency` (Tần suất chớp mắt)**.
  - Bài 2025 này trích xuất đặc trưng mắt trên tập **UTA-RLDD** và dùng thuật toán Random Forest để **đo lường tỷ trọng đóng góp (Feature Importance)** của từng đặc trưng đối với việc phân biệt trạng thái tỉnh táo và buồn ngủ.
- **🔬 Phát hiện khoa học đắt giá nhất (Mục 5.2, Trang 6):**
  - Kết quả phân tích độ quan trọng đặc trưng (Feature Importance) trên UTA-RLDD cho thấy:
    1. **`EAR_Variance` (Phương sai / mức độ dao động độ mở mắt trong cửa sổ thời gian): `41%` (`0.41`)** — Đặc trưng quan trọng số 1, nhưng **bài báo 2019 hoàn toàn không có**!
    2. **`Avg_Blink_Duration` (Thời lượng chớp mắt): `30%` (`0.30`)** — Đặc trưng quan trọng số 2 (bài 2019 có dùng).
    3. **`PERCLOS` (Tỷ lệ phần trăm thời gian mắt nhắm kín): `25%` (`0.25`)** — Đặc trưng quan trọng số 3, nhưng **bài báo 2019 cũng bỏ qua** (vì bài 2019 chỉ trích xuất tại thời điểm có sự kiện chớp mắt rời rạc chứ không tính tỷ lệ thời gian mắt nhắm trong cửa sổ).
    4. **`Blink_Rate` (Tần suất số lần chớp mắt / Frequency): chỉ đạt `4%` (`0.04`)** — Gần như không có khả năng phân loại vì tốc độ chớp mắt giữa các cá nhân biến thiên quá hỗn loạn!
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Bạn không cần đọc toàn bộ phần giới thiệu MediaPipe cơ bản; hãy mở thẳng tới **Trang 4 (Mục 3.4 - Công thức 4 đặc trưng)** và **Trang 6 (Mục 5.2 - Bảng Feature Importance `0.41 / 0.30 / 0.25 / 0.04`)**.

---

## BÀI 05: Sobirov & Hamidov (Tháng 7/2026)
- **Tên bài báo:** *Deep Learning for Real-Time Driver Drowsiness Detection from Facial Video: Architecture Comparison, Temporal Modeling, and Edge Deployment*
- **File PDF:** [`P3_Zenodo_2026_Best_Vol. 3 No. 7. 2026_591-600.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P3_Zenodo_2026_Best_Vol.%203%20No.%207.%202026_591-600.pdf) | **Link gốc:** https://doi.org/10.5281/zenodo.21524614
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Làm sáng tỏ **3 câu hỏi lớn mà bài báo 2019 bỏ ngỏ**: (1) Cơ địa mắt của các tài xế khác nhau lệch nhau bao nhiêu mà bắt buộc phải dùng Công thức (6) Calibration? (2) Có Calibration thì tăng được bao nhiêu % so với không có? (3) Và giả định "lấy phút đầu tiên lúc tỉnh táo làm Calibration" của bài 2019 sẽ sụp đổ trong tình huống thực tế nào?
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  - Bài 2019 áp dụng Công thức (6) chuẩn hóa cá nhân (lấy 1/3 đầu video `Alert`), nhưng **không hề làm thí nghiệm Ablation** xem nếu bỏ Công thức (6) đi thì độ chính xác giảm bao nhiêu %, và cũng không bàn về việc tài xế mệt sẵn từ đầu.
  - Bài 2026 này thực hiện đầy đủ các phép đo định lượng đó.
- **🔬 Phát hiện khoa học đắt giá nhất:**
  1. **Đo đạc sự khác biệt cơ địa mắt giữa các tài xế (Mục 4.4, Trang 6):** Khi hoàn toàn tỉnh táo (`Alert`), giá trị trung vị `EAR` tự nhiên của các tài xế khác nhau trải rộng từ **`0.198` (người mắt hẹp) đến `0.305` (người mắt to)**. Nếu không chuẩn hóa cá nhân như Công thức (6) của bài 2019, người có `EAR = 0.198` sẽ bị hệ thống báo động giả là buồn ngủ suốt cả chuyến đi!
  2. **Định lượng mức tăng của Calibration (Mục 4.4, Trang 6):** Áp dụng chuẩn hóa Z-score bằng 60 giây đầu tiên ($\text{EAR}_{\text{norm}} = (\text{EAR} - \mu_{\text{init}})/\sigma_{\text{init}}$) giúp độ chính xác trên tài xế mới (Unseen Drivers) tăng từ **`88.4%` lên `92.3%` (+3.9 điểm phần trăm)** và giảm một nửa độ lệch chuẩn giữa các tài xế (từ $\pm 7.8\%$ xuống $\pm 4.1\%$).
  3. **Định lượng mức sụt giảm khi đánh giá độc lập người lái (Bảng 1, Trang 5):** Giải thích vì sao bài 2019 chia theo Subject-Independent 5-fold lại khó hơn hẳn các bài chia ngẫu nhiên: cùng một mô hình, khi chuyển từ `Random Window Split` sang `Subject-Independent Split`, độ chính xác **rơi ngay lập tức từ 9.4% đến 11.4%** (1D-CNN rơi từ `96.1%` xuống `84.7%`; LSTM từ `97.4%` xuống `87.9%`; Bi-GRU từ `97.8%` xuống `88.4%`).
  4. **Chỉ ra lỗ hổng thực tế của giả định Calibration (Mục 5.2, Trang 8):** Tác giả viết rõ: phép chuẩn hóa đầu phiên giả định rằng phút đầu tiên tài xế hoàn toàn tỉnh táo; nếu một tài xế bước lên xe khi đã mệt sẵn (`Low Vigilant` hoặc `Drowsy`), việc lấy phút đầu tiên làm chuẩn $\mu_{\text{init}}$ sẽ biến trạng thái mệt mỏi thành mốc `0` (bình thường), làm tê liệt hệ thống cảnh báo!
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Đọc **Trang 5 (Bảng 1 & Mục 4.1)**: Đối chứng sự sụt giảm `-9.4% đến -11.4%` giữa Random Split và Subject-Independent Split.
  - Đọc **Trang 6 (Mục 4.4 - Per-Driver Calibration)**: Thống kê dải `EAR` cơ địa `0.198–0.305` và mức tăng `+3.9%`.
  - Đọc **Trang 8 (Mục 5.2 - Limitations, đoạn thứ 2)**: Lời thú nhận về điểm mù khi tài xế đã mệt ngay từ đầu phiên lái.

---

## BÀI 06: Ersoy et al. (Tháng 4/2026) & Xu et al. (MDPI *Information*, Tháng 4/2025)
- **Tên bài báo:** *Real-Time Driver Fatigue Detection Using Personalized EAR-MAR Thresholds and Hybrid Deep Features*
- **File PDF:** [`P4_Personalized_EAR_MAR_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P4_Personalized_EAR_MAR_2026.pdf) | **Link gốc:** https://arxiv.org/abs/2604.22479
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Cung cấp công thức ngưỡng đóng mắt cá nhân hóa siêu gọn ($\tau_{\text{EAR}} = 0.75 \times \overline{\text{EAR}}_{\text{calib}}$) chỉ cần 5 giây đầu tiên (thay vì phải đợi hết 1/3 video `Alert` dài hơn 3 phút như bài 2019), đồng thời làm rõ cách bài báo `P2` (Xu et al., 2025) xử lý tập UTA-RLDD.
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  - Bài 2019 phải đợi thu thập **1/3 tổng số lần chớp mắt của video `Alert` (~3.3 phút)** mới tính được $\mu, \sigma$ cho các đặc trưng chớp mắt.
  - Bài 2026 này (kế thừa Xu et al. 2025) chỉ lấy **5 giây đầu tiên (150 frames)** để tính độ mở mắt trung bình $\overline{\text{EAR}}_{\text{calib}}$, sau đó đặt ngưỡng mắt nhắm tại **75% độ mở mắt tự nhiên của chính người đó** ($\tau_{\text{EAR}} = 0.75 \times \overline{\text{EAR}}_{\text{calib}}$) để tính `PERCLOS` và phát hiện chớp mắt.
- **🔬 Phát hiện khoa học đắt giá nhất:**
  1. Quy tắc ngưỡng tỷ lệ **75% `EAR` và 140% `MAR`** cực kỳ trực quan về mặt sinh học: bất kể tài xế mắt to (`EAR = 0.32`) hay mắt hẹp (`EAR = 0.20`), khi mí mắt khép xuống dưới 75% mức mở bình thường của chính họ thì được tính là pha đóng mắt.
  2. Làm rõ kết quả của bài **Xu et al. (2025, `doi:10.3390/info16040294` - đạt `86.88%` trên UTA-RLDD)**: Xu et al. chỉ chọn ra **22 người trong số 60 người của UTA-RLDD** và **loại bỏ hoàn toàn lớp `Low Vigilant`**, chỉ phân loại 2 lớp (`Alert` vs `Drowsy`).
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Đọc **Trang 2 (Mục II - Related Work)**: Đoạn tổng kết về Xu et al. (2025) trên UTA-RLDD.
  - Đọc **Trang 3–4 (Mục III-B - Personalized Threshold Calibration)**: Công thức $\tau_{\text{EAR}} = 0.75 \times \overline{\text{EAR}}_{\text{calib}}$ và $\tau_{\text{MAR}} = 1.40 \times \overline{\text{MAR}}_{\text{calib}}$.

---

## BÀI 07: Anshuman Gaikwad (Manipal Institute of Technology, Tháng 10/2026)
- **Tên bài báo:** *Calibrated Multi-Cue Driver Drowsiness Detection from Facial Landmarks with Confidence-Gated Temporal Fusion*
- **File PDF:** [`P5_ResearchSquare_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P5_ResearchSquare_2026.pdf) | **Link gốc:** https://doi.org/10.21203/rs.3.rs-11416808/v1
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Đưa ra cấu trúc thiết kế thí nghiệm đối chứng (Ablation `B0–B3`) rất rõ ràng để tách bạch vai trò của Calibration và cổng kiểm soát chất lượng điểm mốc khuôn mặt (`Confidence Gate`), nhưng khi đọc toàn văn phát hiện tác giả **chưa hề chạy thật trên UTA-RLDD**.
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  - Trong bài 2019, khi tài xế cúi đầu hoặc lấy tay che mặt làm `dlib` bắt sai điểm mốc mắt, tín hiệu `EAR` bị sụt đột ngột và thuật toán tìm chớp mắt sẽ nhận nhầm đó là một nhịp chớp mắt dài (gây nhiễu đặc trưng).
  - Bài 2026 này thêm một **Cổng chất lượng khung hình $q(t) \in [0, 1]$** (dựa trên độ tin cậy phát hiện mặt và góc nghiêng đầu): nếu $q(t) < 0.7$, hệ thống **đóng băng (freeze)** không cập nhật đặc trưng ở frame bị nhiễu đó.
- **🔬 Phát hiện khoa học đắt giá nhất:**
  1. **Cách thiết kế 4 bậc Ablation (`B0` $\rightarrow$ `B3`, Mục 4.3, Trang 6):** Rất đáng học hỏi về mặt trình bày khoa học: `B0` (Không Calibration, ngưỡng cố định) $\rightarrow$ `B1` (Thêm Calibration cá nhân hóa) $\rightarrow$ `B2` (Thêm làm mượt thời gian) $\rightarrow$ `B3` (Thêm cổng chất lượng $q(t) \ge 0.7$).
  2. **Cảnh báo quan trọng khi đọc Trang 7 (Mục 5.2):** Tác giả thú nhận chưa tải và chưa chạy trên tập UTA-RLDD hay NTHU-DDD thật, mà chỉ tự sinh **9 chuỗi dữ liệu giả lập (synthetic traces)** để vẽ biểu đồ! Do đó, chỉ nên đọc bài này để tham khảo **công thức cổng chất lượng $q(t)$ và cách kẻ bảng Ablation `B0–B3`**, tuyệt đối không trích dẫn các con số kết quả giả lập của họ.
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Đọc **Trang 4–5 (Công thức 3 đến 8)**: Công thức chuẩn hóa Z-score có $\epsilon = 10^{-3}$ và cổng chất lượng $q(t)$.
  - Đọc **Trang 6 (Mục 4.3)** và **Trang 7 (Mục 5.2)**: Xem cấu trúc Ablation `B0–B3` và dòng thú nhận chưa chạy dữ liệu thật.

---

## BÀI 08: Xie & Xiao (Hunan University — *Frontiers in Neurorobotics*, Tháng 6/2026)
- **Tên bài báo:** *Real-time driver fatigue detection method based on confidence-driven adaptive time window*
- **File PDF:** [`P2_CDATW_Frontiers_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P2_CDATW_Frontiers_2026.pdf) | **Link gốc:** https://doi.org/10.3389/fnbot.2026.1857548
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Chỉ ra và giải quyết trực tiếp **điểm yếu về độ trễ cửa sổ cố định của bài báo 2019**: Thay vì bắt hệ thống lúc nào cũng phải đợi đủ một cửa sổ dài cố định (như $T = 30$ lần chớp mắt $\approx 2\text{–}3\text{ phút}$ của bài 2019), bài báo này chứng minh việc **co giãn độ dài cửa sổ tự động theo độ tự tin dự đoán (`CDATW`)** giúp vừa cảnh báo nhanh khi tín hiệu rõ, vừa giảm **35.2% báo động giả (`FAR`)** khi tín hiệu nhập nhằng!
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  | Tiêu chí | Bài báo gốc 2019 (Ghoddoosian) | Bài báo 2026 này (Xie & Xiao - CDATW) |
  | :--- | :--- | :--- |
  | **Độ dài cửa sổ quyết định** | **Cố định $T = 30$ lần chớp mắt** (~2–3 phút) cho mọi tình huống, và lấy Majority Voting trên cả video 10 phút. | **Thích nghi liên tục $W_t \in [5\text{s}, 30\text{s}]$** theo công thức: $W_t = W_{\min} + (1 - \bar{c}_t)(W_{\max} - W_{\min})$. |
  | **Xử lý khi dự đoán dao động quanh ngưỡng** | Cắt ngưỡng cứng tại `3.3` và `6.6` (nếu đầu ra nhảy `3.29` $\leftrightarrow$ `3.31` sẽ gây nhấp nháy nhãn). | Dùng **biên trễ Hysteresis $\Delta = \pm 0.05$** và thời gian duy trì trạng thái tối thiểu **$T_{\text{dwell}} = 2\text{s}$**. |
- **🔬 Phát hiện khoa học đắt giá nhất:**
  1. **Quy luật đánh đổi Cửa sổ ngắn vs. Cửa sổ dài (Bảng 4, Trang 10):**
     - Nếu đặt cửa sổ cố định quá ngắn (`5s`): Phát hiện nhanh (trễ chỉ `1.8s`) nhưng **tỷ lệ báo động giả (`FAR`) vọt lên tới `24.6%`** (vì một lần nhíu mắt hay ngáp ngắn cũng làm cả cửa sổ bị kéo sang nhãn buồn ngủ).
     - Nếu đặt cửa sổ cố định quá dài (`30s` — giống triết lý gom 30 lần chớp mắt của bài 2019): Báo động giả giảm xuống `8.5%`, nhưng **độ trễ cảnh báo quá chậm (`6.4s` sau khi đã ngủ gật)** và bỏ sót các cơn buồn ngủ chớp nhoáng.
     - Khi dùng **Cửa sổ thích nghi `CDATW` (Công thức 14, Trang 5)**: Khi mô hình tự tin cao ($\bar{c}_t \to 1$), cửa sổ tự co về `5s–10s`; khi mô hình phân vân ở giai đoạn chuyển giao ($\bar{c}_t \to 0$), cửa sổ tự giãn ra `20s–30s`. Kết quả giúp **giảm 35.2% báo động giả (`FAR` từ 14.2% xuống 9.2%)** so với cửa sổ cố định trung bình!
  2. **Điểm hạn chế khi họ chạy trên UTA-RLDD (Mục 3.1.1, Trang 6):** Dù cơ chế cửa sổ `CDATW` rất xuất sắc, nhưng khi thử nghiệm trên UTA-RLDD (đạt `89.3%`), tác giả lại **gộp `Low Vigilant` và `Drowsy` thành 1 lớp nhị phân `Fatigued`** chứ chưa dám thử trên bài toán 3 lớp nguyên bản của năm 2019.
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Đọc **Trang 4–6 (Mục 2.3 & 2.4, Công thức 10 đến 18, Hình 2)**: Toàn bộ toán học của cơ chế Cửa sổ thời gian thích nghi `CDATW` và Hysteresis.
  - Đọc **Trang 6 (Mục 3.1.1)**: Xem cách họ gộp lớp trên UTA-RLDD.
  - Đọc **Trang 10 (Bảng 4 & Hình 6)**: Bảng Ablation chứng minh hiệu quả của cửa sổ thích nghi so với cửa sổ cố định `5s / 15s / 30s`.

---

## BÀI 09: Chavan, Kaede, & Watanuki (Saitama University, Nhật Bản — *AHFE*, Tháng 7/2026)
- **Tên bài báo:** *Early Driver Drowsiness Detection Using Individually Normalized Ocular Dynamics and Dual-Attention Hierarchical BiLSTM*
- **File PDF:** [`P6_AHFE_2026_Blendshapes_BiLSTM.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/P6_AHFE_2026_Blendshapes_BiLSTM.pdf) | **Link gốc:** https://doi.org/10.54941/ahfe1007333
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Bài báo này có tên và cấu trúc **giống bài báo 2019 đến 90%** (cũng nhấn mạnh *Early Detection*, cũng dùng *Individually Normalized Ocular Dynamics* trên tập *UTA-RLDD* 5-fold), công bố đạt **`VA = 88.89%`**; nhưng khi đọc toàn văn Trang 6–8, bài báo này làm sáng tỏ **2 sự thật cực kỳ quan trọng**: (1) Con số `88.89%` thực chất là kết quả **gộp 2 lớp nhị phân (`Safe` vs `Unsafe`) tại ngưỡng `0.35`**, và (2) chính tác giả bài này đã kiểm tra lại bài của Xu et al. (2025) và phát hiện Xu et al. đã **lọc bỏ thủ công các mẫu khó** trong UTA-RLDD!
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  - **Điểm cải tiến hơn bài 2019:** Thay vì chỉ dùng 1 con số `EAR`, họ trích xuất **7 hệ số Blendshapes vùng mắt và lông mày** từ MediaPipe (`eyeBlink`, `eyeSquint` - nheo mắt, `eyeWide` - mở to mắt, `browDown` - nhíu mày, `browInnerUp`, `browOuterUp`), vì khi tài xế ở trạng thái `Low Vigilant`, họ thường cố gắng **nhướn lông mày hoặc nheo mắt** để chống lại cơn buồn ngủ!
  - **Điểm đánh tráo khái niệm ở bước chấm điểm (Trang 6–7):**
    - Bài 2019 dùng **2 ngưỡng cắt** (`3.3` và `6.6` trên thang 0–10) để bắt buộc mô hình phải phân biệt rõ **3 lớp (`Alert`, `Low Vigilant`, `Drowsy`)**, đạt `VA = 65.2%`.
    - Bài 2026 này lúc train gán nhãn `Alert = 0.0`, `Low Vigilant = 0.5`, `Drowsy = 1.0`, nhưng lúc chấm điểm `VA = 88.89%` ở Mục 2.5 & 3.2 (Trang 6–7), họ chỉ dùng **1 ngưỡng cắt duy nhất `threshold = 0.35`**: mọi video $> 0.35$ đều được tính chung là **`Unsafe` (`Low Vigilant + Drowsy`)**!
- **🔬 Phát hiện khoa học đắt giá nhất:**
  1. Chứng minh rằng ngay cả vào năm 2026, với mạng Dual-Attention Hierarchical BiLSTM và 7 đặc trưng mắt/lông mày + Calibration 2 phút đầu, các nhà nghiên cứu vẫn **phải gộp `Low Vigilant` và `Drowsy` làm một lớp nhị phân (`Unsafe`)** thì mới đạt được mức `88.89%` trên 5-fold UTA-RLDD!
  2. **Mục 3.3 (Trang 8):** Vạch trần lý do vì sao bài báo của Xu et al. (2025) đạt `86.88%`: *"Xu et al. manually filtered out ambiguous samples"* (lọc bỏ thủ công các đoạn dữ liệu nhập nhằng khó phân loại).
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Bài báo dài 10 trang, rất dễ đọc: lật ngay tới **Trang 3 (Bảng 1 - 7 đặc trưng Blendshapes mắt/lông mày)**, **Trang 6 (Mục 2.5 - đoạn quy định ngưỡng nhị phân `0.35`)**, và **Trang 7–8 (Bảng 2, Bảng 3 & Mục 3.3)**.

---

## BÀI 10: Mujtaba et al. — YawDD+ (*IEEE ICIP 2026*)
- **Tên bài báo:** *YawDD+: Frame-Level Benchmarking and Temporal-Enhanced Fine-Grained Action Detection for Driver Yawning*
- **File PDF:** [`B_YawDD_Plus_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_YawDD_Plus_2025.pdf) | **Link gốc:** https://arxiv.org/abs/2512.11446
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Giải thích bằng số liệu thống kê chính xác **tại sao cách gán 1 nhãn duy nhất cho cả video dài (Video-level annotation) như bộ dữ liệu UTA-RLDD của bài báo 2019 lại khiến độ chính xác trên từng chuỗi ngắn (`BSA = 54.0%`) luôn thấp hơn độ chính xác toàn video (`VA = 65.2%`) hơn 10%**, và tại sao lớp `Low Vigilant` hay bị đoán nhầm thành `Alert`.
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  - Trong bài 2019, mỗi video dài ~10 phút chỉ được gán **1 nhãn duy nhất (`0`, `5`, hoặc `10`)**, sau đó tác giả cắt video đó thành hàng chục chuỗi 30 lần chớp mắt và **ép mọi chuỗi con trong video đó đều phải mang cùng nhãn của cả video** khi tính hàm Loss và khi chấm điểm `BSA`!
  - Bài 2026 này tiến hành gán nhãn lại từng frame cho toàn bộ bộ dữ liệu video lái xe để kiểm tra xem trong một video mang nhãn "Mệt mỏi / Ngáp", thực sự có bao nhiêu % thời lượng tài xế biểu hiện mệt mỏi.
- **🔬 Phát hiện khoa học đắt giá nhất:**
  - Kết quả thống kê toàn bộ khung hình chứng minh: trong các video mang nhãn hành vi mệt mỏi/ngáp cấp độ video, có tới **75% đến 92.6% thời lượng thực tế tài xế đang ở trạng thái bình thường (`Neutral / Alert`)**!
  - Điều này giải sáng tỏ hoàn toàn hiện tượng trong bài báo 2019 (và trong `baseline_report.pdf` của nhóm bạn): một người ở trạng thái `Low Vigilant (5)` trong suốt 10 phút không hề chớp mắt lờ đờ ở mọi giây — có những phút họ hoàn toàn tỉnh táo (`Alert`), xen kẽ vài đợt chớp mắt chậm lại. Do đó, khi chấm điểm từng chuỗi 30-blink riêng lẻ (`BSA`), rất nhiều chuỗi thực chất là nhịp chớp mắt tỉnh táo nên chỉ đạt `54.0%`, nhưng khi gom toàn video lại bỏ phiếu (`VA`) thì tăng lên `65.2%`.
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Đọc **Trang 1–2 (Mục Introduction & Hình 1)** và **Trang 3 (Bảng 1 & Hình 2 - Thống kê tỷ lệ frame Neutral vs Action trong các video gán nhãn cấp độ video)**.

---

## BÀI 11: Essahraui et al. (MDPI *Sensors*, Tháng 2/2025)
- **Tên bài báo:** *Real-Time Driver Drowsiness Detection Using Facial Analysis and Machine Learning Techniques*
- **File toàn văn:** [`B_Sensors_2025_Essahraui_FullText.txt`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Sensors_2025_Essahraui_FullText.txt) | **Link gốc:** https://doi.org/10.3390/s25030812
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Đây là **bằng chứng phản diện (Negative Example) đắt giá nhất** giúp bạn hiểu vì sao trên Google Scholar có những bài báo năm 2025 tuyên bố đạt **98.89% – 99.97% trên chính bộ dữ liệu UTA-RLDD của bài báo 2019**, và chứng minh bằng toán học rằng các con số 99% đó hoàn toàn là **nhận diện khuôn mặt do rò rỉ dữ liệu (Frame-Level Data Leakage)**.
- **⚖️ Đối chiếu trực diện với Bài báo 2019:**
  - Bài 2019 chia 60 tình nguyện viên thành **5 folds độc lập theo từng người** (48 người Train, 12 người Test hoàn toàn mới).
  - Bài 2025 này tải bộ UTA-RLDD về, trích xuất các khung hình từ các video, dùng Haar Cascade cắt khuôn mặt ra, rồi **gộp chung tất cả khung hình của cả 60 người lại và chia ngẫu nhiên Train/Test theo từng khung hình**!
- **🔬 Phát hiện khoa học đắt giá nhất khi đọc toàn văn:**
  1. **Con số tự tố cáo ở Bảng 7 & Bảng 10:** Tác giả khoe rằng trên tập UTA-RLDD, thuật toán láng giềng gần nhất **`k-NN` với $k = 1$ đạt độ chính xác `98.89%`**, `Random Forest` đạt `99.51%`, và `CNN` đạt `99.97%`!
  2. **Tại sao con số `1-NN = 98.89%` lại là bằng chứng thép của Data Leakage?** Thuật toán `1-NN` ($k=1$) không hề học bất kỳ quy luật sinh học nào — nó chỉ lấy bức ảnh mặt đang xét trong tập Test, đi tìm **1 bức ảnh có pixel giống hệt nhất trong tập Train** và copy nhãn sang! Để `1-NN` đoán đúng `98.89%` trên 3 lớp của UTA-RLDD, điều kiện cần và đủ là **với mọi frame trong tập Test, luôn có một frame cách đó vài phần mười giây của cùng người đó, trong cùng video đó nằm sẵn trong tập Train**!
  3. **Bằng chứng cẩu thả học thuật (Dòng 59, Mục 3.4.1):** Tác giả thậm chí còn quên xóa câu *"distinguish between cheating and non-cheating behaviors"* khi copy-paste từ bài báo gian lận thi cử trước đó của họ sang bài báo phát hiện buồn ngủ này.
- **📖 Chỉ dẫn đọc nhanh trong file:**
  - Mở [`B_Sensors_2025_Essahraui_FullText.txt`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Sensors_2025_Essahraui_FullText.txt), tìm (`Ctrl + F`) từ khóa **`3.1.4`** (xem cách họ trộn frame), **`98.89`** (Bảng 7 - kết quả `k-NN` $k=1$), **`99.97`** (Bảng 10 - kết quả `CNN`), và **`cheating`** (lỗi copy-paste).

---

## BÀI 12: Nakagama et al. (*IEEE Intelligent Vehicles Symposium - IV 2025*, Tháng 6/2025)
- **Tên bài báo:** *Evaluating the Generalization of Driver Drowsiness Detection Models Across Datasets*
- **File PDF:** [`B_Nakagama_2025_Reproducibility_Leakage.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/pdf_bai_bao/B_Nakagama_2025_Reproducibility_Leakage.pdf) | **Link gốc:** https://arxiv.org/abs/2506.07014
- **🎯 Đúc kết 1 câu (Đóng góp cho bài 2019):** Giải thích hiện tượng mà nhóm bạn gặp phải trong [`baseline_report.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/baseline_report.pdf) khi tái lập bài báo 2019: **Tại sao lấy checkpoint có sẵn của tác giả (`R0`) thì đạt `64.9%`, nhưng khi tự huấn luyện lại từ đầu (`R1`) thì chỉ đạt `53.7% ± 2.0%`?**
- **🔬 Phát hiện khoa học đắt giá nhất:**
  - Nhóm nghiên cứu Nhật Bản này thực hiện đúng công việc mà nhóm bạn đang làm: lấy các mô hình phát hiện buồn ngủ đã công bố trên các hội nghị/tạp chí (vốn báo cáo độ chính xác từ **91% đến 98%**), sau đó **tự huấn luyện và đánh giá lại từ đầu (re-train from scratch)** dưới quy trình kiểm định nghiêm ngặt không rò rỉ dữ liệu và không chọn lọc thủ công trên tập Test.
  - **Kết quả (Bảng II & Bảng III, Trang 4–5):** Toàn bộ các mô hình đình đám đó khi huấn luyện lại trung thực đều **rơi về vùng độ chính xác `51% – 70%`** (AUC chỉ quanh mức `0.52 – 0.53` khi sang người lái mới)!
- **📖 Chỉ dẫn đọc nhanh trong PDF:**
  - Bài báo dài 6 trang chuẩn IEEE: đọc ngay **Trang 2 (Mục II - Vấn đề Data Leakage & Chọn mô hình trên tập Test)** và **Trang 4–5 (Bảng II, Bảng III - Sự sụt giảm từ >90% xuống 51%–70% khi tái lập trung thực)**.

---

# PHẦN II: 8 BÀI BÁO TRONG THƯ MỤC `luu_tru_phu/pdf_phu_tham_khao/` (ĐỌC KHI CẦN ĐÀO SÂU THÊM TỪNG KHÍA CẠNH PHỤ)

> 8 bài báo dưới đây được tách sang thư mục phụ vì chúng không trực tiếp giải bài toán chuỗi chớp mắt trên UTA-RLDD như 12 bài ở Phần I, nhưng mỗi bài lại cung cấp **một phát hiện bổ trợ rất rõ ràng** khi đặt cạnh bài báo 2019:

---

## BÀI 13: Hassan et al. (*Artificial Intelligence Review* Q1, Tháng 5/2026)
- **File PDF:** [`B_Survey_AI_Review_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_Survey_AI_Review_2026.pdf) | **Link gốc:** https://doi.org/10.1007/s10462-026-11505-w
- **🎯 Đóng góp/Phát hiện gì so với bài 2019?**
  - Bài báo 2019 chỉ đánh giá mô hình bằng 4 chỉ số (`BSA`, `VA`, `BSRE`, `VRE`) trên 1 lần chạy duy nhất.
  - Bài tổng quan Q1 dài 83 trang này tổng kết 185 bài báo (2018–2025) và chỉ ra rằng: trong bài toán phát hiện buồn ngủ thực tế, chỉ nhìn vào `Accuracy` là chưa đủ vì một hệ thống có `Accuracy = 70%` nhưng báo động giả liên tục sẽ bị tài xế tắt bỏ ngay. Bài báo thiết lập chuẩn đánh giá mới gồm: **Khoảng tin cậy qua nhiều lần chạy (`mean ± std` — chính là cách nhóm bạn báo cáo `R1 = 53.7% ± 2.0%`)**, **`Macro-F1`**, **Tỷ lệ báo động giả (`FAR`)** và **Độ trễ phát hiện (`Detection Latency`)**.
- **📖 Đọc trang nào?** Chỉ cần xem các bảng tổng hợp phương pháp và mục *Evaluation Metrics & Open Challenges* (Trang 55–68).

---

## BÀI 14: Theivadas et al. (Tháng 8/2026)
- **File PDF:** [`P7_Leakage_Resistant_Calibrated_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/P7_Leakage_Resistant_Calibrated_2026.pdf) | **Link gốc:** https://doi.org/10.21203/rs.3.rs-10574400/v1
- **🎯 Đóng góp/Phát hiện gì so với bài 2019?**
  - Chỉ ra **lỗi rò rỉ ngầm trong code huấn luyện của bài báo 2019**: Trong file `drowsiness_detection.py` của Ghoddoosian 2019, tác giả chỉ chia dữ liệu thành 2 tập (`Train` và `Test`), sau đó ở mỗi epoch đều đem tập `Test` ra chấm điểm và chọn lưu cấu hình/epoch có điểm `Test` cao nhất (khiến `R0 = 64.9%` cao hơn hẳn mức trung bình `R1 = 53.7%` ở epoch 80).
  - Bài báo này chuẩn hóa quy trình chống rò rỉ bằng cách bắt buộc chia thành **3 tập độc lập hoàn toàn về người lái**: `I_fit` (để train trọng số), `I_cal` (Validation riêng để chọn epoch dừng sớm và chọn ngưỡng phân loại), và `I_test` (chỉ mở ra chấm đúng 1 lần cuối cùng).
- **📖 Đọc trang nào?** Đọc **Trang 3–5 (Mục 2.2 - Three-Way Subject-Disjoint Split `I_fit / I_cal / I_test`)**.

---

## BÀI 15: Jang et al. (Tháng 11/2025)
- **File PDF:** [`B_TTA_CalibrationFree_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_TTA_CalibrationFree_2025.pdf) | **Link gốc:** https://arxiv.org/abs/2511.22030
- **🎯 Đóng góp/Phát hiện gì so với bài 2019?**
  - Trả lời câu hỏi: *"Tại sao để bỏ giả định lấy 1/3 đầu video `Alert` của bài 2019, ta không dùng luôn trung bình trượt liên tục (Running Mean/Std) cập nhật theo từng phút khi xe đang chạy?"*
  - Bài báo này chứng minh bằng thực nghiệm rằng: vì trạng thái buồn ngủ kéo dài liên tục hàng chục phút (temporally correlated stream), nếu bạn cập nhật $\mu_t, \sigma_t$ liên tục ở mọi thời điểm, khi tài xế bắt đầu buồn ngủ, bộ chuẩn hóa sẽ **tự động lấy chính các nhịp chớp mắt buồn ngủ đó làm mốc chuẩn bình thường mới**, làm xóa sạch dấu hiệu buồn ngủ và khiến **F1-score sập từ `67.23%` xuống chỉ còn `6.46%`**! Muốn cập nhật trực tuyến, bắt buộc phải có bộ lọc chỉ cập nhật ở các mẫu có độ tự tin tỉnh táo cao (Selective Updating).
- **📖 Đọc trang nào?** Đọc **Trang 2–3 (Hình 1 & Mục II-B)** và **Trang 6 (Bảng Ablation so sánh Naive Running Normalization `6.46%` vs Selective TTA `67.23%`)**.

---

## BÀI 16: Bodaghi et al. — Bộ Dữ Liệu UL-DD (*Nature Scientific Data*, Tháng 1/2026)
- **File PDF:** [`B_UL_DD_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_UL_DD_2026.pdf) | **Link gốc:** https://doi.org/10.1038/s41597-025-06540-1
- **🎯 Đóng góp/Phát hiện gì so với bài 2019?**
  - Chỉ ra **hạn chế trong thiết kế thu thập dữ liệu của UTA-RLDD (2019)**: UTA-RLDD quay 3 video rời rạc (mỗi video 10 phút) và chỉ hỏi điểm buồn ngủ KSS 1 lần cho cả 10 phút đó. Bộ dữ liệu mới **UL-DD (2026)** quay liên tục 40 phút và hỏi điểm KSS **mỗi 4 phút/lần** để bắt chính xác quá trình chuyển giao từ tỉnh sang chớm buồn ngủ.
  - **Phát hiện quan trọng ở mục Technical Validation (Trang 8–10):** Ngay cả trên bộ dữ liệu mới năm 2026 của tạp chí *Nature*, khi đánh giá 5-fold độc lập người lái và **chỉ dùng camera hình ảnh khuôn mặt (Unimodal Visual)**, độ chính xác cũng chỉ đạt **52% – 68%** (chứng minh con số `53.7% – 65.2%` của bài 2019 là giới hạn tự nhiên của phương thức chỉ dùng hình ảnh đơn thuần!).
- **📖 Đọc trang nào?** Đọc **Trang 2 (Bảng 1 - So sánh UTA-RLDD với UL-DD)** và **Trang 9 (Bảng kết quả 5-fold CV Unimodal vs Multimodal)**.

---

## BÀI 17: Ren et al. — LiteFat (Tháng 8/2025)
- **File PDF:** [`B_LiteFat_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_LiteFat_2025.pdf) | **Link gốc:** https://arxiv.org/abs/2507.21756
- **🎯 Đóng góp/Phát hiện gì so với bài 2019?**
  - Giải thích vì sao mạng **4-layer HM-LSTM** của bài báo 2019 lại khó huấn luyện, nhạy cảm với khởi tạo ngẫu nhiên (`R1` dao động $\pm 2.0\%$) và dễ bị overfit trên tập dữ liệu nhỏ (chỉ có 8,661 chuỗi): vì HM-LSTM dùng biến cổng nhị phân rời rạc ($z_t^l \in \{0, 1\}$) phải xấp xỉ đạo hàm bằng Straight-Through Estimator.
  - Bài báo này chứng minh việc thay thế các mạng RNN/LSTM phức tạp bằng mạng **Tích chập thời gian nhân quả giãn nở (Dilated Causal TCN)** giúp huấn luyện ổn định hơn nhiều, song song hóa nhanh và chỉ tốn **0.296 triệu tham số**.
- **📖 Đọc trang nào?** Đọc **Trang 4–5 (Mục III-C - Kiến trúc Dilated Causal TCN cho chuỗi thời gian dài)**.

---

## BÀI 18: Light-VTD (*Nature Scientific Reports*, Tháng 3/2026)
- **File PDF:** [`B_LightVTD_2026.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_LightVTD_2026.pdf) | **Link gốc:** https://doi.org/10.1038/s41598-026-41847-y
- **🎯 Đóng góp/Phát hiện gì so với bài 2019?**
  - **Đóng góp kỹ thuật:** Trong bài 2019, nhiều video UTA-RLDD quay trong phòng tối hoặc ngược sáng khiến `dlib` không bắt được mặt. Bài này chứng minh tiền xử lý ảnh bằng thuật toán cân bằng sáng thích nghi **`CLAHE`** trước khi nhận diện mặt giúp tăng **+2.4% độ chính xác** trên UTA-RLDD.
  - **Phát hiện lỗi phương pháp ở Trang 8:** Bài báo khoe đạt **`97.6%` trên UTA-RLDD**, nhưng khi đọc Mục *Benchmark datasets and preprocessing* (Trang 8), hóa ra họ chỉ cắt ra **11,787 frames**, bỏ lớp `Low Vigilant` để gộp thành **2 lớp** (`Active` = 7,230 frames vs `Fatigue` = 4,557 frames) và chia ngẫu nhiên theo frame!
- **📖 Đọc trang nào?** Đọc **Trang 8 (Mục Dataset preprocessing - xem cách họ rút 11,787 frames từ UTA-RLDD)** và **Trang 13 (Bảng Ablation của bước tiền xử lý CLAHE)**.

---

## BÀI 19: Essahraui et al. — FastKAN (*PLOS ONE*, Tháng 11/2025)
- **File PDF:** [`B_FastKAN_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_FastKAN_2025.pdf) | **Link gốc:** https://doi.org/10.1371/journal.pone.0332577
- **🎯 Đóng góp/Phát hiện gì so với bài 2019?**
  - Tiếp nối Bài 11: Nhóm tác giả này dùng mạng MobileNetV2 + FastKAN trên các frame chia ngẫu nhiên của UTA-RLDD và khoe đạt **`99.94%`**.
  - **Phát hiện đắt giá nhất:** Khi họ thử nén mô hình từ dấu phẩy động 32-bit (`FP32`) xuống số nguyên 8-bit (`INT8 Post-Training Quantization - PTQ`), độ chính xác trên UTA-RLDD **sập từ `99.94%` xuống chỉ còn `48.86%`**! Điều này chứng minh mặt phẳng phân lớp của mô hình `99.94%` kia thực chất là những đường ranh giới cực kỳ sắc nhọn và mong manh dùng để **học vẹt từng giá trị pixel nền/khuôn mặt** của các frame bị rò rỉ giữa tập Train và tập Test, nên chỉ cần làm tròn trọng số một chút là sụp đổ hoàn toàn!
- **📖 Đọc trang nào?** Đọc **Trang 14–15 (Bảng kết quả Quantization `FP32 = 99.94%` sập xuống `PTQ INT8 = 48.86%`)**.

---

## BÀI 20: Hassan et al. (*Nature Scientific Reports*, Tháng 5/2025)
- **File PDF:** [`B_ViT_SciRep_2025.pdf`](file:///d:/Git/test/ScientificMethod/SC_25A01_Group05/tong_hop_bai_bao_chuyen_sau/luu_tru_phu/pdf_phu_tham_khao/B_ViT_SciRep_2025.pdf) | **Link gốc:** https://doi.org/10.1038/s41598-025-02111-x
- **🎯 Đóng góp/Phát hiện gì so với bài 2019?**
  - Bài báo này thử dùng mạng Vision Transformer (ViT / Swin) khổng lồ để phân loại buồn ngủ chỉ từ **từng bức ảnh cắt vùng mắt tĩnh (Static Eye ROI)**.
  - **Phát hiện khẳng định giá trị của bài báo 2019:** Phần kết luận của chính bài báo này thừa nhận rằng dù mạng ViT có mạnh đến đâu, một bức ảnh tĩnh chụp mắt đang nhắm không bao giờ phân biệt được tài xế đang **chớp mắt sinh lý bình thường (kéo dài 0.1–0.2 giây)** hay đang **ngủ gật (kéo dài >0.5 giây)**, và hoàn toàn bất lực trước trạng thái chớm buồn ngủ (`Low Vigilant`). Qua đó khẳng định cách tiếp cận **Mô hình hóa chuỗi thời gian của các nhịp chớp mắt (Temporal Blink Sequence)** của Ghoddoosian 2019 là hướng đi bắt buộc nếu muốn phát hiện buồn ngủ sớm.
- **📖 Đọc trang nào?** Chỉ cần xem **Trang 11–12 (Mục Discussion & Limitations về giới hạn của phân loại ảnh tĩnh so với chuỗi thời gian)**.
