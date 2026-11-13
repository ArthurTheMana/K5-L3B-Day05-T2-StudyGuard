# Bài nộp LAB5 - T2 Education · Nhóm StudyGuard (bản đề xuất, chờ nhóm xác nhận)

**Lớp:** L3B *(cần xác nhận)* · **Bàn/zone:** [BỔ SUNG] · **Track:** T2 Education  
**Trạng thái:** Bản chuẩn bị của một thành viên; chưa coi là quyết định chung, chưa demo với TA.  
**Nguồn đề:** `01-challenge-brief.md`, `02-guide.md`, `03-spec-template.md`, `04-rubric.md`, `tracks/t2-education.md` trong ZIP Day 5.

| Họ và Tên                     | Mã Học Viên   | Việc đã làm / cần xác nhận |
|-------------------------------|---------------|---|
| Nguyễn Tài Minh Huy           | 2A202603828   | Chuẩn bị bản nháp §1-§7, phân tích rủi ro, thiết kế UX/autonomy và prototype HTML; cần tự rà soát, kiểm thử trước khi nhận là đã làm |
| Hoàng Quang Đạt | 2A202603808 | Product UX & Frontend Prototype (§5, §7), mở rộng Edge-Case Engine xử lý ca lạ, thiết kế tương tác Portal TA 2 chiều, ánh xạ HAX/PAIR |
| Đỗ Anh Thư                    | 2A202603815   | [BỔ SUNG phần đã thực sự đọc/chỉnh/sở hữu, ví dụ autonomy & demo] |

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

| Tool | Mức đề xuất | Cái giá khi sai, tính đảo ngược, giá chờ duyệt | Ai duyệt / thấy gì / quá hạn | Phương án đã loại |
|---|---|---|---|---|
| `tra_cuu_tai_lieu` | **Tự làm** (chỉ đọc), nhưng câu đáng nghi bị gắn cờ và không được xác nhận | Chỉ đọc; tìm nhầm mục có thể được phát hiện/sửa trong UX, trong khi bắt TA duyệt mỗi lượt sẽ cản học lúc tối | Không cần duyệt; hiển thị Buổi·§ và trạng thái nguồn; có `Bỏ/Chỉnh` | `Cần duyệt` cho mọi lần: chờ vô ích; `Cấm`: không còn trợ lý có căn cứ |
| `goi_y_bai_tap` | **Cần người duyệt** (học viên xác nhận nhận gợi ý); bộ lọc bắt buộc chỉ **bước đầu** cho bài đang mở | Gợi ý sai mức làm học viên chép, khó thu hồi; một lượt học viên xem preview và chủ động nhận không thay cho kiểm soát nội dung | **Học viên** duyệt phần preview chỉ có bước đầu; nếu không xác nhận, không gửi gì; khi bài mở thì không cho đáp số kể cả học viên đồng ý | `Tự gửi` dễ đẩy lời giải; `Cấm` làm mất lợi ích học từng bước. Xác nhận học viên **không đủ** để hợp pháp hoá việc lộ đáp án |
| `chuyen_TA` | **Cần người duyệt** (học viên xác nhận gửi) | Chuyển được/rút yêu cầu demo được; gửi nhầm có thể làm lộ câu hỏi không mong muốn và tăng tải TA; chờ xác nhận ít tốn hơn | **Học viên** xem nội dung câu hỏi, nguồn, giờ hỗ trợ 08-22; hết giờ thì lưu hàng chờ, không cam kết thời gian TA trả lời; chỉ báo gửi sau confirm | `Tự gửi` xâm phạm ý định người học; `Cấm` khiến R01 không có đường sửa nguồn |
| `dang_FAQ` | **Cấm** trong lát cắt | Có thể gỡ nhưng nhiều người đã đọc kiến thức sai; nguy cơ R10 lan toàn lớp | Không có nút để người dùng/AI đăng FAQ. Giảng viên có thể xây workflow biên tập **ngoài phạm vi** sau này | `Tự đăng` quá nguy hiểm; `Duyệt bởi học viên` không đủ chuyên môn; ngay cả `TA duyệt` cần quy trình quản trị nội dung và kiểm chứng mới, chưa có trong fixture |

**Tool khó xếp nhất: `goi_y_bai_tap`.** Phương án A: tự làm vì người học cần ngay lúc tối (rủi ro R02 lộ đáp số). Phương án B: cần học viên duyệt preview gợi ý **đã giới hạn ở bước đầu**, tránh gửi quá tay mà vẫn nhanh. Phương án C: cấm, an toàn nhưng làm mất giá trị Study mode. **Đề xuất chốt B** cùng kiểm soát nội dung bắt buộc ở tầng chính sách. **[CHỜ MỖI THÀNH VIÊN ĐIỀN LỰA CHỌN THỰC SỰ]**: Huy [ ], bạn 2 [ ], bạn 3 [ ]; sau thảo luận ghi kết quả, không dựng biên bản giả.

**Thử mức:**
- **R01:** `tra_cuu_tai_lieu` tự đọc §3.3 nhưng flag “cần kiểm chứng”; không phát biểu câu sai như chân lý; `chuyen_TA` chỉ thực thi sau xác nhận; `dang_FAQ` cấm. **Sai bị chặn**, không hỏi học viên lại điều đã rõ; TA không xử lý ngay ngoài giờ.
- **R02:** `goi_y_bai_tap` tạo preview **bước đầu**, không tạo đáp số và chờ học viên bấm dùng; `dang_FAQ` cấm. **Sai bị chặn** bởi quy tắc nội dung (không chỉ bởi confirmation), học viên không phải chờ TA.
- **R09 bình thường:** `tra_cuu_tai_lieu` tự lấy đáp án bài 2 đã công bố; giải thích 6 mà không cần TA, vì bài 2 đã hết hạn và có đáp án. **Không chờ vô ích**.

**Luật/tách bước mới:** `goi_y_bai_tap` thành `soan_preview_goi_y` (không gửi, bước đầu) → `xac_nhan_dung_goi_y` (bấm của học viên); `chuyen_TA` thành `soan_ticket` → `xac_nhan_gui_ticket` (bấm của học viên). Đây là **tách logic UX** trong prototype, không tạo thêm tool gốc có năng lực ngoài Data A/B. **Luật guard:** kiểm trạng thái bài trước khi sinh gợi ý; kiểm mã mục trước khi trích; chặn FAQ ở cả UI và tầng handler.

**Lời hứa đã đổi:** không nói “AI tự giải bài và gửi kết quả”, mà là “AI tìm nguồn, chỉ gợi ý bước đầu; bạn chọn nhận gợi ý hoặc gửi vấn đề cho TA”. Đây là trade-off có chủ đích giữa nhanh và không học sai.

## §5. Prototype (M3)
**File:** `prototype/index.html` — ứng dụng web chạy hoàn toàn offline (SPA), không dùng framework ngoài, không backend, không API key (chủ động không lấy bonus API để đảm bảo demo 100% không bao giờ gặp sự cố mạng hay quota).  
**Công cụ:** HTML5, CSS3, Vanilla JavaScript thuần.  
**Dữ liệu & Fixture:** Bám sát Data A (Buổi 3 §3.1–§3.5) và Data B (Bài 2 đã đóng có đáp án 6, Bài 3 đang mở hạn 13/11/2026 23:59, giờ TA 08:00–22:00).

### Cấu trúc 2 màn hình tương tác:
1. **Màn hình 1 · Học viên (Student Interface):**
   - **Đồng hồ giả lập ngữ cảnh:** Tích hợp bộ đếm giờ thực tế giả lập mốc **22:30 (Đêm) · Ngoài ca trực TA (08:00–22:00)** làm nổi bật bài toán học bài lúc tối muộn.
   - **5 nút kịch bản dựng sẵn:** Bấm chuyển nhanh R01 (lỗi tài liệu §3.3), R02 (xin đáp án bài 3 đang mở), R04 (hỏi mơ hồ), R09 (bài 2 đã đóng), R03 (hỏi slide 12 không tồn tại).
   - **Edge-Case Engine (`customAsk`):** Ô nhập tự do kèm 6 chip gợi ý test nhanh các ca hiểm hóc (tâm lý nản chí R08, xin nộp trễ deadline, hỏi hàm Excel R06, hỏi buổi 4–10 chưa mở R07, hỏi ngoài giờ trực, đòi đăng FAQ). Bộ phân loại nhận diện chính xác ngữ cảnh để phản hồi đúng chuẩn mực.
   - **Cơ chế duyệt 2 bước an toàn:** Khi xem gợi ý bài 3 (chỉ xem preview bước 1, bấm `Xác nhận nhận` mới nạp vào); khi chuyển TA (hiện popup xem lại nội dung và cảnh báo ngoài giờ, bấm `Xác nhận gửi` mới tạo ticket).
2. **Màn hình 2 · Portal TA (Teacher Assistant Interface):**
   - **Quản lý hàng chờ 2 chiều:** Nhận ticket theo thời gian thực từ Màn hình 1.
   - **Phân loại ưu tiên:** Tự động gắn tag độ ưu tiên (`Ưu tiên cao · Nghi vấn lỗi tài liệu` cho R01; `Thắc mắc bài tập đang mở` cho R02).
   - **Tương tác trực tiếp:** TA có thể bấm **"Tiếp nhận xử lý"** (đổi trạng thái từ `Chờ xử lý (Hàng chờ đêm)` sang `Đang xử lý`), bấm **"Ghi chú / Phản hồi"** để nhập nhận xét gửi ngược lại cho học viên, hoặc đóng ticket.
   - **Bộ lọc trạng thái:** Lọc theo *Tất cả / Chờ xử lý / Đang xử lý*.

### Minh chứng ảnh đánh số & Bảng ánh xạ HAX / PAIR / Mức tự chủ:

![Màn hình 1 · Giao diện Học viên có đánh số](prototype/01-student.png)
*Hình 1: Màn hình Học viên — Thể hiện các vị trí [1], [2], [3], [4], [5] tương ứng các nguyên tắc HAX/PAIR và mức tự chủ.*

![Màn hình 2 · Giao diện Portal TA có đánh số](prototype/02-ta.png)
*Hình 2: Màn hình Portal TA — Thể hiện các vị trí [6], [7], [8] tương ứng luồng chuyển người an toàn và mức tự chủ.*

| Vị trí số | Thể hiện gì trên giao diện | Nguyên tắc HAX / PAIR | Mức tự chủ tương ứng (Autonomy Level) |
|---|---|---|---|
| **[1]** | Thẻ trạng thái & nhãn ngữ cảnh (`Cần kiểm chứng · Lỗi nguồn §3.3`, `Bài 3 đang mở · Giới hạn quyền`, `Đã có đáp án · An toàn giải thích`). | **HAX G1** (Làm rõ hệ thống làm được gì) & **HAX G2** (Làm rõ mức độ tin cậy/giới hạn). Không dùng số % confidence giả mạo. | **Tự làm (Chỉ đọc)**: AI tự động phân tích và gắn cờ cảnh báo trạng thái từ fixture. |
| **[2]** | Khung căn cứ & nguồn trích dẫn sự thật (Truth Source): trích nguyên văn mã mục `Buổi 3 · §3.1-§3.5` hoặc deadline từ Data B. Nói rõ không có slide đánh số. | **HAX G11** (Minh bạch nguyên nhân/căn cứ) & **PAIR Explainability + Trust** (Tạo niềm tin đúng mức qua bằng chứng kiểm chứng được). | **Tự làm (Chỉ đọc)**: Thuộc công cụ `tra_cuu_tai_lieu`, chỉ đọc dữ liệu tĩnh, không suy diễn ngoài nguồn. |
| **[3]** | Phản hồi của Trợ lý AI: Từ chối giải hộ/xác nhận đáp số bài 3 đang mở; không khẳng định câu sai §3.3; chỉ đưa gợi mở bước 1. | **HAX G10** (Thu hẹp phạm vi khi nghi ngờ / thiếu thông tin). | **Cần người duyệt**: Thuộc công cụ `goi_y_bai_tap`, AI chỉ được tạo preview bước 1, tuyệt đối bị chặn không được tự gửi đáp án. |
| **[4]** | Cụm nút hành động điều khiển: `Gửi TA xác minh`, `Xem bước gợi ý đầu`, `Bỏ qua / Hoàn tác`, `Chỉnh sửa câu hỏi`. | **HAX G8** (Dễ dàng bỏ qua) & **HAX G9** (Dễ dàng sửa đổi câu hỏi khi AI hiểu sai ý). | **Cần người duyệt**: Cả 2 tool `goi_y_bai_tap` và `chuyen_TA` đều bắt buộc học viên bấm phê duyệt thì mới thực thi. |
| **[5]** | Hộp trạng thái phản hồi hệ thống: Báo rõ AI đã làm gì, chưa làm gì (*"Đã đọc fixture (chỉ đọc). Chưa gửi hay đăng bất kỳ nội dung nào"*). | **PAIR Feedback & Transparency** (Minh bạch hành động, giúp học viên an tâm không lo bị gửi nhầm). | **Tự làm**: Cập nhật trạng thái hệ thống theo thời gian thực sau mỗi thao tác. |
| **[6]** | Hàng chờ tiếp nhận của TA: Tổng số lượng ticket đang chờ và các nút lọc trạng thái (*Tất cả / Chờ xử lý / Đang xử lý*). | **PAIR Graceful Failure** (Lối thoát an toàn khi AI không có thẩm quyền hoặc gặp nội dung nghi vấn). | **Cần người duyệt**: Chỉ những ticket được học viên confirm mới được đưa vào hàng chờ của TA. |
| **[7]** | Thẻ ticket chi tiết: Hiển thị nguyên văn câu hỏi, trích nguồn, tag độ ưu tiên, nút `Tiếp nhận xử lý` và ô nhập `Ghi chú / Phản hồi`. | **HAX G11** (Minh bạch căn cứ) & **PAIR Explainability** (Đưa đầy đủ ngữ cảnh để TA xử lý chính xác). | **Cần người duyệt**: TA là người duyệt xử lý và lưu phản hồi gửi lại cho học viên. |
| **[8]** | Khung thông báo ca trực TA: Báo rõ giờ hỗ trợ 08:00–22:00, cảnh báo mốc 22:30 đêm nên ticket lưu hàng chờ sáng mai giải quyết. | **HAX G2** (Minh bạch giới hạn dịch vụ) & **PAIR Graceful Failure** (Không hứa hẹn sai lệch SLA khi ngoài ca trực). | **Cần người duyệt / Quy tắc hệ thống**: Chặn hứa hẹn bừa bãi, bảo vệ quyền lợi học viên và thời gian của TA. |
| **CẤM** | Công cụ `dang_FAQ` hoàn toàn không có nút gọi trên giao diện. | **HAX G1** (Không tạo kỳ vọng sai lệch về thẩm quyền). | **CẤM HOÀN TOÀN**: Tránh rủi ro phát tán kiến thức sai lệch cho toàn thể lớp học. |

### Quyết định thiết kế giao diện:
- *Đã cân nhắc dùng % chắc chắn (ví dụ: "Độ tin cậy 85%")*: **Đã loại bỏ** vì trong mô hình ngôn ngữ hoặc prototype rule-based, % xác suất không được hiệu chuẩn sẽ gây ra độ tin cậy giả tạo nguy hiểm. Chọn thay thế bằng **nhãn trạng thái ngữ nghĩa** (`Cần kiểm chứng`, `Đang mở`).
- *Đã cân nhắc nút "Đăng FAQ" bị làm mờ*: **Đã loại bỏ** vì nút mờ vẫn ngầm hiểu là tính năng tồn tại nhưng tạm khóa, có thể gây hiểu lầm hoặc bị bypass bằng DevTools. Quyết định **loại bỏ hoàn toàn khỏi UI**.
- *Đã cân nhắc cơ chế tự động gửi ticket khi học viên bấm*: **Đã loại bỏ** vì học viên có thể bấm nhầm hoặc đổi ý. Bắt buộc có **bước xác nhận** hiển thị tóm tắt nội dung gửi để học viên nắm quyền quyết định cuối cùng.

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
