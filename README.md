# Thailand-PM2.5-Report
Power BI dashboard for reporting the daily PM2.5 in Thailand

## About
<p>&emsp; แดชบอร์ดนี้ทำขึ้นมาเพื่อเป็นการฝึกใช้ Power BI ในการทำ data visualize โดยหยิบข้อมูลที่มีการอัพเดตตลอดเวลาอย่างรายงานค่าฝุ่น (PM 2.5) ในประเทศไทยนี้มาทดลองสร้างแดชบอร์ดจริงจังครั้งแรก</p>

[Data set ได้มาจาก open data.go.th](https://opendata.onde.go.th/en/dataset/14-pm-25) 



### Get data set
<p>&emsp;อันดับแรก ใส่ลิงค์ api ของดาต้าเพื่อเรียกข้อมูลเข้ามาใน Power BI </p>

<p align="center">
&nbsp;<img src = "https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20162316.png" width = "500"/>
</p>


<p>&emsp;ดาต้าที่ได้มามี column ที่เก็บข้อมูลเยอะมาก ดูได้จากเจ้า entity นี้ที่แสดง column ต่าง ๆ </p>

<p align="center">
&nbsp;<img src = "https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20162439.png " width = "500"/>
</p>



### Cleaning data

<p>&emsp;สำรวจดาต้าแล้ววางแผนว่าจะใช้อะไรบ้างในการสร้างแดชบอร์ด จากนั้นทำการลบ column ที่ไม่ใช้ทั้งหมดทิ้งไป </p>

<p align="center">
&nbsp;<img src = "https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20163235.png " width = "500"/>
</p>


#### Column ที่นำมาใช้งาน

- stationsName: รายชื่อของสถานีที่วัดคุณภาพอากาศ
-  พื้นที่: พื้นที่ของสถานี
-  province: จังหวัดของสถานี
-  lat: ละติจูดของสถานี
-  long: ลองจิจูดของสถานี
-  stations.AQILast.date: วันล่าสุดที่วัดคุณภาพอากาศ
-  stations.AQILast.PM25.color_id: ระดับคุณภาพอากาศ 0-5 โดย 0 คืออากาศดี 5 คืออากาศเป็นอันตราย ซึ่งนำข้อมูลจาก ค่าPM มาเป็นตัวแบ่ง
-  ค่าPM: ค่า PM 2.5 ที่วัดได้
-  stations.AQILast.AQI.param: เป็น column ที่ชี้ว่าฝุ่นในอากาศเป็นประเภทไหน


<p>&emsp; เนื่องจากว่าข้อมูลนั้นมี row ไม่เยอะ พอจะตรวจสอบแบบ manual ไหว ทุก column นั้นปกติดี จนกระทั่งไปเจอกับสิ่งนี้ใน stations.AQILast.date</p>

<p align = "center">
  &nbsp;<img src ="https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20164418.png" width = "500">
</p>

<p>&emsp; ที่ row 19 และ 22 สองสถานีไม่มีการอัพเดตมาสักพักแล้วนั่นเอง เพื่อไม่ให้ข้อมูล (ค่า PM) มีความผิดพลาดในภาพรวม จึงลบสองสถานีนี้ออกไปก่อน (ช่วงเริ่มทำ project นี้ ก่อนที่จะนำมาลงแพลตฟอร์มออนไลน์ เคยมีสถานีที่ไม่อัพเดตมานานกว่า 5 เดือน แต่ปัจจุบันก็อัพเดตสถานะทุกวันเป็นปกติ ดังนั้น ถึงลบออกไปแล้วก็ควรกลับมาเช็คบ่อย ๆ เพื่อนำสถานีเหล่านั้นกลับมาแสดงบนแดชบอร์ดให้เป็นปกติ)</p>


#### เพิ่ม Data set อีกชุด

<p>&emsp; หลังจากเตรียมข้อมูลชุดนี้เสร็จแล้ว ก็นึกได้ว่าเรามี data set ที่แบ่งจังหวัดในระเทศไทยตามภูมิภาคนี่นา (ซึ่งจริง ๆ แล้วมานึกได้ทีหลังด้วย ฮา) พอนำ data ชุดนี้เข้ามา Power BI ก็จัดการผูก relationship ของ 2 entity ให้เลย เพราะมี column ที่ชื่อว่า provine และ value ที่สามารถนำมาอ้างอิงถึงกันได้ </p> 

<p align= "center"> 
  &nbsp;<img src ="https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-27%20163503.png" width = "500"/>
</p>

#### สร้าง Dashboard

<p>&emsp; สร้างแดชบอร์ดรายงานค่าฝุ่น PM 2.5 รายวัน</p> 

<p align = "center">
   &nbsp;<img src = "https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-28%20132732.png" width = "500"/>
</p>

<p>
&emsp; อธิบายแต่ละส่วนในแดชบอร์ด
</p>

- <p><b>PM 2.5 ตามภูมิภาค</b> ใช้ stacked bar chart ในการแสดงค่าเฉลี่ย PM2.5 ในแต่ละภูมิภาคและจัดเรียงตามภูมิภาคที่มีค่าเฉลี่ย PM.2.5 มากที่สุดไปหาน้อยสุด</p>
- <p><b>สัดส่วนระดับ PM 2.5</b> ใช้ pie chart แสดงสัดส่วนของระดับ PM 2.5 ตั้งแต่ระดับ 1 - 5 (หรือ 1 - ระดับสูงสุดในตอนนี้) ดูภาพรวมว่าส่วนใหญ่ระดับฝุ่นในอากาศเป็นยังไง โดยใช้ stationsName มา count(นับจำนวนสถานี)เป็น value และใช้ stations.AQILast.PM25.color_id ในการแบ่งสัดส่วนของ chart</p>
- <p><b>ระดับ PM 2.5</b> ตรงส่วนนี้ใช้ slicer แบบ tile ทำงานร่วมกับ ArcGIS Maps เจ้า slicer มีไว้เลือกระดับPM (1-5 หรือ 1 - ค่าPMสูงสุดตอนนั้น) และ maps จะ plot สถานีที่เข้าเงื่อนไขทั้งหมด ใช้ lat, long ในการระบุตำแหน่ง</p>
- <p><b>วันที่</b> แสดงวันที่ของ data set ที่รายงานอยู่ตอนนี้โดย stations.AQILast.date </p>
- <p><b>จังหวัด</b> ใช้ slicer ในการแสดงทุกจังหวัดแบบ dropdown โดยใช้ province จาก data set ตัวแรกที่เราดึง api มา</p>
- <p><b>การ์ดแสดงค่าPM 2.5</b> แสดงค่า PM 2.5 ที่มากที่สุด และ น้อยที่สุด พร้อมทั้งระดับและจังหวัดดังกล่าว โดยใช้ ค่าPM, stations.AQILast.PM25.color_id, province ทำงานร่วมกัน</p>
&emsp; ในภาพอาจจะเห็นว่าค่า PM 2.5 มากที่สุดตอนนี้(28/8/2023) คือ 31 และอยู่ใน ระดับ 3 เท่านั้น แต่ในเดือนเมษายนปีนี้ (ข้อมูลจากไฟล์ภาพ) ประเทศไทยเคยมีค่า PM 2.5 สูงถึง 241 ระดับ 5 เป็นระดับสูงสุดของการจัดระดับนั่นเอง (ช่วงนั้นเป็นช่วงที่ค่า PM 2.5 ในประเทศไทยเยอะมาก เป็นเหตุผลที่ทำให้เราเลือก data set ชุดนี้ทำ project ตัวนี้ด้วย)

<p align = "center">
  &nbsp; <img src = "https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-04-15%20150719.png" width = "500"/>
</p>

- <p><b>5 อันดับที่พบPM 2.5 มากที่สุด</b>ใช้ table ในการแสดงค่าโดยเลือก ค่าPM2.5, จังหวัด, พื้นที่ และใช้ค่าPM2.5 ฟิลเตอร์ ค่าที่มากที่สุด 5 อันดับ</p>


#### ใช้งาน Dashboard
&emsp; โดยฟิลเตอร์ภาคเหนือ และเลือกระดับ 2 จะได้ภาพแบบนี้
<p align = "center">
  &nbsp;<img src = "https://github.com/nittayattngx/Thailand-PM2.5-Report/blob/main/pm25img/Screenshot%202023-08-28%20141413.png" width = "500">
</p>
<p>
<p>
<p>
<p>&emsp; project ตัวนี้ก็สิ้นสุดลงที่กระบวนการทำ visualization ตรงนี้</p>
