# Data_Analytics_Logistic_Project
Phân tích doanh thu bán hàng, tỷ lệ sản phẩm và tìm ra các yếu tố ảnh hưởng đến việc giao hàng trễ của một công ty Logistic

# Quy trình xử lý dữ liệu và kết quả đạt được
**1. Thư viện được sử dụng**__
Các thư viện Python sau được sử dụng để phân tích và xử lý dữ liệu:

- **numpy:** hỗ trợ các phép tính toán trên mảng số học.
- **pandas:** để quản lý và thao tác với các cấu trúc dữ liệu bảng.
- **matplotlib và seaborn:** vẽ biểu đồ trực quan.
- **scikit-learn:** các mô hình và công cụ học máy như Logistic Regression, Isolation Forest, StandardScaler, và LabelEncoder.

**2. Đọc dữ liệu**
Dữ liệu được đọc từ tệp CSV có tên LogisticDataset.csv với mã hóa ISO-8859-1 để tránh lỗi ký tự. Kết quả là bảng dữ liệu gồm 53 cột và 180,519 dòng.

**3. Tiền xử lý dữ liệu**
Loại bỏ các cột không cần thiết: Một số cột như thông tin cá nhân và các cột không liên quan đến phân tích được loại bỏ.
Kiểm tra dữ liệu null và trùng lặp: Không có giá trị null và không có dòng trùng lặp.
Chuyển đổi dữ liệu: Các cột ngày/tháng được chuyển đổi sang định dạng ngày hợp lệ.

**4. Tính toán tỷ lệ phần trăm tích lũy của tổng doanh thu đóng góp của từng loại sản phẩm**

Mục tiêu: Xác định tỷ lệ đóng góp của mỗi danh mục sản phẩm vào tổng doanh số.

Biểu đồ: Một biểu đồ thanh ngang cho thấy tỷ lệ lũy kế của các danh mục sản phẩm, với các danh mục được xếp hạng theo doanh số từ cao đến thấp.

![image](https://github.com/user-attachments/assets/a24aa61f-fb2e-4149-994e-23cbaba7e66b)


**5. Phân tích độ co dãn của cầu (Price Elasticity of Demand - PED)**

Mục tiêu: Tính PED để đánh giá sự thay đổi về lượng bán khi giá sản phẩm thay đổi.

Kết quả: Tìm ra các sản phẩm có sự thay đổi lớn nhất về PED. Biểu đồ thanh cho thấy top 3 sản phẩm có sự biến động đáng kể về PED.

![image](https://github.com/user-attachments/assets/231862d0-a961-4859-a71f-530981013739)


**6. Phân tích tỷ lệ giao hàng trễ**

Mục tiêu: Đánh giá tỷ lệ giao hàng trễ theo khu vực và phương thức giao hàng.

Kết quả: Biểu đồ nhiệt thể hiện tỷ lệ giao hàng trễ theo khu vực và phương thức giao hàng, cho thấy sự phân bố rõ rệt giữa các khu vực.

![image](https://github.com/user-attachments/assets/46581f90-1072-4c7e-b753-845fac0d3b51)

![image](https://github.com/user-attachments/assets/b00ee3cb-f43d-4b35-95c2-a5fcdb2b08d3)



**7. Mô hình hồi quy Logistic để phân tích các yếu tố ảnh hưởng đến việc trễ giao hàng**

Mục tiêu: Sử dụng Logistic Regression để phân tích các yếu tố ảnh hưởng đến rủi ro giao hàng trễ.

Kết quả: Xác định được các biến quan trọng nhất ảnh hưởng đến việc giao hàng trễ, trong đó ba yếu tố hàng đầu là:
- Khu vực đặt hàng (Order Region),
- Số lượng sản phẩm (Order Item Quantity),
- Phương thức giao hàng (Shipping Mode).

Đánh giá mô hình: Độ chính xác mô hình đạt được là 69,6%, với bảng ma trận và báo cáo phân loại cho các chỉ số như Precision và Recall.
