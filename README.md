# Thailand-PM2.5-Report
Power BI dashboard for reporting the daily PM2.5 in Thailand

## About
<p>&nbsp แดชบอร์ดนี้ทำขึ้นมาเพื่อเป็นการฝึกใช้ Power BI ในการทำ data visualize โดยหยิบข้อมูลที่มีการอัพเดตตลอดเวลาอย่างรายงานค่าฝุ่น (PM 2.5) ในประเทศไทยนี้มาทดลองสร้างแดชบอร์ดจริงจังครั้งแรก</p>

[Data set ได้มาจาก open data.go.th](https://opendata.onde.go.th/en/dataset/14-pm-25) 



### Get data set
<p>&nbspอันดับแรก ใส่ลิงค์ api ของดาต้าเพื่อเรียกข้อมูลเข้ามาใน Power BI </p>

<p align="center">
&nbsp;<img src = "https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20162316.png" width = "500"/>
</p>


<p>&nbspดาต้าที่ได้มามี column ที่เก็บข้อมูลเยอะมาก ดูได้จากเจ้า entity นี้ที่แสดง column ต่าง ๆ </p>

<p align="center">
&nbsp;<img src = "https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20162439.png " width = "500"/)
</p>



### Cleaning data

<p>&nbspสำรวจดาต้าแล้ววางแผนว่าจะใช้อะไรบ้างในการสร้างแดชบอร์ด จากนั้นทำการลบ column ที่ไม่ใช้ทั้งหมดทิ้งไป </p>

<p align="center">
&nbsp;<img src = "https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20163235.png " width = "500"/)
</p>


#### Column ที่นำมาใช้งาน

- stationsName: รายชื่อของสถานีที่วัดคุณภาพอากาศ
-  พื้นที่: พื้นที่ของสถานี
-  province: จังหวัดของสถานี
-  lat: ละติจูดของสถานี
-  long: ลองจิจูดของสถานี
-  stations.AQILast.date: วันล่าสุดที่วัดคุณภาพอากาศ
-  stations.AQILast.PM25.color_id: ระดับคุณภาพอากาศ 0-5 โดย 0 คืออากาศดี 5 คืออากาศเป็นอันตราย
-  ค่าPM: ค่า PM 2.5 ที่วัดได้
-  stations.AQILast.AQI.param: เป็น column ที่ชี้ว่าฝุ่นในอากาศเป็นประเภทไหน




