# Black Friday Sale Analysis
Black Friday là dịp mua sắm lớn nhất trong năm với các chương trình giảm giá hấp dẫn, thu hút đông đảo người tiêu dùng. Việc phân tích dữ liệu từ Black Friday giúp hiểu rõ hơn về hành vi và xu hướng mua sắm, qua đó xác định các nhóm khách hàng tiềm năng và sản phẩm bán chạy. Dataset Black Friday Sale này chứa các thông tin về giới tính, độ tuổi, nghề nghiệp và sản phẩm, cung cấp nền tảng để khám phá những yếu tố tác động đến quyết định mua hàng và hỗ trợ doanh nghiệp tối ưu hóa chiến lược kinh doanh.

Nguồn dữ liệu: https://www.kaggle.com/datasets/rajeshrampure/black-friday-sale

## Giới Thiệu Về Bộ Dữ Liệu
Tập dữ liệu có 550068 bản ghi và 10 cột

Chi tiết từng cột 

- User_ID: Mã khách hàng đến mua hàng
- Product_ID: Mã sản phẩm
- Gender: Giới tính (Male - Female)
- Age: Độ tuổi ( 0-17, 18-25, 26-35 , 36-45, 45-50, 51-55, 55+ )
- Occupation: Ngành nghề (thông tin này được mã hoá nên sẽ dùng các số nguyên 1,2,3,... để tượng)
- City_Category: Khu vực thành phố (A, B, C)
- Stay_In_Current_City_Years: Số năm sống tại thành phố hiện tại của khách hàng (1, 2, 3, 4+ )
- Marital_Status: Tình trạng hôn nhân (Married, UnMarried)
- Product_Category_1 : Số lượng mua
- Purchase : Tổng số tiền mua

## Xử lý và làm sạch dữ liệu

