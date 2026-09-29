# Lời nói đầu

## Từ một Agent chạy được đến một hệ thống đáng tin cậy

Agent đang thay đổi cách chúng ta xây dựng phần mềm. Nếu ứng dụng AI trước đây chủ yếu tiếp nhận câu hỏi và tạo ra nội dung, Agent có thể theo đuổi một mục tiêu qua nhiều bước, sử dụng tool, thay đổi môi trường và phối hợp với con người hoặc những Agent khác để hoàn thành nhiệm vụ. Sự thay đổi này mở ra nhiều khả năng mới, nhưng cũng đưa vào hệ thống một mức độ bất định chưa từng có.

Một bản demo có thể gây ấn tượng chỉ sau vài phút. Đưa chính Agent đó vào môi trường production lại là một bài toán hoàn toàn khác. Khi nhiệm vụ kéo dài, context tăng lên, tool nhiều hơn và tác động của mỗi hành động lớn hơn, những câu hỏi khó bắt đầu xuất hiện: trạng thái nào cần được lưu lại, quyền hạn được giới hạn ra sao, lỗi giữa chừng được khôi phục thế nào, kết quả được kiểm chứng bằng gì, và ai chịu trách nhiệm khi hệ thống đưa ra quyết định sai?

Vì vậy, năng lực của model chỉ là một phần của câu chuyện. Để Agent có thể làm việc ổn định, hệ thống bao quanh model phải tổ chức context, duy trì state, kiểm soát hành động, cô lập môi trường thực thi, ghi lại bằng chứng và tạo ra các vòng lặp đánh giá. Trong cuốn sách này, tập hợp những năng lực đó được gọi chung là **Harness**. Ranh giới giữa Model và Harness cũng là một trong những chủ đề xuyên suốt: model cung cấp năng lực nhận thức mang tính xác suất, còn Harness biến năng lực ấy thành một quá trình thực thi có thể kiểm soát, quan sát và cải tiến.

Mục tiêu của cuốn sách không phải là giới thiệu thêm một framework hay đưa ra một công thức duy nhất cho mọi hệ thống Agent. Mỗi bài toán có đặc điểm nghiệp vụ, mức rủi ro và giới hạn đầu tư khác nhau. Một kiến trúc phù hợp cho trợ lý nội bộ chưa chắc phù hợp cho Agent có quyền thay đổi dữ liệu production; một quy trình hiệu quả với task ngắn chưa chắc duy trì được tính liên tục trong nhiều ngày. Điều quan trọng là hiểu rõ các lựa chọn kiến trúc, ranh giới trách nhiệm và điều kiện để từng lựa chọn phát huy tác dụng.

## Cách tiếp cận của cuốn sách

Nội dung được tổ chức theo vòng đời của một Agentic Application: **kiến trúc, xây dựng, vận hành, quản trị và tối ưu**. Cách tổ chức này phản ánh một thực tế: Agent không trở nên đáng tin cậy nhờ một component riêng lẻ, mà nhờ nhiều lớp kỹ thuật phối hợp với nhau trong suốt vòng đời hệ thống.

**Phần Kiến trúc** xác định các hình thái ứng dụng Agent, mức độ tự chủ phù hợp và kiến trúc tham chiếu. Trọng tâm không nằm ở việc dùng càng nhiều component càng tốt, mà ở việc chọn kiến trúc tối giản nhưng đủ đáp ứng mục tiêu, rủi ro và quy mô của bài toán.

**Phần Xây dựng** đi sâu vào Harness qua ba nhóm hợp đồng chính: task, thông tin và hành động. Phần này trình bày cách Agent duy trì tiến trình, tổ chức context và state, sử dụng Memory, Knowledge và Skill, gọi tool, nhận phản hồi từ môi trường và chứng minh rằng nhiệm vụ thực sự đã hoàn thành.

**Phần Vận hành** xem Agent như một workload cần chạy ổn định trong môi trường thực tế. Các chương lần lượt đề cập đến Runtime, Sandbox, lưu trữ trạng thái, AI Gateway, task bất đồng bộ, cộng tác Multi-Agent và giao tiếp phân tán.

**Phần Quản trị** tập trung vào khả năng quan sát, bảo mật, quản lý tài sản AI và kiểm định chất lượng. Một hệ thống tự chủ chỉ có thể đáng tin cậy khi hành vi của nó được truy vết, quyền hạn được ràng buộc, các phụ thuộc được quản lý và thay đổi được kiểm chứng trước khi phát hành.

**Phần Tối ưu** trình bày cách biến dữ liệu vận hành thành năng lực cải tiến. Trace, Trajectory, golden dataset, badcase và Evaluation không chỉ phục vụ việc tìm lỗi; khi được tổ chức đúng, chúng tạo thành nền tảng cho việc tối ưu Harness, lựa chọn hoặc huấn luyện model và xây dựng vòng lặp cải tiến liên tục.

**Phần Thực tiễn** đưa các khái niệm trên vào những bối cảnh cụ thể như phát triển phần mềm, thiết kế, AIOps, vận hành doanh nghiệp, phân tích dữ liệu và cộng tác Multi-Agent. Các case study không được xem như khuôn mẫu để sao chép nguyên trạng, mà là nguồn tham khảo để hiểu cách những nguyên tắc kỹ thuật được áp dụng dưới các điều kiện khác nhau.

Phần cuối mở rộng góc nhìn từ từng Agentic Application sang **Agentic OS**: khi số lượng Agent, framework và môi trường thực thi tăng lên, năng lực nào nên tiếp tục nằm trong ứng dụng và năng lực nào nên trở thành dịch vụ dùng chung ở tầng hệ thống.

## Danh mục tài liệu

Bạn có thể đọc tuần tự hoặc đi thẳng tới phần phù hợp với vấn đề đang quan tâm.

| Phần | Chương và nội dung |
| --- | --- |
| Tổng quan | [Báo cáo khảo sát lập trình viên Agent 2026](../2026-bao-cao-khao-sat-agent.md) - hiện trạng phát triển, triển khai production, kiến trúc, công cụ và phương pháp đánh giá Agent trong doanh nghiệp. |
| Kiến trúc | [Chương 1 - Giai đoạn mới của ứng dụng AI-native](../01-kien-truc/chuong-01-giai-doan-moi-cua-ung-dung-ai-native.md)<br>[Chương 2 - Kiến trúc tham chiếu của Agentic Application](../01-kien-truc/chuong-02-kien-truc-tham-chieu-agentic-application.md) |
| Xây dựng | [Chương 3 - Paradigm: các cách xây Harness phổ biến và ranh giới trách nhiệm](../02-xay-dung/chuong-03-paradigm-harness-va-ranh-gioi-trach-nhiem.md)<br>[Chương 4 - Task: điều phối, tiến trình dài và cộng tác](../02-xay-dung/chuong-04-task-dieu-phoi-tien-trinh-dai-va-cong-tac.md)<br>[Chương 5 - Thông tin: context, state và năng lực tái sử dụng](../02-xay-dung/chuong-05-thong-tin-context-state-va-nang-luc-tai-su-dung.md)<br>[Chương 6 - Hành động: thực thi có kiểm soát và kiểm chứng](../02-xay-dung/chuong-06-hanh-dong-thuc-thi-co-kiem-soat-va-xac-thuc.md) |
| Vận hành | [Chương 7 - Agent Runtime và Sandbox](../03-van-hanh/chuong-07-agent-runtime-va-sandbox.md)<br>[Chương 8 - Lưu trữ trạng thái và tài sản ngữ nghĩa](../03-van-hanh/chuong-08-luu-tru-trang-thai-va-tai-san-ngu-nghia.md)<br>[Chương 9 - AI Gateway và quản trị traffic thống nhất](../03-van-hanh/chuong-09-ai-gateway-va-quan-tri-traffic-thong-nhat.md)<br>[Chương 10 - Task bất đồng bộ và quy trình tự động hoá](../03-van-hanh/chuong-10-task-bat-dong-bo-va-quy-trinh-tu-dong-hoa.md)<br>[Chương 11 - Multi-Agent: cộng tác và orchestration](../03-van-hanh/chuong-11-multi-agent-cong-tac-va-orchestration.md)<br>[Chương 12 - Giao tiếp phân tán của Agent](../03-van-hanh/chuong-12-agent-giao-tiep-phan-tan.md) |
| Quản trị | [Chương 13 - Observability của Agent](../04-quan-tri/chuong-13-observability-cua-agent.md)<br>[Chương 14 - Bảo mật Agent](../04-quan-tri/chuong-14-bao-mat-agent.md)<br>[Chương 15 - Khám phá và quản lý tài sản AI](../04-quan-tri/chuong-15-kham-pha-va-quan-ly-tai-san-ai.md)<br>[Chương 16 - Sinh hành vi và kiểm định chất lượng Agent](../04-quan-tri/chuong-16-sinh-hanh-vi-va-kiem-dinh-chat-luong.md) |
| Tối ưu | [Chương 17 - Tối ưu model](../05-toi-uu/chuong-17-toi-uu-model.md)<br>[Chương 18 - Tổng quan tối ưu Agent](../05-toi-uu/chuong-18-tong-quan-toi-uu-agent.md)<br>[Chương 19 - Dữ liệu Trajectory của Agent](../05-toi-uu/chuong-19-du-lieu-trajectory.md)<br>[Chương 20 - Xử lý dữ liệu runtime](../05-toi-uu/chuong-20-xu-ly-du-lieu-runtime.md)<br>[Chương 21 - Golden dataset cho Agent](../05-toi-uu/chuong-21-golden-dataset.md)<br>[Chương 22 - Tối ưu Agent qua badcase](../05-toi-uu/chuong-22-toi-uu-agent-badcase.md)<br>[Chương 23 - Tự tiến hoá có kiểm soát](../05-toi-uu/chuong-23-tu-tien-hoa-co-kiem-soat.md)<br>[Chương 24 - Edge Runtime và tối ưu toàn cầu](../05-toi-uu/chuong-24-edge-runtime-va-toi-uu-toan-cau.md) |
| Thực tiễn | [Chương 25 - Hiệu suất kỹ thuật](../06-thuc-tien/chuong-25-hieu-suat-ky-thuat/)<br>[Chương 26 - Design Engineering](../06-thuc-tien/chuong-26-design-engineering/)<br>[Chương 27 - Vận hành, bảo mật và IT doanh nghiệp](../06-thuc-tien/chuong-27-van-hanh-bao-mat-va-it-doanh-nghiep/)<br>[Chương 28 - Khách hàng, bán hàng và vận hành](../06-thuc-tien/chuong-28-khach-hang-ban-hang-va-van-hanh/)<br>[Chương 29 - GOAI Agent Infra](../06-thuc-tien/chuong-29-goai-agent-infra.md) |
| Tổng kết | [Chương 30 - Từ Agentic Application đến Agentic OS](../07-tong-ket/chuong-30-tu-agentic-application-den-agentic-os.md) |

### Danh mục Case Study

Các case study được tách thành danh mục riêng để có thể tiếp tục bổ sung, thay thế và mở rộng theo bối cảnh triển khai Agent tại Việt Nam.

| Chủ đề | Case study |
| --- | --- |
| Hiệu suất kỹ thuật | [ABACI: Agent kiểm thử có định hướng và phát hiện lỗi cho patch kernel](../06-thuc-tien/chuong-25-hieu-suat-ky-thuat/abaci-kiem-thu-patch-kernel-va-phat-hien-loi.md) |
| Hiệu suất kỹ thuật | [Kitta: Code Review Agent chuyên ngành](../06-thuc-tien/chuong-25-hieu-suat-ky-thuat/kitta-code-review-agent-chuyen-nganh.md) |
| Hiệu suất kỹ thuật | [PatchPilot Agents: biến việc bàn giao patch kernel thành vòng lặp kỹ thuật có thể điều phối và kiểm chứng](../06-thuc-tien/chuong-25-hieu-suat-ky-thuat/patchpilot-agents.md) |
| Hiệu suất kỹ thuật | [Từ cảnh báo đến tự động sửa lỗi: thực tiễn kỹ thuật Loop của PolarDB-X](../06-thuc-tien/chuong-25-hieu-suat-ky-thuat/polardb-x-tu-canh-bao-den-tu-dong-sua-loi.md) |
| Hiệu suất kỹ thuật | [Từ tăng tốc viết code đến bàn giao đầu cuối: cộng tác người–máy tại Cloud Communication](../06-thuc-tien/chuong-25-hieu-suat-ky-thuat/hop-tac-nguoi-may-tai-cloud-communication.md) |
| Hiệu suất kỹ thuật | [Từ eval-driven đến bàn giao đầu cuối: tăng hiệu suất phát triển sản phẩm bảo mật AI Agent](../06-thuc-tien/chuong-25-hieu-suat-ky-thuat/eval-driven-phat-trien-san-pham-bao-mat.md) |
| Hiệu suất kỹ thuật | [Đội Multi-Agent: AI trong R&D đi từ viết code tới bàn giao đầu cuối](../06-thuc-tien/chuong-25-hieu-suat-ky-thuat/doi-multi-agent-giao-hang-dau-cuoi.md) |
| Design Engineering | [GenUI: đưa Agent từ trả lời câu hỏi tới bàn giao kết quả](../06-thuc-tien/chuong-26-design-engineering/genui.md) |
| Design Engineering | [Vibe Designing: sự tiến hoá của paradigm thiết kế do AI dẫn dắt theo ý định](../06-thuc-tien/chuong-26-design-engineering/vibe-designing.md) |
| Vận hành và AIOps | [Thực tiễn triển khai AIOps tại Geely Auto](../06-thuc-tien/chuong-27-van-hanh-bao-mat-va-it-doanh-nghiep/geely-aiops.md) |
| Vận hành và AIOps | [Vòng lặp AIOps khép kín cho chuỗi cửa hàng Tastien](../06-thuc-tien/chuong-27-van-hanh-bao-mat-va-it-doanh-nghiep/tastien-aiops-chuoi-cua-hang.md) |
| Vận hành và AIOps | [Thực tiễn observability và AIOps tại Chanjet](../06-thuc-tien/chuong-27-van-hanh-bao-mat-va-it-doanh-nghiep/chanjet-observability-va-aiops.md) |
| Khách hàng và vận hành | [MiniMax xây dựng nền tảng dữ liệu bộ nhớ dài hạn quy mô lớn](../06-thuc-tien/chuong-28-khach-hang-ban-hang-va-van-hanh/minimax-nen-tang-du-lieu-memory.md) |
| Khách hàng và vận hành | [ShineWing ứng dụng Agent để nâng cao hiệu suất văn phòng](../06-thuc-tien/chuong-28-khach-hang-ban-hang-va-van-hanh/shinewing-nang-cao-hieu-suat-van-phong.md) |
| Khách hàng và vận hành | [Bilibili xây dựng năng lực phân tích nội dung toàn cục](../06-thuc-tien/chuong-28-khach-hang-ban-hang-va-van-hanh/bilibili-content-insight.md) |
| Khách hàng và vận hành | [Thực tiễn Data Agent cho phân tích vận hành](../06-thuc-tien/chuong-28-khach-hang-ban-hang-va-van-hanh/data-agent-phan-tich-van-hanh.md) |

Phần mô tả chi tiết cho từng chương cũng được duy trì tại [trang mục lục chính](../README.md). Các thuật ngữ sử dụng xuyên suốt cuốn sách được giải thích trong [Bảng thuật ngữ](../THUAT-NGU.md).

## Dành cho người xây dựng hệ thống thực tế

Cuốn sách hướng tới kỹ sư phát triển Agent, kiến trúc sư, kỹ sư nền tảng, nhân sự vận hành và bảo mật, người phụ trách chất lượng, cũng như các nhà quản lý kỹ thuật đang cân nhắc đưa Agent vào quy trình nghiệp vụ. Bạn không nhất thiết phải đọc tuần tự từ đầu đến cuối. Có thể bắt đầu từ vấn đề đang gặp phải, sau đó lần theo các liên kết giữa kiến trúc, xây dựng, vận hành, quản trị và tối ưu.

Trong một lĩnh vực thay đổi nhanh, tên sản phẩm, phiên bản giao thức và giới hạn của model sẽ liên tục dịch chuyển. Vì vậy, cuốn sách ưu tiên những nguyên tắc có thể sử dụng lâu dài: phân định trách nhiệm rõ ràng, duy trì state có thẩm quyền, cấp quyền tối thiểu, tách thực thi khỏi kiểm chứng, lưu lại bằng chứng, đánh giá bằng dữ liệu thực và lựa chọn kiến trúc theo mức rủi ro.

Thông điệp cốt lõi rất đơn giản: **một Agent hữu ích không chỉ cần thông minh; nó còn phải hoàn thành nhiệm vụ trong một hệ thống có thể kiểm soát, kiểm chứng và chịu trách nhiệm.** Cuốn sách này được xây dựng để giúp người đọc thiết kế hệ thống đó.
