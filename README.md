# Thailand-PM2.5-Report
Power BI dashboard for reporting the daily PM2.5 in Thailand

## About
แดชบอร์ดนี้ทำขึ้นมาเพื่อเป็นการฝึกใช้ Power BI ในการทำ data visualize โดยหยิบข้อมูลที่มีการอัพเดตตลอดเวลาอย่างรายงานค่าฝุ่น (PM 2.5) ในประเทศไทยนี้มาทดลองสร้างแดชบอร์ดจริงจังครั้งแรก

[Data set ได้มาจาก open data.go.th](https://opendata.onde.go.th/en/dataset/14-pm-25) 

### Get data set
อันดับแรก ใส่ลิงค์ api ของดาต้าเพื่อเรียกข้อมูลเข้ามาใน Power BI 

![alt text](https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20162316.png "img 1")

ดาต้าที่ได้มามี column ที่เก็บข้อมูลเยอะมาก ดูได้จากเจ้า entity นี้ที่แสดง column ต่าง ๆ 

![alt text](https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20162439.png "img 2")


### Cleaning data

สำรวจดาต้าแล้ววางแผนว่าจะใช้อะไรบ้างในการสร้างแดชบอร์ด จากนั้นทำการลบ column ที่ไม่ใช้ทั้งหมดทิ้งไป

![alt text](https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20163235.png "img 3")

#### Column ที่นำมาใช้งาน

1. stationsName: รายชื่อของสถานีที่วัดคุณภาพอากาศ
2. พื้นที่: พื้นที่ของสถานี
3. province: จังหวัดของสถานี
4. lat: ละติจูดของสถานี
5. long: ลองจิจูดของสถานี
6. stations.AQILast.date: วันล่าสุดที่วัดคุณภาพอากาศ
7. stations.AQILast.PM25.color_id: ระดับคุณภาพอากาศ 0-5 โดย 0 คืออากาศดี 5 คืออากาศเป็นอันตราย
8. ค่าPM: ค่า PM 2.5 ที่วัดได้
9. stations.AQILast.AQI.param: เป็น column ที่ชี้ว่าฝุ่นในอากาศเป็นประเภทไหน


