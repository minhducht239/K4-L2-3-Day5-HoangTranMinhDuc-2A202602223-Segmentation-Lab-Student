# Mẫu tham khảo để điền REPORT.md

**Cách dùng:** Bản cần nộp đã có sẵn ở [`REPORT.md`](../REPORT.md) trong thư mục gốc của fork; mở file đó và điền vào chỗ `…`. File này giải thích từng mục và có ví dụ để tham khảo khi bạn bị kẹt. Giữ nguyên bốn mục và bảng để coach đọc bài nhanh; **không chép ví dụ thành câu trả lời của mình**.

- Mã học viên theo lớp: 2A202602223
- Ngày / CVAT local: 17/9/2026
- Công cụ đã dùng: Brush / Polygon / Intelligent Scissors / gợi ý tự động có sẵn / khác: Brush, Polygon

Mã học viên là mã lớp cấp, không cần ghi họ tên trong bản nộp nếu kênh lớp đã nhận diện bạn. Ở dòng công cụ, giữ lại những công cụ bạn thật sự dùng; không có SAM cũng hoàn toàn bình thường.

## 1. Bài đã nộp

**Bạn cần điền gì?** “File ZIP đúng tên” là tên file bạn đã tải từ CVAT rồi đặt lại, ví dụ `easy_semantic.zip`. “Hoàn thành mấy ảnh” là số ảnh bạn đã vẽ và Save, không phải số ảnh có trong task. Chưa làm hoặc export lỗi thì ghi `chưa có`, đừng ghi tên một ZIP rỗng. Cột điểm là **điểm tối đa của task**, không phải điểm tự chấm.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic | 1 | 3 / 3 | 20 |
| medium_instance | 1 | 3 / 3 | 32 |
| hard_panoptic | 1 | 2 / 2 | 30 |
| cp1_holes | 1 | 1 / 1 | 3 |
| cp2_slice | 1 | 1 / 1 | 3 |
| cp5_occlusion | 1 | 1 / 1 | 3 |
| cp3_thin | 1 | 1 / 1 | 3 |
| cp4_curb | 1 | 1 / 1 | 3 |
| cp6_coverage | 1 | 1 / 1 | 3 |
| easy_semantic | easy_semantic.zip | 3 / 3 | 20 |
| medium_instance | medium_instance.zip | 3 / 3 | 32 |
| hard_panoptic | hard_panoptic.zip | 2 / 2 | 30 |
| cp1_holes | cp1_holes.zip | 1 / 1 | 3 |
| cp2_slice | cp2_slice.zip | 1 / 1 | 3 |
| cp5_occlusion | cp5_occlusion.zip | 1 / 1 | 3 |
| cp3_thin | cp3_thin.zip | 1 / 1 | 3 |
| cp4_curb | cp4_curb.zip | 1 / 1 | 3 |
| cp6_coverage | cp6_coverage.zip | 1 / 1 | 3 |
| **Tổng tối đa** | | | **100** |

Không tự điền điểm nếu chưa có phản hồi từ người chấm. Nếu export lỗi, ghi task, trạng thái Save và thông báo đã gửi coach.

Ví dụ cách ghi lỗi export: “`cp3_thin`: đã Save 1/1 ảnh, CVAT không hiện Segmentation mask 1.1 lúc 14:10, đã báo coach”. Bạn vẫn ghi đúng tình trạng, không tự đổi format.

## 2. Một quyết định trước khi dùng gợi ý

**Mục này hỏi cách bạn tự ra quyết định.** Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi mở bất kỳ đề xuất tự động nào cho object đó. “Vị trí” chỉ cần mô tả đủ để tìm lại, chẳng hạn “xe bên trái, nửa dưới ảnh”; nếu nhớ tên file JPG thì ghi luôn. “Quy tắc biên” nghĩa là lý do bạn dừng mask ở đâu, nhất là mép ảnh hoặc vật che. Không cần ảnh chụp riêng nếu lớp không yêu cầu.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: person ở giữa khung
- Class và quy tắc tôi dùng để chọn biên: class person
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: vùng gợi ý sai, lý do sửa là do bị mark cả chân của người ở cạnh
- Class và quy tắc tôi dùng để chọn biên: class person, vẽ sát theo phần nhìn thấy của cơ thể
- Nếu dùng gợi ý sau đó: vùng gợi ý sai, lý do sửa là do bị mark cả chân của người ở cạnh
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

Ví dụ cách giải thích, không phải đáp án cho ảnh của bạn: “Tôi chỉ vẽ phần thân xe còn nhìn thấy; phần sau cột bị che nên không đoán đường biên phía sau.” Nếu công cụ đưa vùng tràn ra nền, hãy ghi đã xóa vùng nào và vì sao. “Gợi ý đúng” cũng cần nói bạn đã kiểm điều gì rồi mới giữ.

## 3. Một lỗi tôi tìm thấy và sửa

**Chọn một lỗi có thật trong bài của bạn**, không cần lỗi lớn nhất. Một dòng tốt có thể là: “Tại `cp2_slice`, hai xe cùng lớp bị gộp thành một mask; nhìn thấy khe giữa hai xe; tôi tách thành hai object, Save và export lại.” Nếu chưa sửa được do công cụ lỗi, nói rõ đã thử gì và cần coach hỗ trợ gì; đừng ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng: …
- Lỗi thuộc loại: sai lớp / thiếu-thừa vật / gộp-tách / biên / phủ vùng / khác: …
- Bằng chứng tôi nhìn thấy: …
- Quy tắc và hành động sửa: …
- Sau sửa đã Save và export lại chưa? …
- Task/ảnh/vùng: `medium_instance`, ảnh `000000181542.jpg`, vùng hai người đi bộ đứng sát nhau ở giữa khung hình.
- Lỗi thuộc loại: gộp-tách (dính mask giữa 2 instance cùng lớp).
- Bằng chứng tôi nhìn thấy: Khi vẽ (và xem gợi ý), mask của người thứ nhất bị lem bao trùm cả phần cẳng chân của người thứ hai đứng ngay cạnh; trên danh sách Objects chỉ có 1 instance gộp cả hai người dù phóng to nhìn thấy rõ khe ranh giới giữa hai vạt áo và chân.
- Quy tắc và hành động sửa: Theo quy tắc Instance Segmentation ("Hai vật cùng lớp sát nhau vẫn là hai instance riêng biệt"). Tôi dùng Brush ở chế độ Eraser để xóa phần mask bị lem sang người bên cạnh, sau đó tạo thêm một Object `person` mới cho người thứ hai và vẽ mask độc lập sát theo phần nhìn thấy.
- Sau sửa đã Save và export lại chưa? Đã bấm Save trên CVAT và đã Export lại file `medium_instance.zip`.

**Nếu đã xem điểm tự đánh giá trên GitHub Actions hoặc chạy scorer:** ghi một kết quả liên quan lỗi bạn vừa sửa, chẳng hạn “`easy_semantic`: per-class IoU của `sidewalk` tăng sau khi tôi sửa ranh bó vỉa, Save và export lại”; nếu chưa có điểm, ghi “chưa có”. Xem [hướng dẫn xem Summary hoặc chạy dự phòng](../docs/SELF_SCORING.md). Kết quả ba tier là tổng **/82**, không tự điền PASS, top 3 hoặc bonus. Đừng đưa ground truth vào fork.
**Nếu đã xem điểm tự đánh giá trên GitHub Actions hoặc chạy scorer:** chưa có điểm (chờ coach đối chiếu và chấm theo ground truth của lớp).

## 4. Ba ca chưa chắc hoặc đã cân nhắc

**“Ca” là một vùng cụ thể khiến bạn phải dừng lại và chọn cách hiểu**, không nhất thiết là ba lỗi. Với mỗi dòng, ghi vị trí, hai khả năng bạn đã cân nhắc, dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi quyết định của bạn. Nếu quy tắc chưa đủ rõ, viết một câu hỏi mà coach có thể trả lời. Ví dụ: “mép bó vỉa trong `cp4_curb`: road hay sidewalk? Tôi chọn sidewalk vì phần nền nâng cao; xin xác nhận ranh tại chỗ màu giống mặt đường.” Ba dòng có thể đến từ ba task khác nhau.

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| 1 | … | … | … |
| 2 | … | … | … |
| 3 | … | … | … |
| 1. `cp4_curb`, mép gờ bó vỉa tiếp giáp lòng đường | Gán là `road` hay `sidewalk` | Màu sắc và vật liệu nhựa đường tương đồng lòng đường, nhưng có gờ bê tông nổi cao phân cách làn đi bộ | Chọn `sidewalk` cho phần gờ nâng cao theo quy tắc chức năng bó vỉa. Câu hỏi: Với đoạn bó vỉa bị mòn bằng phẳng với mặt đường thì lấy ranh theo vệt nứt hay mép gạch? |
| 2. `cp1_holes`, vùng kính chắn gió nhìn xuyên nền | Khoét lỗ (cut out) hay giữ liền trong mask của xe | Kính trong suốt nhìn thấy cây/đường phía sau, nhưng kính là bộ phận cấu thành của xe | Quyết định giữ nguyên mask liền khối không khoét lỗ theo đúng quy tắc `cp1_holes`. Câu hỏi: Khoảng hở gầm xe giữa 2 bánh có áp dụng tương tự không? |
| 3. `cp5_occlusion`, thân xe bị cột đèn che cắt đôi | Tách thành 2 object riêng (đầu và đuôi) hay gộp chung 1 instance | Hai mảng nhìn thấy tách rời nhau về mặt thị giác do cột đèn che ở giữa | Quyết định gán chung 1 object `car` (mask có 2 vùng rời nhau), không vẽ đè qua cột đèn. Câu hỏi: Nếu vật che khuất trên 70% thân xe thì vẫn gộp hay tách rời? |
