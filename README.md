NYC Taxi Trip Data Analysis
Mô tả
Dự án này thực hiện phân tích dữ liệu các chuyến đi taxi tại thành phố New York bằng R và Apache Spark. Chương trình xử lý dữ liệu từ tập tin CSV, tính toán các thông số chuyến đi, nhóm dữ liệu theo ngày/giờ/ngày trong tuần và trực quan hóa thông tin thông qua ggplot2.

Cài đặt môi trường
Yêu cầu hệ thống
Hệ điều hành: Windows, macOS, Linux
Phần mềm: R (>= 4.0.0), RStudio
Thư viện:
sparklyr
dplyr
ggplot2
lubridate
Apache Spark (có thể cài qua sparklyr)
Cách cài đặt
Cài đặt R và RStudio:

Tải R và cài đặt
Tải RStudio và cài đặt
Cài đặt các thư viện cần thiết trong RStudio:

r
Sao chép
Chỉnh sửa
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
Clone repository và chạy mã:

Mở terminal và chạy lệnh:
sh
Sao chép
Chỉnh sửa
git clone <URL_GITHUB>
cd <TÊN_THƯ_MỤC_REPO>
Rscript PhantichTripdataNYC.R
Đảm bảo rằng file dữ liệu taxi được đặt đúng thư mục C:/DuLieu/TripDataNYC.csv hoặc cập nhật lại đường dẫn trong file PhantichTripdataNYC.R.
Các thư viện sử dụng
Thư viện	Chức năng
sparklyr	Kết nối với Apache Spark để xử lý dữ liệu lớn
dplyr	Xử lý dữ liệu với cú pháp dplyr
ggplot2	Trực quan hóa dữ liệu với biểu đồ
lubridate	Xử lý dữ liệu ngày giờ
spark_read_csv	Đọc dữ liệu từ tập tin CSV vào Spark
sdf_sample	Lấy mẫu dữ liệu từ Spark DataFrame
Mô tả các bước chính
Kết nối với Apache Spark
Đọc dữ liệu từ tập tin CSV
Xử lý dữ liệu:
Chuyển đổi kiểu dữ liệu ngày tháng
Tính toán thời gian chuyến đi (trip_duration)
Lọc các giá trị bất hợp lệ
Tính toán lại tổng chi phí
Nhóm dữ liệu theo ngày, giờ, ngày trong tuần
Trực quan hóa dữ liệu:
Số lượng chuyến đi theo ngày
Số lượng chuyến đi theo giờ
Biểu đồ cột số lượng chuyến đi theo ngày trong tuần
Phân phối giá cước (Fare Amount)
Quan hệ giữa thời gian chuyến đi và tổng chi phí
Chạy code
Mở RStudio
Chạy lệnh sau trong RStudio:
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
Kết quả
Biểu đồ số lượng chuyến đi theo ngày
Biểu đồ số lượng chuyến đi theo giờ
Biểu đồ số lượng chuyến đi theo các ngày trong tuần
Biểu đồ phân phối giá cước
Biểu đồ mối quan hệ giữa chi phí và thời gian chuyến đi
