# CẨM NANG TỪ KHÓA (KEYWORDS) VÀ CÁCH TÌM KIẾM, THẨM ĐỊNH BÀI BÁO KHOA HỌC

> Tài liệu này hướng dẫn chi tiết cách nhóm bạn tự tìm kiếm thêm các bài báo mới, cách truy vết xem một bài báo cổ điển (như bài Ghoddoosian 2019) đã được các nhóm nghiên cứu năm 2025–2026 kế thừa/giải quyết tới đâu, và quy trình 5 bước đọc toàn văn (Full-Text) để không bị "đánh lừa" bởi những bài báo công bố độ chính xác ảo.

---

## 1. Ma Trận Từ Khóa (Keyword Matrix) Theo Từng Mảnh Ghép Của Đề Tài

Khi tìm kiếm trên mạng, nếu chỉ gõ chung chung `"driver drowsiness detection"`, bạn sẽ bị ngập trong hàng chục ngàn bài báo dùng CNN/YOLO phân loại ảnh mắt nhắm/mở đơn giản. Để tìm trúng các bài giải quyết đúng **3 khoảng trống (Gap A, B, C)** trên tập **UTA-RLDD**, hãy ghép các từ khóa theo bảng ma trận dưới đây:

| Nhóm chủ đề | Từ khóa chính xác (Primary Keywords) | Từ khóa kết hợp chuyên sâu (Secondary / Technical Terms) |
| :--- | :--- | :--- |
| **1. Truy vết trực tiếp bài gốc 2019 & Bộ dữ liệu** | `"UTA-RLDD"`<br>`"Real-Life Drowsiness Dataset"`<br>`"Ghoddoosian"`<br>`"HM-LSTM"` | `"Low Vigilant"` (Từ khóa vàng để lọc các bài có làm 3-class)<br>`"early drowsiness detection"`<br>`"5-fold"` OR `"subject-independent"`<br>`"Blink Sequence Accuracy"` OR `"Video Accuracy"` |
| **2. GAP A: Hiệu chuẩn cá nhân hóa (Calibration & Subject-Independence)** | `"personalized calibration"`<br>`"individual calibration"`<br>`"driver-specific threshold"`<br>`"adaptive threshold"` | `"inter-subject variability"` (Biến thiên giữa các cá nhân)<br>`"anatomical variation"` (Khác biệt giải phẫu mắt)<br>`"unsupervised calibration"` OR `"calibration-free"`<br>`"test-time adaptation"` OR `"domain adaptation"`<br>`"Gaussian Mixture Model"` OR `"baseline normalization"` |
| **3. GAP B: Động học chớp mắt & Chuẩn hóa tốc độ khung hình (Blink Kinematics & VFR)** | `"blink dynamics"`<br>`"blink kinematics"`<br>`"eyelid closure velocity"`<br>`"reopening velocity"` | `"variable frame rate"` OR `"frame rate normalization"`<br>`"closing duration"` AND `"reopening duration"`<br>`"Eyelid Angle"` OR `"ELA"`<br>`"PERCLOS"` AND `"blink amplitude"`<br>`"Soukupova"` (Tác giả bài EAR 2016) |
| **4. GAP C: Cửa sổ thời gian thích nghi & Độ trễ quyết định (Adaptive Window & Latency)** | `"adaptive time window"`<br>`"decision latency"`<br>`"observation window"`<br>`"early prediction"` | `"accuracy-latency trade-off"`<br>`"confidence-driven"`<br>`"Monte Carlo dropout"` OR `"epistemic uncertainty"`<br>`"exponentially weighted moving average"` OR `"EWMA"`<br>`"false alarm rate"` AND `"hysteresis"` |
| **5. Phát hiện lỗi Rò rỉ dữ liệu (Data Leakage / Evaluation Protocol)** | `"subject-independent"`<br>`"cross-subject"`<br>`"leave-one-subject-out"` (`"LOSO"`) | `"data leakage"` OR `"subject leakage"`<br>`"frame-level split"` vs `"subject-disjoint"`<br>`"video-level annotation"` OR `"label noise"` |

---

## 2. Các Câu Lệnh Truy Vấn Boolean (Copy & Paste Trực Tiếp)

Bạn có thể copy nguyên văn các chuỗi truy vấn (Search Strings) dưới đây dán vào thanh tìm kiếm của **Google Scholar** (https://scholar.google.com), **Semantic Scholar** (https://www.semanticscholar.org), hoặc **arXiv** (https://arxiv.org/search/advanced):

### Truy vấn 1: Tìm các bài báo mới nhất (2024–2026) chạy trên UTA-RLDD và có xét lớp `Low Vigilant` (3-class)
```text
"UTA-RLDD" AND ("Low Vigilant" OR "three-class" OR "3-class") AND ("blink" OR "EAR" OR "temporal")
```
*(Mẹo trên Google Scholar: Sau khi bấm tìm kiếm, nhìn sang cột bên trái chọn **"Since 2025"** hoặc **"Custom range: 2024 - 2026"** để lọc bài mới nhất).*

### Truy vấn 2: Tìm các bài làm về Hiệu chuẩn cá nhân hóa (Personalized / Individual Calibration) cho `EAR`/`MAR`
```text
("driver drowsiness" OR "driver fatigue") AND ("individual calibration" OR "personalized calibration" OR "personalized threshold" OR "adaptive threshold") AND ("EAR" OR "Eye Aspect Ratio" OR "blink")
```

### Truy vấn 3: Tìm các bài phân tích Động học chớp mắt (Vận tốc đóng/mở mắt, thời lượng tính theo ms, ảnh hưởng của FPS)
```text
("driver drowsiness" OR "fatigue detection") AND ("blink dynamics" OR "blink kinematics" OR "opening velocity" OR "closing duration" OR "reopening") AND ("EAR" OR "eyelid")
```

### Truy vấn 4: Tìm các bài giải quyết Cửa sổ thời gian thích nghi & Độ trễ cảnh báo (Adaptive Time Window / Latency)
```text
("driver drowsiness" OR "driver fatigue") AND ("adaptive time window" OR "adaptive window" OR "window length" OR "decision latency") AND ("confidence" OR "false alarm" OR "real-time")
```

### Truy vấn 5: Tìm các bài chứng minh sự sụt giảm độ chính xác giữa Random Split và Subject-Independent Split
```text
("driver drowsiness" OR "NTHU-DDD" OR "UTA-RLDD") AND ("subject-independent" OR "cross-subject") AND ("random split" OR "data leakage" OR "inter-subject")
```

---

## 3. Cách Tìm Chính Xác Từng Bài Báo Đã Tổng Hợp Trong Thư Mục Này

Nếu bạn muốn tải lại bản gốc PDF hoặc kiểm tra thông tin trích dẫn (BibTeX) của bất kỳ bài nào trong 14 bài báo đã được phân tích trong thư mục này, hãy dùng tên hoặc mã `arXiv` / `DOI` dưới đây:

| STT | Tên bài báo cần tìm | Từ khóa gõ nhanh (100% ra ngay kết quả đầu tiên) | Mã định danh trực tiếp (`arXiv` / `DOI` / `PMCID`) |
| :-: | :--- | :--- | :--- |
| **0** | **Bài gốc 2019:** Ghoddoosian et al. (CVPRW 2019) | `"A Realistic Dataset and Baseline Temporal Model for Early Drowsiness Detection"` | `arXiv:1904.07312` |
| **1** | **Top 1:** Wolter et al. (11/2025) - 3D Eyelid Angle & VFR | `"Blinking Beyond EAR: A Stable Eyelid Angle Metric for Driver Drowsiness"` | `arXiv:2511.19519` |
| **2** | **Top 2:** Sobirov & Hamidov (07/2026) - Calibration 60s | `"Subject-Independent Model and Individual Calibration Algorithms for Determining Driver Drowsiness"` | `doi:10.5281/zenodo.21524614` |
| **3** | **Top 3:** Xie & Xiao (06/2026) - Cửa sổ thích nghi CDATW | `"Confidence-driven adaptive time window for real-time driver fatigue detection"` | `doi:10.3389/fnbot.2026.1857548` |
| **4A** | **Top 4A:** Xu et al. (04/2025) - Hybrid CNN + Landmarks | `"Detecting Driver Drowsiness Using Hybrid Facial Features and Ensemble Learning"` | `doi:10.3390/info16040294` |
| **4B** | **Top 4B:** Ersoy et al. (04/2026) - Ngưỡng 75% EAR / 140% MAR | `"Improving Driver Drowsiness Detection via Personalized EAR/MAR Thresholds"` | `arXiv:2604.22479` |
| **5A** | **Top 5A:** Gaikwad (10/2026) - Adaptive Risk Scoring & B0-B3 | `"Personalized Temporal Fatigue Analysis and Adaptive Risk Scoring for Camera-Based Driver Monitoring"` | `doi:10.21203/rs.3.rs-11416808/v1` |
| **5B** | **Top 5B:** FEM-PDNet (10/2026) - Profile-Driven Calibration | `"FEM-PDNet" "drowsiness"` | `doi:10.3390/electronics15204838` |
| **6** | **Dự phòng 1:** Mujtaba et al. (12/2025) - YawDD+ Label Noise | `"YawDD+: Frame-level Annotations for Accurate Yawn Recognition"` | `arXiv:2512.11446` |
| **7** | **Dự phòng 2:** Bodaghi et al. (2026) - UL-DD Multimodal Dataset | `"UL-DD: A Multimodal Drowsiness Dataset Using Video, Biometric Signals"` | `arXiv:2507.13403` / `doi:10.1038/s41597-025-06540-1` |
| **8** | **Dự phòng 3:** Jang et al. (11/2025) - Calibration-Free TTA | `"Calibration-Free EEG-based Driver Drowsiness Detection with Online Test-Time Adaptation"` | `arXiv:2511.22030` |
| **9** | **Dự phòng 4:** Ren et al. (08/2025) - LiteFat Graph + TCN | `"LiteFat: Lightweight Spatio-Temporal Graph Learning for Real-Time Driver Fatigue Detection"` | `arXiv:2507.21756` |
| **10** | **Dự phòng 5:** Light-VTD (03/2026) - Swin ViT + CLAHE | `"Domain-robust vision transformer with hierarchical swin encoding for explainable low-latency"` | `doi:10.1038/s41598-026-41847-y` (`PMC13554065`) |
| **11** | **Dự phòng 6:** Hassan et al. (05/2025) - ViT Drowsiness | `"Real-time driver drowsiness detection using transformer architectures"` | `doi:10.1038/s41598-025-02111-x` (`PMC12092738`) |
| **12** | **Dự phòng 7 (Mẫu lỗi Leakage):** Essahraui et al. (02/2025) | `"Real-Time Driver Drowsiness Detection Using Facial Analysis and Machine Learning Techniques"` | `doi:10.3390/s25030812` (`PMC11819803`) |
| **13** | **Dự phòng 8 (Mẫu lỗi Leakage):** FastKAN-DDD (11/2025) | `"FastKAN-DDD: A novel fast Kolmogorov-Arnold network-based approach"` | `doi:10.1371/journal.pone.0332577` |

---

## 4. Kỹ Thuật Truy Vết Trích Dẫn Ngược & Xuôi (Forward & Backward Snowballing)

Làm sao để biết **tất cả các bài báo trên thế giới đã từng giải bài toán của Ghoddoosian (2019)** mà không bỏ sót bài nào? Đừng chỉ tìm bằng từ khóa — hãy dùng kỹ thuật **Forward Citation Tracking (Truy vết trích dẫn xuôi)**:

1. **Bước 1:** Lên Google Scholar hoặc Semantic Scholar, tìm bài gốc:
   `"A Realistic Dataset and Baseline Temporal Model for Early Drowsiness Detection"` (Ghoddoosian, Galib, Athitsos, 2019).
   *(Hoặc trên cơ sở dữ liệu OpenAlex, bài báo này có mã định danh cố định là `W2936027599`).*
2. **Bước 2:** Bấm vào nút **"Cited by ..."** (Được trích dẫn bởi ~210+ bài báo).
3. **Bước 3:** Tích vào ô **"Search within citing articles"** (Tìm kiếm bên trong các bài trích dẫn bài này) trên Google Scholar.
4. **Bước 4:** Gõ từ khóa lọc vào thanh tìm kiếm con đó:
   - Muốn xem ai đã giải bài toán **Calibration** trên UTA-RLDD: gõ `"calibration" OR "personalized"`
   - Muốn xem ai đã giữ đúng **3 lớp (`Low Vigilant`)**: gõ `"Low Vigilant"`
   - Muốn xem ai đã cải tiến **đặc trưng chớp mắt (`Velocity` / `Duration`)**: gõ `"opening velocity" OR "blink duration"`
   - Chọn bộ lọc năm **2025 – 2026**.

Bằng cách này, 100% các bài báo mới nhất có sử dụng bộ dữ liệu UTA-RLDD hoặc so sánh với Ghoddoosian (2019) sẽ hiện ra ngay lập tức mà không bị lẫn rác!

---

## 5. Quy Trình 5 Bước "Đọc Thẩm Định Toàn Văn" Trong 3 Phút (Tránh Bẫy Độ Chính Xác Ảo)

Khi tìm được một bài báo mới, **TUYỆT ĐỐI KHÔNG tin ngay con số Accuracy trong Abstract**. Hãy tải file PDF toàn văn về và dùng `Ctrl + F` kiểm tra 5 điểm sau đây trong mục *Methodology / Experimental Setup*:

1. **Kiểm tra số lượng lớp (Class Count Check):**
   - `Ctrl + F` tìm từ `"Low Vigilant"` hoặc `"three classes"` hoặc `"binary"`.
   - Nếu bài báo gộp `Low Vigilant + Drowsy` hoặc bỏ `Low Vigilant` để chỉ phân loại 2 lớp (`Alert` vs. `Drowsy`), hãy ghi chú ngay: *"Bài này giải bài toán 2-class (dễ hơn ~20–28% so với bài toán 3-class gốc)"*.
2. **Kiểm tra cách chia tập Train/Test (Data Split / Leakage Check):**
   - `Ctrl + F` tìm từ `"split"`, `"fold"`, `"subject"`, `"frames"`.
   - Nếu bài báo viết: *"We extracted X frames from the videos and randomly split them into 80% training and 20% testing"* mà **không** nói rõ là chia theo đối tượng (Subject-independent / Subject-disjoint / 5-fold of 12 subjects), thì bài báo đó **bị Data Leakage 100%**.
3. **Kiểm tra giả định Calibration (Calibration Label Assumption Check):**
   - Nếu bài báo có bước chuẩn hóa theo từng tài xế, hãy đọc xem họ lấy dữ liệu chuẩn hóa từ đâu. Nếu họ lấy từ đoạn video đã được gán nhãn sẵn là `Alert` (như Ghoddoosian 2019 hay Sobirov 2026), hãy chỉ ra rằng ngoài thực tế khi xe mới khởi hành, hệ thống không hề có nhãn Ground-Truth đó.
4. **Kiểm tra đơn vị của Đặc trưng thời gian (FPS & Physical Unit Check):**
   - Kiểm tra xem thời lượng chớp mắt (`Duration`) và vận tốc (`Velocity`) được tính theo **số khung hình (`frames`)** hay theo **thời gian vật lý (`ms` / `seconds`)**. Trên tập UTA-RLDD (169/182 video bị biến thiên FPS từ 12–30 Hz), mọi đặc trưng tính theo `frame` đều bị nhiễu nặng.
5. **Kiểm tra tính xác thực của Bảng kết quả (Real vs. Synthetic / Typo Check):**
   - Đọc kỹ phần chú thích bảng biểu và mục *Limitations / Threats to Validity* ở gần cuối bài (như trường hợp bài Gaikwad 10/2026 thú nhận ở trang 7 là mới chạy trên dữ liệu giả lập chứ chưa chạy trên UTA-RLDD thật, hay bài Essahraui 2025 copy-paste nhầm chữ *"cheating and non-cheating"* ở mục 3.4.1).

