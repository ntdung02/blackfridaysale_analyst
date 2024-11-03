# Black Friday Sale Analysis
Black Friday là dịp mua sắm lớn nhất trong năm với các chương trình giảm giá hấp dẫn, thu hút đông đảo người tiêu dùng. Việc phân tích dữ liệu từ Black Friday giúp hiểu rõ hơn về hành vi và xu hướng mua sắm, qua đó xác định các nhóm khách hàng tiềm năng và sản phẩm bán chạy. Dataset Black Friday Sale này chứa các thông tin về giới tính, độ tuổi, nghề nghiệp và sản phẩm, cung cấp nền tảng để khám phá những yếu tố tác động đến quyết định mua hàng và hỗ trợ doanh nghiệp tối ưu hóa chiến lược kinh doanh.

Nguồn dữ liệu: https://www.kaggle.com/datasets/rajeshrampure/black-friday-sale

## Giới Thiệu Về Bộ Dữ Liệu
Tập dữ liệu có 550068 bản ghi và 7 cột. Bộ dữ liệu này được thống kê từ số liệu tập hợp giao dịch mua hàng trong dịp lễ Black Friday của một công ty bán lẻ tại một thành phố của Mỹ.

Chi tiết từng cột 

- User_ID: Mã khách hàng đến mua hàng
- Product_ID: Mã sản phẩm
- Gender: Giới tính (Male - Female)
- Age: Độ tuổi ( 0-17, 18-25, 26-35 , 36-45, 45-50, 51-55, 55+ )
- Marital_Status: Tình trạng hôn nhân (Married, UnMarried)
- Quantity : Số lượng mua
- Purchase : Tổng số tiền mua

## Xử lý và làm sạch dữ liệu
Đối với bộ dữ liệu này không có các giá trị trùng lặp, chỉ có cột UserID  đang định dạng kiểu Decimal Number vì vậy cần thay đổi sang kiểu Text

![image](https://github.com/user-attachments/assets/a217d09d-64a5-4902-9193-74ef1ac52064)


Ở cột Quantity có một số giá trị bị thiếu ( số giá thị thiếu là rất nhỏ) vì vậy cần xoá các dòng có chứa giá trị Quantity bị thiếu đó đi

![image](https://github.com/user-attachments/assets/92f1e460-fbe5-4096-b91c-dd4a9dda5a3a)

Vì dự án này tập trung phân tích nhân khẩu học tác động đến hành vi mua sắm và báo cáo kết quả bán hàng nên mình đã tạo ra 2 bảng: Bảng User (chứa thông tin của khách hàng) và bảng Total_Purchase (chứa thông tin của giá trị đơn hàng và số lượng mua của khách). Cả 2 bảng này được tách ra từ bảng Train của tập dữ liệu

![image](https://github.com/user-attachments/assets/1691f84e-7512-41cc-a947-743ca31375a1)

## Phân tích các yếu tố tác động đến hành vi mua sắm và kết quả bán hàng

- Phân tích yếu tố Giới tính tác đông đến mức chi tiêu mua sắm

![image](https://github.com/user-attachments/assets/83e6ec29-89a5-4576-8c1a-4966815073f8)

Biểu đồ tròn thể hiện số lượng người mua hàng theo giới tính  và biểu đồ cột có thể hiện giá mua sắm theo từng nhóm Giới tính. Phần lớn người mua hàng là nam giới, chiếm khoảng 75.31% tổng số lượng.
Nữ giới chiếm 24.69% tổng số lượng người mua hàng. Bên cạnh đó Nam giới có tổng chi tiêu lớn hơn đáng kể, đạt đến 3910M trong khi nữ giới có tổng chi tiêu là 1186M, thấp hơn nam giới.

Nhận xét Nhận xét: Nam giới không chỉ chiếm số lượng lớn hơn mà còn có giá trị mua sắm cao hơn đáng kể.  Điều này có thể do các yếu tố như sở thích mua sắm của nam giới hoặc các sản phẩm mà họ quan tâm, ví dụ như các mặt hàng công nghệ/điện tử trong Black Friday, nơi nam giới thường có xu hướng mua sắm nhiều hơn. Nữ giới, mặc dù có tỷ lệ mua hàng thấp hơn, nhưng vẫn chi tiêu đáng kể trong danh mục sản phẩm.
Tỷ lệ phân bố và chi tiêu khá tương đồng - khoảng 70/30 cho cả hai chỉ số. Vì vậy cần có chiến lược marketing riêng cho phân khúc nữ giới để tăng tỷ lệ khách hàng, đa dạng hóa sản phẩm để thu hút cả hai giới

- Phân tích yếu tố Tình trạng hôn nhân tác động đến mức chi tiêu mua sắm

![image](https://github.com/user-attachments/assets/5d802786-3a04-4c9a-a3da-44bfa7d9feea)

Phần lớn người mua hàng là chưa kết hôn, chiếm 59.03%, người đã kết hôn chiếm 40.97% trong tổng số người mua hàng, người chưa kết hôn chiếm đa số trong cả tỷ lệ người mua hàng và tổng chi tiêu. Trong khi mức Chi Tiêu Theo Tình Trạng Hôn Nhân: người chưa kết hôn có tổng mức chi tiêu cao hơn, đạt 3.0 tỷ, người đã kết hôn có tổng mức chi tiêu thấp hơn, ở mức 2.1 tỷ.

Nguyên nhân có thể là do người chưa kết hôn có nhu cầu mua sắm cá nhân nhiều hơn hoặc ít chịu ảnh hưởng của chi tiêu gia đình. Tuy nhiên, người đã kết hôn cũng có mức chi tiêu đáng kể, có thể là do nhu cầu mua sắm cho gia đình và con cái.

- Phân tích yếu tố Tình trạng hôn nhân và Độ tuổi (mối tương quan giữa chúng) đã tác động đến mức chi tiêu mua sắm

![image](https://github.com/user-attachments/assets/06296e2c-44a4-46a2-9391-0d3874fbcfc7)

Nhóm tuổi 26-35 có mức chi tiêu cao nhất, đặc biệt là những người chưa kết hôn. Nhóm này chi tiêu khoảng 1.2 tỷ (UnMarried) và 0.8 tỷ (Married), với tổng cộng là 2 tỷ. Đây có thể là nhóm có thu nhập ổn định nhưng chưa có quá nhiều trách nhiệm gia đình, nên sẵn sàng chi tiêu nhiều cho bản thân hoặc nhu cầu cá nhân.

Nhóm tuổi 36-45 cũng chi tiêu ở mức tương đối cao, với khoảng 0.6 tỷ cho người chưa kết hôn và 0.4 tỷ cho người đã kết hôn. Điều này có thể do nhóm này có xu hướng ổn định về sự nghiệp và gia đình, nên chi tiêu được tập trung cho các nhu cầu của gia đình hơn là bản thân.

Nhóm tuổi 18-25 có tổng chi tiêu 0.7 tỷ, với người chưa kết hôn chiếm tỷ lệ lớn. Nhóm này có thể bao gồm những người mới bắt đầu đi làm, có thu nhập hạn chế nhưng lại có xu hướng chi tiêu nhiều cho trải nghiệm cá nhân, đặc biệt khi chưa kết hôn  vì ít phải lo lắng về trách nhiệm gia đình

Nhóm tuổi 46-50 và 51-55 có mức chi tiêu thấp hơn đáng kể, với tổng cộng khoảng 0.3 tỷ mỗi nhóm. Độ tuổi này thường đã có gia đình và những chi phí lớn khác như chăm sóc con cái hoặc chuẩn bị cho hưu trí, dẫn đến hạn chế hơn trong chi tiêu mua sắm cá nhân.

Nhóm 55+ và 0-17 có mức chi tiêu rất thấp. Người từ 55 tuổi trở lên có thể đang tiết kiệm hoặc tập trung chi tiêu cho sức khỏe và hưu trí. Còn nhóm 0-17 không có thu nhập riêng nên thường phụ thuộc vào gia đình trong việc mua sắm.

- Hành vi mua sắm

![image](https://github.com/user-attachments/assets/c9494cac-8bc6-4352-9a9f-0088de506dc0)

Biểu đồ cho thấy mối quan hệ tỷ lệ thuận giữa số lượng và giá trị đơn hàng, cho thấy rằng khách hàng có xu hướng tăng số lượng mua sắm khi họ muốn đạt giá trị đơn hàng cao hơn.

Phần lớn các điểm dữ liệu nằm ở mức dưới 2000 đơn vị với giá trị đơn hàng từ 0 đến khoảng 2 triệu. Điều này cho thấy hầu hết khách hàng mua với số lượng vừa phải và có giới hạn về chi tiêu cho mỗi đơn hàng.
Đây có thể là các khách hàng mua lẻ, chỉ mua sản phẩm phục vụ nhu cầu cá nhân hoặc mua thử.

Một số điểm nằm ở khu vực số lượng từ 3000 đến 6000 với giá trị đơn hàng từ 6 triệu đến trên 10 triệu. Những khách hàng này có thể là những người mua sắm theo số lượng lớn, có nhu cầu cao về sản phẩm (như đại lý bán lẻ, người bán buôn, hoặc các doanh nghiệp). Điều này cho thấy rằng có một phân khúc khách hàng sẵn sàng chi tiêu cao hơn nếu họ nhận được giá trị tương xứng, có thể là do giá sản phẩm cao hoặc số lượng lớn sản phẩm.

Các điểm dữ liệu phân tán cho thấy có sự khác biệt trong hành vi chi tiêu giữa các khách hàng. Một số khách hàng chi tiêu rất cao với lượng mua lớn, trong khi những người khác chi tiêu ít và mua số lượng nhỏ.
Điều này chỉ ra rằng có nhiều phân khúc khách hàng khác nhau với nhu cầu và khả năng chi tiêu khác nhau, từ những người chỉ mua sản phẩm thiết yếu hoặc có nhu cầu nhỏ đến những khách hàng mua sắm với mục đích kinh doanh hoặc bán lại.


![image](https://github.com/user-attachments/assets/45d87a95-4afb-4c4e-b92e-1b4e01992482)


Bảng điều khiển bên dưới thể hiện kết quả bán hàng trong dịp lễ Black Friday, với các chỉ số về Doanh thu bán hàng, số lượng người mua, số lượng sản phẩm bán ra, giá trị trung bình của các đơn hàng, top các sản phẩm có lượt bán cao nhất và doanh thu thu về cao nhất, mức độ tập trung của giá trị đơn và số lượng mua của khách hàng. Kèm theo là các bộ lọc để dễ dàng theo dõi kết quả bán hàng.

![image](https://github.com/user-attachments/assets/c08c7b99-da2b-493c-9d6b-d4742e0ba95a)








