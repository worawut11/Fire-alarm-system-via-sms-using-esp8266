# Fire-alarm-system-via-sms-using-esp8266
ระบบแจ้งเตือนไฟไหม้ผ่าน sms โดยใช้ esp8266
#ขั้นตอนการทำงานงานของระบบแจ้งเตือนไฟไหม็ผ่าน SMS โดยใช้ ESP8266
1. การวางแผนโครงการ
กำหนดเป้าหมาย:
1.พัฒนาระบบที่สามารถตรวจจับควัน แจ้งเตือนผ่าน SMS และควบคุมพัดลมดูดอากาศอัตโนมัติ
การเตรียมอุปกรณ์:
  1.ไมโครคอนโทรลเลอร์ ESP8266 (NodeMCU)
  2.Gas Sensor (เช่น MQ-2 หรือ MQ-135)
  3.โมดูลรีเลย์
  4.พัดลมดูดอากาศ
  5.สายไฟและ Breadboard
  6.แหล่งจ่ายไฟ
วางแผนซอฟต์แวร์:
  1.ใช้ Twilio API สำหรับส่งข้อความ SMS
  2.เขียนโค้ดด้วย Arduino IDE
3. การเตรียมอุปกรณ์ฮาร์ดแวร์
ประกอบวงจร:
  1.เชื่อมต่อ Gas Sensor กับพิน A0 ของ ESP8266
  2.เชื่อมต่อโมดูลรีเลย์กับพินดิจิทัล (เช่น D1) เพื่อควบคุมพัดลม
  3.ตรวจสอบแรงดันไฟฟ้าของอุปกรณ์ (ใช้ 5V หรือ 3.3V ตามอุปกรณ์ที่เลือก)
ตรวจสอบการทำงานของเซ็นเซอร์:
  4.อ่านค่าที่เซ็นเซอร์ส่งออกมาโดยใช้คำสั่ง analogRead() เพื่อวัดระดับควัน
3. การตั้งค่าและทดสอบ ESP8266
การติดตั้ง Arduino IDE และไลบรารี:
  1.ดาวน์โหลดและติดตั้ง Arduino IDE
  2.เพิ่ม Board ESP8266 ใน Arduino IDE โดยไปที่ File > Preferences แล้วเพิ่ม URL:
**http://arduino.esp8266.com/stable/package_esp8266com_index.json**
  3.ติดตั้งไลบรารีที่จำเป็น เช่น ESP8266WiFi และ ESP8266HTTPClient
   ![image](file:///C:/Users/junio/Pictures/Screenshots/%E0%B8%AA%E0%B8%81%E0%B8%A3%E0%B8%B5%E0%B8%99%E0%B8%8A%E0%B9%87%E0%B8%AD%E0%B8%95%202024-12-11%20090816.png)
การเชื่อมต่อ Wi-Fi:
  1.ทดสอบการเชื่อมต่อ Wi-Fi โดยใช้โค้ดตัวอย่าง ESP8266 ใน Arduino IDE
5. การตั้งค่า Twilio API
 สมัครใช้งาน Twilio:
  1.สร้างบัญชี Twilio และรับ Account SID, Auth Token, และเบอร์โทร Twilio
  2.ตั้งค่าหมายเลขโทรศัพท์สำหรับส่ง SMS
   ทดสอบการส่ง SMS:
  3.ใช้ HTTP POST Request เพื่อส่งข้อความผ่าน Twilio API
6. การเขียนโปรแกรมและรวมระบบ
 การเขียนโค้ดใน Arduino IDE:
  1.อ่านค่าควันจากเซ็นเซอร์
  2.ตรวจสอบค่าควันว่ามากกว่าค่าที่ตั้งไว้หรือไม่
 หากควันเกินเกณฑ์:
  1.ส่งข้อความแจ้งเตือนผ่าน Twilio API
  2.เปิดพัดลมโดยการสั่งงานโมดูลรีเลย์
การทดสอบการทำงาน:
  1.ทดสอบระบบกับสถานการณ์จำลอง เช่น จุดธูปหรือเทียนใกล้เซ็นเซอร์
7. การปรับปรุงและพัฒนา
 ปรับแต่งค่าการตั้งค่า:
  1.ปรับเกณฑ์ค่าควันที่ตรวจจับได้ตามความเหมาะสม
  2.ทดสอบในสถานที่จริง เช่น ห้องครัวหรือพื้นที่เสี่ยงไฟไหม้
เพิ่มฟีเจอร์:
  1.บันทึกข้อมูลควันผ่าน Cloud
  2.แสดงผลบน Dashboard หรือแอปพลิเคชัน
8. การจัดทำเอกสารและนำเสนอ
 จัดทำเอกสาร:
  1.เขียนรายงานเกี่ยวกับเป้าหมาย ขั้นตอน และผลลัพธ์ของโครงการ
การนำเสนอ:
  1.สาธิตการทำงานของระบบ
  2.ชี้แจงประโยชน์และการประยุกต์ใช้งานในชีวิตจริง
9. การบำรุงรักษาและปรับใช้ในสถานที่จริง
  1.ติดตั้งระบบในพื้นที่จริง
  2.ตรวจสอบการทำงานและอัปเดตเฟิร์มแวร์หรือปรับโค้ดให้เหมาะสม
  3.หากต้องการรายละเอียดเพิ่มเติมในขั้นตอนใด แจ้งได้เลยครับ!






