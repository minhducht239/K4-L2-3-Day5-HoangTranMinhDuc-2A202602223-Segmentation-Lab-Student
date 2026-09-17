# Báo cáo Day 5 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên VLearn. Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: …
- Ngày / CVAT local: …
- Công cụ đã dùng: …
- Mã học viên theo lớp: 2A202602223
- Ngày / CVAT local: 17/9/2026
- Công cụ đã dùng: Brush, Polygon

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh VLearn đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic | … | … / 3 | 20 |
| medium_instance | … | … / 3 | 32 |
| hard_panoptic | … | … / 2 | 30 |
| cp1_holes | … | … / 1 | 3 |
| cp2_slice | … | … / 1 | 3 |
| cp5_occlusion | … | … / 1 | 3 |
| cp3_thin | … | … / 1 | 3 |
| cp4_curb | … | … / 1 | 3 |
| cp6_coverage | … | … / 1 | 3 |
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

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: …
- Class và quy tắc tôi dùng để chọn biên: …
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: …
- Ảnh, vị trí và object Medium đầu tiên tự vẽ: person ở giữa khung
- Class và quy tắc tôi dùng để chọn biên: class person, vẽ sát phần cơ thể nhìn thấy
- Nếu dùng gợi ý sau đó: vùng gợi ý sai, lý do sửa là do bị mark cả chân của người ở cạnh
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi **có thật** trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

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

Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): … / chưa có điểm. Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.
Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): chưa có điểm (chờ coach đối chiếu và chấm theo ground truth của lớp). Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| 1 | … | … | … |
| 2 | … | … | … |
| 3 | … | … | … |
| 1. `cp4_curb`, mép gờ bó vỉa tiếp giáp lòng đường | Gán là `road` hay `sidewalk` | Màu sắc và vật liệu nhựa đường tương đồng lòng đường, nhưng có gờ bê tông nổi cao phân cách làn đi bộ | Chọn `sidewalk` cho phần gờ nâng cao theo quy tắc chức năng bó vỉa. Câu hỏi: Với đoạn bó vỉa bị mòn bằng phẳng với mặt đường thì lấy ranh theo vệt nứt hay mép gạch? |
| 2. `cp1_holes`, vùng kính chắn gió nhìn xuyên nền | Khoét lỗ (cut out) hay giữ liền trong mask của xe | Kính trong suốt nhìn thấy cây/đường phía sau, nhưng kính là bộ phận cấu thành của xe | Quyết định giữ nguyên mask liền khối không khoét lỗ theo đúng quy tắc `cp1_holes`. Câu hỏi: Khoảng hở gầm xe giữa 2 bánh có áp dụng tương tự không? |
| 3. `cp5_occlusion`, thân xe bị cột đèn che cắt đôi | Tách thành 2 object riêng (đầu và đuôi) hay gộp chung 1 instance | Hai mảng nhìn thấy tách rời nhau về mặt thị giác do cột đèn che ở giữa | Quyết định gán chung 1 object `car` (mask có 2 vùng rời nhau), không vẽ đè qua cột đèn. Câu hỏi: Nếu vật che khuất trên 70% thân xe thì vẫn gộp hay tách rời? |
