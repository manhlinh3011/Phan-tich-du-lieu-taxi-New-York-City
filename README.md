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
   install.packages("sparklyr")
   install.packages("dplyr")
   install.packages("ggplot2")
   install.packages("lubridate")
Cài đặt Apache Spark:

Mở RStudio và chạy:
library(sparklyr)
spark_install()
Clone repository và chạy mã

