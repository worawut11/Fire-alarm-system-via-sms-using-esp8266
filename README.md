Fire-alarm-system-via-sms-using-esp8266
ระบบแจ้งเตือนไฟไหม้ผ่าน sms โดยใช้ esp8266 #ขั้นตอนการทำงานงานของระบบแจ้งเตือนไฟไหม็ผ่าน SMS โดยใช้ ESP8266

การวางแผนโครงการ กำหนดเป้าหมาย:
พัฒนาระบบที่สามารถตรวจจับควัน แจ้งเตือนผ่าน SMS และควบคุมพัดลมดูดอากาศอัตโนมัติ การเตรียมอุปกรณ์:

1.ไมโครคอนโทรลเลอร์ ESP8266 (NodeMCU)

2.Gas Sensor (เช่น MQ-2 หรือ MQ-135)

3.โมดูลรีเลย์

4.พัดลมดูดอากาศ

5.สายไฟและ Breadboard

6.แหล่งจ่ายไฟ

วางแผนซอฟต์แวร์:

1.ใช้ Twilio API สำหรับส่งข้อความ SMS

2.เขียนโค้ดด้วย Arduino IDE

การเตรียมอุปกรณ์ฮาร์ดแวร์
ประกอบวงจร:

1.เชื่อมต่อ Gas Sensor กับพิน A0 ของ ESP8266

2.เชื่อมต่อโมดูลรีเลย์กับพินดิจิทัล (เช่น D1) เพื่อควบคุมพัดลม

3.ตรวจสอบแรงดันไฟฟ้าของอุปกรณ์ (ใช้ 5V หรือ 3.3V ตามอุปกรณ์ที่เลือก)

ตรวจสอบการทำงานของเซ็นเซอร์:

4.อ่านค่าที่เซ็นเซอร์ส่งออกมาโดยใช้คำสั่ง analogRead() เพื่อวัดระดับควัน

การตั้งค่าและทดสอบ ESP8266
การติดตั้ง Arduino IDE และไลบรารี:

1.ดาวน์โหลดและติดตั้ง Arduino IDE

2.เพิ่ม Board ESP8266 ใน Arduino IDE โดยไปที่ File > Preferences แล้วเพิ่ม URL:

http://arduino.esp8266.com/stable/package_esp8266com_index.json

![image](![สกรีนช็อต 2024-12-11 090816](https://github.com/user-attachments/assets/f23871e1-babe-4d1a-b6d1-64e004ab3029)
)

3.ติดตั้งไลบรารีที่จำเป็น เช่น ESP8266WiFi และ ESP8266HTTPClient

image

การเชื่อมต่อ Wi-Fi:

1.ทดสอบการเชื่อมต่อ Wi-Fi โดยใช้โค้ดตัวอย่าง ESP8266 ใน Arduino IDE

การตั้งค่า Twilio API
สมัครใช้งาน Twilio:

1.สร้างบัญชี Twilio และรับ Account SID, Auth Token, และเบอร์โทร Twilio

2.ตั้งค่าหมายเลขโทรศัพท์สำหรับส่ง SMS

ทดสอบการส่ง SMS:

3.ใช้ HTTP POST Request เพื่อส่งข้อความผ่าน Twilio API

การเขียนโปรแกรมและรวมระบบ
การเขียนโค้ดใน Arduino IDE:

1.อ่านค่าควันจากเซ็นเซอร์

2.ตรวจสอบค่าควันว่ามากกว่าค่าที่ตั้งไว้หรือไม่

หากควันเกินเกณฑ์:

1.ส่งข้อความแจ้งเตือนผ่าน Twilio API

2.เปิดพัดลมโดยการสั่งงานโมดูลรีเลย์

การทดสอบการทำงาน:

1.ทดสอบระบบกับสถานการณ์จำลอง เช่น จุดธูปหรือเทียนใกล้เซ็นเซอร์

การปรับปรุงและพัฒนา
ปรับแต่งค่าการตั้งค่า:

1.ปรับเกณฑ์ค่าควันที่ตรวจจับได้ตามความเหมาะสม

2.ทดสอบในสถานที่จริง เช่น ห้องครัวหรือพื้นที่เสี่ยงไฟไหม้

เพิ่มฟีเจอร์:

1.บันทึกข้อมูลควันผ่าน Cloud

2.แสดงผลบน Dashboard หรือแอปพลิเคชัน

การจัดทำเอกสารและนำเสนอ
จัดทำเอกสาร:

1.เขียนรายงานเกี่ยวกับเป้าหมาย ขั้นตอน และผลลัพธ์ของโครงการ

การนำเสนอ:

1.สาธิตการทำงานของระบบ

2.ชี้แจงประโยชน์และการประยุกต์ใช้งานในชีวิตจริง

การบำรุงรักษาและปรับใช้ในสถานที่จริง
1.ติดตั้งระบบในพื้นที่จริง

2.ตรวจสอบการทำงานและอัปเดตเฟิร์มแวร์หรือปรับโค้ดให้เหมาะสม

3.หากต้องการรายละเอียดเพิ่มเติมในขั้นตอนใด แจ้งได้เลยครับ!

**ขั้นตอนการทำงาน ของระบบแจ้งเตือนไฟไหม้ผ่าน SMS โดยใช้ESP866**

เริ่มต้นระบบ
1.เปิดใช้งาน ESP8266 และตรวจสอบการเชื่อมต่อ Wi-Fi

2.ระบบเข้าสู่โหมดรอการตรวจจับ 3. การตรวจจับควัน

1.เซ็นเซอร์ตรวจจับควัน (Gas Sensor) อ่านค่าควันในอากาศผ่านพิน Analog

2.ค่าควันจะถูกแปลงเป็นข้อมูลดิจิทัลด้วย ADC (Analog-to-Digital Converter)

เปรียบเทียบค่าควันกับเกณฑ์ที่กำหนด
หากค่าควัน:

1.น้อยกว่าค่าที่กำหนด: ระบบยังคงทำงานในโหมดตรวจจับ

2.มากกว่าค่าที่กำหนด: ไปยังขั้นตอนถัดไป

การแจ้งเตือนผู้ใช้งาน
1.ESP8266 ส่งข้อความแจ้งเตือนผ่าน Twilio API

ระบุข้อความ เช่น:

"Smoke detected! Please check immediately. Smoke level: [ค่าควันที่อ่านได้]"

3.ข้อความจะถูกส่งไปยังหมายเลขโทรศัพท์ของผู้ใช้งาน

การควบคุมพัดลมดูดอากาศ

1.ESP8266 สั่งงานรีเลย์เพื่อเปิดพัดลมดูดอากาศ

2.พัดลมทำงานเพื่อระบายควันออกจากพื้นที่

การตรวจสอบและประเมินผลใหม่

ระบบกลับไปตรวจสอบค่าควันอีกครั้ง:

หากค่าควันยังคงเกินเกณฑ์:

1.ระบบจะยังคงทำงานในโหมดแจ้งเตือนและระบายอากาศ

หากค่าควันลดลงต่ำกว่าเกณฑ์:

1.พัดลมหยุดทำงาน

2.ระบบเข้าสู่โหมดตรวจจับปกติ

การปิดระบบ
1.หากไม่มีเหตุการณ์เพิ่มเติม ระบบจะทำงานต่อไปในโหมดตรวจจับ

2.หากระบบถูกรีเซ็ตหรือปิดการทำงาน อุปกรณ์ทั้งหมดจะหยุดทำงาน

3.แผนผังลำดับการทำงาน (Flowchart)

4.เริ่มต้น

5.เชื่อมต่อ Wi-Fi

6.อ่านค่าควันจากเซ็นเซอร์

ตรวจสอบค่าควัน:

1.หากค่าปกติ → วนกลับไปอ่านใหม่

2.หากค่าสูง → ส่ง SMS

3.เปิดพัดลมดูดอากาศ

ตรวจสอบค่าควันซ้ำ:

1.หากค่าปกติ → หยุดพัดลม

2.หากยังสูง → ทำซ้ำขั้นตอน 5

3.สิ้นสุด

![image](![5](https://github.com/user-attachments/assets/82a00959-8243-45a8-b433-966b69eed83f)