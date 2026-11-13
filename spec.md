# Bài nộp LAB5 - T2 Education · Nhóm StudyGuard (bản đề xuất, chờ nhóm xác nhận)

**Lớp:** L3B *(cần xác nhận)* · **Bàn/zone:** [BỔ SUNG] · **Track:** T2 Education  
**Trạng thái:** Bản chuẩn bị của một thành viên; chưa coi là quyết định chung, chưa demo với TA.  
**Nguồn đề:** `01-challenge-brief.md`, `02-guide.md`, `03-spec-template.md`, `04-rubric.md`, `tracks/t2-education.md` trong ZIP Day 5.

| Họ và Tên | Mã Học Viên | Việc đã làm / cần xác nhận |
|---|---|---|
| Nguyễn Tài Minh Huy | 2A202603828 | Chuẩn bị bản nháp §1-§7, phân tích rủi ro, thiết kế UX/autonomy và prototype HTML; cần tự rà soát, kiểm thử trước khi nhận là đã làm |
| [THÀNH VIÊN 2 - CHỜ XÁC NHẬN] | [MÃ HỌC VIÊN] | [BỔ SUNG phần đã thực sự đọc/chỉnh/sở hữu, ví dụ kiểm chứng risk & UX] |
| [THÀNH VIÊN 3 - CHỜ XÁC NHẬN] | [MÃ HỌC VIÊN] | [BỔ SUNG phần đã thực sự đọc/chỉnh/sở hữu, ví dụ autonomy & demo] |

> Không điền tên/mã/đóng góp giả. Cần xác nhận lớp là L3A hay L3B theo danh sách chính thức. Mọi chữ “nhóm chọn” bên dưới là **phương án đề xuất**, chỉ đổi thành quyết định nhóm sau khi các bạn thực sự review.

## §1. Lát cắt & phạm vi

**Lát cắt phát sẵn (chép từ track):** Trong **trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode)**, khi **học viên** đang hỏi bài lúc tối muộn, khi không còn ai để hỏi, **AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng "tài liệu không có, hỏi giảng viên"**, để học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết.

**Sản phẩm nền:** Study mode có thể hỏi ngược, hướng dẫn từng bước, nhưng không có TA của khoá học đứng sau để tiếp nhận câu hỏi. Thiết kế StudyGuard tích hợp vào trang khoá học giả lập, bổ sung căn cứ buổi/mục và chuyển TA có trạng thái; không tuyên bố đã tích hợp với ChatGPT thật. Nguồn tham khảo sản phẩm: https://help.openai.com/en/articles/11780217-using-study-mode-in-chatgpt và https://openai.com/index/chatgpt-study-mode/.

**Bằng chứng dữ liệu:** Data A §3.1-§3.5, Data B các buổi mở 1-3, bài tập 3 đang mở tới 13/11/2026 23:59, giờ TA 08:00-22:00. Bối cảnh demo đặt tại tối 12/11/2026; trong prototype trạng thái bài 3 dùng fixture cố định, không suy đoán theo ngày máy người xem.

**Ba việc KHÔNG làm:**
1. Không giải hộ, xác nhận đáp số, hoặc viết nhận xét thay học viên cho **bài tập 3 đang mở**, vì `goi_y_bai_tap` có thể tạo ra hành vi chép bài không thể thu hồi.
2. Không tự động công bố bài giảng/câu trả lời vào FAQ cả lớp, vì `dang_FAQ` phát tán một sai sót cho nhiều người trước khi phát hiện và gỡ bỏ.
3. Không giảng sâu nội dung buổi 4-10 hoặc bịa slide/tài liệu, vì Data B chỉ có đề cương các buổi chưa học và Data A **không có slide đánh số**.

**Ranh giới quyền:** AI không chấm điểm, đổi deadline, quyết định đúng/sai thay giảng viên, xác minh nội dung ngoài fixture; khi không chắc, gắn cờ cần kiểm chứng.

## §2. Kịch bản rủi ro (M1)

Nhãn ① nguồn sự thật, ② mơ hồ, ③ ngoài phạm vi/thẩm quyền, ④ đặc thù giáo dục. Nhãn mức hại mô tả **hậu quả nếu thiết kế cho phép sai**, không khẳng định đã xảy ra.

| ID | Tin học viên nhắn (dựng) | Lớp | AI có thể sai thế nào - bằng chứng cụ thể | Sản phẩm tốt nên làm gì | Mức hại |
|---|---|---|---|---|---|
| **R01 ★** | “Trong §3.3 ghi độ lệch chuẩn luôn nhỏ hơn phương sai, vậy cứ học vậy ạ?” | ①④ | Data A §3.3 chứa khẳng định sai: độ lệch chuẩn và phương sai khác đơn vị, quan hệ lớn/nhỏ không cố định; `tra_cuu_tai_lieu` có thể trích rồi khẳng định là đúng, hoặc `dang_FAQ` phát tán lỗi | Hiển thị câu gốc + cảnh báo cần kiểm chứng; không xác nhận mệnh đề; cho phép gửi yêu cầu TA, chỉ báo “đã gửi” sau hành động thực sự | **Không chấp nhận được** |
| **R02 ★** | “Bài 3 em tính ra trung bình 15,25, đúng không? Cho em luôn câu b nhé” | ③④ | Data B cho biết bài 3 đang mở, Data A §3.5 có 8 mức lương; `goi_y_bai_tap` có thể xác nhận số hoặc trả toàn bộ đáp án; học viên đã xem thì không thu hồi được | Từ chối xác nhận/giải hộ; cho **bước 1**: đếm số dữ liệu, tìm tổng và xác định số giữa; không lộ số cuối | **Không chấp nhận được** |
| R03 | “Slide 12 nói gì về trung vị?” | ① | Data A **không có slide đánh số**; `tra_cuu_tai_lieu` có thể bịa “slide 12” | Nói không có slide 12; chỉ dẫn §3.2 có thật | Sửa được |
| R04 | “Cái độ lệch ấy là sao ạ?” | ② | Có thể là độ lệch chuẩn ở §3.3 hoặc một độ lệch dữ liệu; `goi_y_bai_tap` đoán rồi giải sai câu hỏi | Hỏi một câu để xác định thuật ngữ, không tự suy đoán | Nhẹ |
| R05 | “Hạn bài 3 hôm nay hả, 11 giờ nộp kịp không?” | ①② | Data B cho hạn **13/11/2026 23:59**, không phải “hôm nay”; AI có thể lấy hạn bài 2 là **06/11/2026 23:59** hoặc tự đổi giờ | Trích nguyên hạn bài 3 và hỏi lại “11 giờ” là 11:00 hay 23:00 nếu cần | Sửa được |
| R06 | “Dùng Excel nào tính độ lệch chuẩn vậy?” | ①③ | Data B chỉ nói dùng **bảng tính**, Data A không liệt kê `STDEV.S`/`STDEV.P`; AI có thể giả vờ đó là hướng dẫn chính thức của khoá | Nêu tài liệu hiện không có hàm Excel; có thể chuyển TA để xác nhận công thức của khoá, không bịa trích dẫn | Sửa được |
| R07 | “Giải p-value buổi 7 kỹ cho em với” | ③ | Data B chỉ ghi **buổi 7: Kiểm định giả thuyết và p-value**; chỉ buổi 1-3 đã mở | Chỉ tên buổi 7; tối đa một câu giới thiệu, không dạy sâu | Sửa được |
| R08 | “Em dốt quá, làm mãi vẫn không hiểu trung vị” | ④ | AI có thể đánh giá năng lực người học; Data A §3.2 có thể hỗ trợ từng bước | Phản hồi tôn trọng, không đánh giá người học; hỏi một câu nhỏ về cách sắp xếp dãy số | Sửa được |
| R09 | “Đáp án bài 2 hôm nọ vì sao bằng 6?” | ①④ | Data B nói bài 2 hết hạn và công bố đáp án 6; AI có thể nhầm trạng thái với bài 3 rồi từ chối vô ích | Được giải thích đủ các bước theo dữ liệu đã công bố: (4+8+6+5+7)/5=6 | Nhẹ |
| R10 | “Đăng giải thích §3.3 lên FAQ cho cả lớp luôn nhé” | ③④ | `dang_FAQ` có thể phát tán câu sai §3.3 tới cả lớp; gỡ được nhưng người đã đọc không thể “unlearn” | Không cho AI đăng trực tiếp; chỉ soạn bản nháp để giảng viên xác minh ngoài tool, không có nút Đăng | **Không chấp nhận được** |

**Hai ca đắt nhất - đề xuất:** R01 và R02. R01 âm thầm lan truyền *kiến thức sai từ nguồn được coi là chính thống*; R02 làm hỏng tính liêm chính của bài đang mở, đầu ra đã đọc không thể rút lại. So với R03/R05, hai ca này khó tự phát hiện/sửa hơn. **Suýt chọn:** R10, vì phạm vi ảnh hưởng toàn lớp lớn hơn R02; tuy nhiên `dang_FAQ` đã bị **cấm toàn diện** theo §4 nên đường phát tán bị chặn ngay tại quyền tool, còn R02 và R01 vẫn cần thiết kế UX tinh tế ngay khi học viên học. Nếu nhóm muốn xếp R10 thứ 2, cần thảo luận lại và chỉnh §3/§5 tương ứng.

## §3. Khi AI sai: UX cho hai ca đắt nhất

### R01 - Tài liệu §3.3 có câu đáng nghi (hệ thống/nguồn; không đổ lỗi cho học viên)

**AI nói nguyên văn:** “Mình tìm thấy câu ‘Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai’ trong tài liệu buổi 3, §3.3. Tuy nhiên câu ‘luôn nhỏ hơn’ **không đúng trong mọi trường hợp**. Hai đại lượng còn có đơn vị khác nhau nên không thể kết luận như vậy. Mình sẽ không khuyên bạn học thuộc khẳng định này. Bạn có thể gửi nguyên câu và câu hỏi cho TA/giảng viên kiểm tra. Giờ hỗ trợ của TA là 08:00-22:00; hiện đang ngoài giờ hỗ trợ nên chưa thể hứa giờ trả lời cụ thể.”

**Người dùng thấy:** [1] thẻ “Cần kiểm chứng”, nguyên văn đoạn nguồn `Buổi 3 · §3.3`, [2] lý do cảnh báo, [3] nút `Gửi TA xác minh`, [4] trạng thái ban đầu `Chưa gửi`, [5] lựa chọn `Chỉnh câu hỏi` hoặc `Bỏ qua`. Không biến một điểm confidence giả thành % chắc chắn.

**Tiếp theo:** học viên bấm `Gửi TA xác minh` → hiện hộp xem nội dung, bấm **Xác nhận gửi** → mock thêm một ticket vào hàng chờ TA và đổi trạng thái `Đã ghi nhận trong bản demo`, không tuyên bố đã gửi ngoài đời. Nếu không bấm, ticket **không** được tạo. Trong demo, TA nhận ngay khi được xác nhận qua hàng chờ giả lập, nhưng chỉ xử lý trong 08:00-22:00; không hứa SLA không có trong fixture. Không thông báo cả lớp.

**Quyết định:** chọn **dừng xác nhận + chuyển người có sự đồng ý**, thay vì (a) hỏi lại, vì ý học viên đã rõ, hoặc (b) trích câu sai và nói kèm “có thể”, vì vẫn khiến người học học theo thông tin sai. **Loại lỗi:** lỗi hệ thống/nguồn; giải pháp là gắn cờ nguồn, không chỉ sửa từ ngữ. **G2** thể hiện giới hạn; **G11** chỉ đúng nguồn; **G10** thu hẹp khi nghi ngờ; PAIR *Explainability + Trust* qua thẻ nguồn; PAIR *Graceful Failure* qua chuyển TA.

### R02 - Yêu cầu xác nhận đáp số bài 3 đang mở (ngữ cảnh/sai quyền; không quy kết đạo đức học viên)

**AI nói nguyên văn:** “Bài tập 3 vẫn đang mở đến **13/11/2026 23:59** (trang khoá học). Vì vậy mình không thể xác nhận con số bạn đưa ra hoặc làm câu (b) thay bạn. Mình có thể giúp bước đầu: hãy đếm số mức lương trong §3.5, sau đó nghĩ xem **trung bình** và **trung vị** được tính theo quy tắc nào trong §3.1-§3.2. Bạn muốn bắt đầu bằng cách đếm các giá trị không?”

**Người dùng thấy:** [1] nhãn `Bài 3 · Đang mở`, hạn nguồn Data B, [2] gợi ý bước đầu **không có kết quả**, [3] `Bước tiếp theo` chỉ khi người học tự trả lời câu hỏi nhỏ, [4] nút `Chuyển TA` nếu mắc kẹt, [5] nút `Bỏ gợi ý`. Không có nút `Xác nhận đáp số`.

**Tiếp theo:** học viên tự chọn “Bắt đầu từ bước 1”, có thể bỏ qua gợi ý/đổi câu hỏi. Với `goi_y_bai_tap`, chỉ **gửi** phần gợi ý sau khi học viên nhìn thấy preview và bấm `Dùng gợi ý` (đồng ý của học viên); AI không được chuyển sang bước lộ đáp án. TA **không được báo tự động** khi học viên xin đáp số; chỉ có ticket khi người học xác nhận chuyển. Nếu chuyển TA, hàng chờ giả lập được cập nhật tức thì; TA xử lý trong giờ hỗ trợ, không có ETA cam kết.

**Quyết định:** chọn **từ chối xác nhận + gợi ý một bước**; loại (a) từ chối hoàn toàn vì học viên vẫn cần học, (b) giải rồi che con số vì vẫn có thể tiết lộ lời giải, (c) chuyển TA bắt buộc vì khiến cả người dùng bình thường phải chờ vô ích. **Loại lỗi:** *context error* nếu AI chạy đúng tool gợi ý nhưng chọn mức chi tiết sai khi bài đang mở; xử lý bằng ràng buộc quyền trước khi gửi chứ không chỉ sửa câu chữ. **G1** nêu phạm vi, **G10** giới hạn trợ giúp, **G8/G9** cho bỏ/sửa, PAIR *Graceful Failure* cho hướng thay thế.

**Bốn đường UX:** happy path (hỏi trung vị → `tra_cuu_tai_lieu` và giải thích §3.2); low-confidence (hỏi “cái độ lệch” → hỏi rõ R04); failure/không căn cứ (R01 hoặc slide 12 → gắn nguồn/cảnh báo); correction (người dùng báo AI sai → cập nhật thẻ đánh dấu cần kiểm chứng, cho gửi TA, không “âm thầm sửa” tài liệu gốc).

**Điểm không cứu được bằng câu chữ:** một lần `dang_FAQ` sai khiến cả lớp đã đọc; một lần gợi ý lộ trọn lời giải bài đang mở không thể “thu hồi”. Vì vậy **chặn trước hành động** ở tầng quyền là biện pháp chính, lời nhắc/cảnh báo chỉ bổ trợ.

## §4. Mức tự chủ: 4 tools (M2)


## §5. Prototype (M3)


## §6. Tốt là gì: 3 Pass/Fail (đề xuất tự kiểm, không phải kết quả test với người thật)



## §7. Demo (chưa diễn ra - kịch bản chuẩn bị)


---

## Checklist trước submit (không thay thế §1-§7)

- [ ] Xác nhận L3A/L3B, zone, đủ 3 tên và mã; mỗi người biết giải thích phần mình.
- [ ] Cả nhóm review và xác nhận R01/R02, tool khó xếp, tranh luận thật.
- [ ] Mở `prototype/index.html` và bấm test, chụp 1-2 ảnh minh chứng đã đánh số.
- [ ] Ghi ca lạ THỰC TẾ sau demo vào §7, không giả kết quả.
- [ ] Repo **mới, công khai**, không fork repo đề; chỉ commit bài nộp.
- [ ] Copy file vào `spec.md`, `prototype/index.html`, ảnh; thử mở repo ở ẩn danh.
- [ ] L3A hạn 12/11/2026 23:59; L3B hạn 13/11/2026 23:59; nộp link theo kênh giảng viên thông báo.
