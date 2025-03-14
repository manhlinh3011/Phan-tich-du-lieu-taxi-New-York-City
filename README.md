# 🚖 NYC Taxi Trip Data Analysis

## 📌 Giới thiệu
Dự án này thực hiện phân tích dữ liệu các chuyến đi taxi tại thành phố New York bằng **R** và **Apache Spark**. Chương trình xử lý dữ liệu từ tập tin CSV, tính toán các thông số chuyến đi, nhóm dữ liệu theo ngày/giờ/ngày trong tuần và trực quan hóa dữ liệu bằng `ggplot2`.  

## 🛠️ Cài đặt môi trường

### 📌 Yêu cầu hệ thống
- **Hệ điều hành**: Windows, macOS, Linux  
- **Phần mềm**: R (>= 4.0.0), RStudio  
- **Thư viện cần cài đặt**:  
  - `sparklyr`
  - `dplyr`
  - `ggplot2`
  - `lubridate`  
  - **Apache Spark** (có thể cài qua `sparklyr`)

### 🔧 Cách cài đặt
1. **Cài đặt R và RStudio**  
   - [Tải R](https://cran.r-project.org/) và cài đặt  
   - [Tải RStudio](https://posit.co/download/rstudio-desktop/) và cài đặt  

2. **Cài đặt các thư viện cần thiết** trong RStudio:  
   ```r
   install.packages("sparklyr")
   install.packages("dplyr")
   install.packages("ggplot2")
   install.packages("lubridate")
Cài đặt Apache Spark:

Mở RStudio và chạy:
r
Sao chép
Chỉnh sửa
library(sparklyr)
spark_install()
Clone repository và chạy mã

sh
Sao chép
Chỉnh sửa
git clone <URL_GITHUB>
cd <TÊN_THƯ_MỤC_REPO>
Rscript PhantichTripdataNYC.R
📌 Đảm bảo rằng file dữ liệu taxi được đặt đúng thư mục C:/Du_lieu_lon/yellow_tripdata_2015-01_lam_sach.csv hoặc cập nhật lại đường dẫn trong file PhantichTripdataNYC.R.

📚 Các thư viện sử dụng
📦 Thư viện	🔍 Chức năng
sparklyr	Kết nối Apache Spark để xử lý dữ liệu lớn
dplyr	Xử lý dữ liệu với cú pháp dplyr
ggplot2	Trực quan hóa dữ liệu với biểu đồ
lubridate	Xử lý dữ liệu ngày giờ
spark_read_csv	Đọc dữ liệu CSV vào Spark
sdf_sample	Lấy mẫu dữ liệu từ Spark DataFrame
🔎 Quy trình phân tích dữ liệu
Kết nối với Apache Spark
Đọc dữ liệu từ tập tin CSV
Xử lý dữ liệu:
Chuyển đổi kiểu dữ liệu ngày tháng
Tính toán thời gian chuyến đi (trip_duration)
Lọc các giá trị bất hợp lý
Tính tổng chi phí chuyến đi
Nhóm dữ liệu theo ngày, giờ, ngày trong tuần
Trực quan hóa dữ liệu:
📊 Số lượng chuyến đi theo ngày
⏳ Số lượng chuyến đi theo giờ
📅 Biểu đồ số lượng chuyến đi theo ngày trong tuần
💰 Phân phối giá cước (fare_amount)
🔄 Quan hệ giữa thời gian chuyến đi và tổng chi phí
📊 Hướng dẫn chạy code
Mở RStudio
Kết nối với Spark
r
Sao chép
Chỉnh sửa
library(sparklyr)
library(dplyr)
library(ggplot2)
library(lubridate)

# Kết nối Spark
sc <- spark_connect(master = "local")
Chạy file phân tích
r
Sao chép
Chỉnh sửa
source("PhantichTripdataNYC.R")
✅ Kết quả mong đợi
🔹 Biểu đồ số lượng chuyến đi theo ngày
🔹 Biểu đồ số lượng chuyến đi theo giờ
🔹 Biểu đồ số lượng chuyến đi theo các ngày trong tuần
🔹 Biểu đồ phân phối giá cước
🔹 Biểu đồ mối quan hệ giữa chi phí và thời gian chuyến đi
