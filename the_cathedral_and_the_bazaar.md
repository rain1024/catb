# Nhà thờ lớn và chợ trời

Tôi sẽ phân tích sự thành công của dự án nguồn mở, fetchmail, phần mềm được vận hành như là một kiểm thử cẩn thận của các nguyên lý đáng ngạc nhiên về kỹ nghệ phần mềm, được để xuất bởi lịch sử của Linux. 
Tôi sẽ thảo luận về những nguyên lý của hai phong cách phát triển cơ bản khác nhau hoàn toàn, mô hình `nhà thờ lớn` của hầu hết thế giới thương mại với mô hình `chợ giời` của thế giới Linux.
Tôi sẽ chỉ ra rằng những mô hình được để xuất từ những giả định đối nghịch về bản chất của nhiệm vụ tìm kiếm lỗi.
Tiếp theo đó, tôi sẽ chỉ ra các tham số chứng minh được từ kinh nghiệm của Linux cho nhận định rằng `Nếu mã nguồn được xem xét kỹ lưỡng thì lượng lỗi sẽ ít đi`, suggest productive analogies với hệ thống tự sửa lỗi của một đại lý ích kỷ, và kết luận với một số thăm dò ý nghĩa vào chi tiết cho tương lai của phần mềm.

## Nhà thờ lớn và chợ trời

Linux là một sự đột phá. 
Cách đây năm năm (1991), ai có thể nghĩ được rằng một hệ điều hành hàng đầu thế giới được kết hợp như một ma thuật của part-time hacking bởi hàng ngàn nhà phát triển phần mềm rải rác khắp trên thế giới, kết nối thông qua Internet?
Chắc chắn không phải tôi.
Thời gian Linux xuất hiện trong màn hình radar của tôi là đầu năm 1993, Tôi đã tham gia vào Unix và phát triển nguồn mở được 10 năm.
Tôi đã là một trong những người đóng góp cho GNU vào giữa khoảng thập niên 1980s.
Tôi đã đưa ra nhiều ý tưởng hay ho về phần mềm mã nguồn mở trên mạng, phát triển hay đồng phát triển nhiều chương trình (nethack, Emac's VC và mô hình GUD, xlife, và nhiều phần mềm khác nữa) vẫn đang được sử dụng ngày nay. 
Tôi nghĩ là mình hiểu được cách mà nó hoàn thành.

Linux làm thay đổi hoàn toàn những gì mà tôi nghĩ mình biết.
Tôi đã từng được "truyền giáo" về triết lý của Unix như là các công cụ nhỏ, phát triển bản mẫu nhanh, và sự tiến hoá của phần mềm theo thời gian.
Nhưng tôi cũng tin rằng có một sự phức tạp quan trọng nhất định vượt qua các cách tiếp cận tập trung, một cách tiếp cận ưu tiên là cần thiết.
Tôi tin rằng các phần mềm quan trọng nhất (hệ điều hành và các công cụ phức tạp như trình soạn thảo lập trình Emacs) cần được xây dựng như một nhà thờ lớn, được xây dựng một cách cẩn thận bởi một kỹ sư tài năng hoặc một nhóm nhỏ trong một môi trường độc lập, không có bản beta nào được phát hành cho đến khi nó được phát hành.

Phương pháp phát triển của Linus Torvalds - phát hành thường xuyên và sớm, uỷ thác nhiều nhất có thể cho bạn, mở đến mức hỗn loạn - mang đến nhiều điều ngạc nhiên.
Không phải kiểu xây dựng các nhà thờ lớn, tôn kính và yên tĩnh ở đây, thay vào đó, một cộng đồng Linux giống như một cái chợ ồn ào, náo nhiệt bao gồm nhiều chương trình và cách tiếp cận khác nhau (hình ảnh đặc trưng nhất là trang web lưu trữ của Linux, nơi chấp nhận các bài viết từ mọi người) tới một hệ thống liên kết và ổn định dường như chỉ xuất hiện bởi hàng loạt các phép lạ.

Thực tể chỉ ra rằng phương pháp chợ trời dường như hoạt động, thậm chí rất tốt là đằng khác, đến như một cú sốc khác biệt.
Theo kinh nghiệp của bản thân, tôi đã làm việc chăm chỉ không những trong các dự án cá nhân, mà còn cố gắng để hiểu tại sao Linux có thể hoạt động không những không ngập trong các rối rắm mà còn vận hành trơn tru, mạnh mẽ, nhanh như trong việc xây dựng các nhà thờ.

Giữa năm 1996 tôi nghĩ mình đã bắt đầu hiểu được tại sao.
Tôi đã có một cơ hội hoàn hảo để kiểm chứng lại các lý thuyết của mình, dưới dạng một dự án nguồn mở mà tôi cố gắng vận dụng phong cách chợ trời.
Vì vậy, tôi đã áp dụng phương pháp đó và đạt được một số thành công đáng kể.

Sau đây là câu chuyện của dự án đó.
Tôi sẽ sử dụng nó để đề xuất một số aphorisms về phát triển nguồn mở hiệu quả.
Những điều này không phải là tất cả những bài học vỡ lòng tôi đã học được từ thế giới Linux, nhưng chúng ta sẽ thấy cách mà thế giới Linux mang lại những điểm cụ thể như thế nào. 
Nếu như tôi đúng, chúng sẽ giúp bạn hiểu được chính xác điều gì làm cho cộng đồng Linux trở thành một tập hợp các phần mềm chất lượng, và có lẽ chúng sẽ giúp bạn trở nên hiệu quả hơn.
