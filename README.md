# moonlight-thai-installation

# เดี๋ยวมาลงรูปให้ทีหลัง หรือถ้าใครอยากแก้ไข Pull requests เข้ามาได้เลยครับ

### คู่มือสำหรับ webOS หากเป็นค่ายอื่น ใช้ Steamlink หรือ ลง moonlight ได้โดยตรงที่นี่ [moonlight-stream](https://moonlight-stream.org/) Tab client download

### หมายเหตุ
 - ใช้ Geforce Experience เป็น host ในการ Steam (ไม่รู้ การ์ดจอ AMD ลงได้ไหม)
 - ***ห้ามปิด PC แต่ปิดจอได้***
 - ***controller ต้องต่อกับ PC***
 
 - จัดทำเพื่อสมาชิกกลุ่ม [นักเลงทีวี “Oled Qled Led TV Thailand Community“](https://www.facebook.com/groups/747168688821081) และใช้งานส่วนตัว ไม่ใช้ในเชิงพาณิชย์
 - ผู้จัดทำไม่ได้มีส่วนได้ส่วนเสียกับ [mariotaku/moonlight-tv](https://github.com/mariotaku/moonlight-tv), [webosbrew/dev-manager-desktop](https://github.com/webosbrew/dev-manager-desktop), [moonlight-stream](https://moonlight-stream.org/)
 - ห้ามคัดลอก แก้ไข หรือทำซ้ำ
 - ไม่สามารถแก้ไขปัญหารายบุคคลได้ และไม่รู้ข้อจำกัดของระบบ ว่ารองรับเครื่องไหน หรือไม่รองรับเครื่องไหนบ้าง
 - โปรแกรมที่ใช้เป็น community version คือ กลุ่มคนช่วยกันทำขึ้นมา เป็น opensource ไม่มีค่าใช้จ่าย อันนี้ผู้ใช้ต้องยอมรับความเสี่ยงของ opensource ให้ได้ก่อน คือ จะไม่มีพนักงานมาแก้ไขปัญหาให้ และโปรแกรมอาจจะมีบัคบ้าง หากเป็นกังวลเรื่องความปลอดภัย สามารถตรวจสอบ sourcecode ได้ที link ข้างต้น


## specification ที่ผมใช้ในคู่มือนี้

### PC
 - CPU Intel i7-8700
 - VGA 3070Ti
 - RAM 32GB DDR4 Bus 3600
 - NETWORK LAN
 - fixed local IP


### TV
 - LG OLED 4K Smart TV 55 นิ้ว รุ่น OLED55C1
 - NETWORK Wifi 5G
 - fixed local IP
 
** TV กับ PC อยู่ใน Network เดียวกัน
 
## อ้างอิง
 - [mariotaku/moonlight-tv](https://github.com/mariotaku/moonlight-tv)
 - [webosbrew/dev-manager-desktop](https://github.com/webosbrew/dev-manager-desktop)
 - [moonlight-stream](https://moonlight-stream.org/)
 - [LG's official documentation](http://webostv.developer.lge.com/develop/app-test)
 - [วิธีตั้งค่า IP Address ใน Windows 10 fix ip address](https://www.youtube.com/watch?v=j2YjWZ3WAOk)

### สิ่งที่ต้องเตรียม
 1. หา IP ของ PC
 
    1.1 พิม `cmd` ในช่องค้นหาใน PC แล้ว enter
    
    1.2 พิม `ipconfig` กด enter
    
    1.3 หา network connection ที่ใช้อยู่ ปกติจะเป็น 192.168.1.x หรือ 192.168.2.x
    
    1.4 จด IP ของ PC ไว้
 
 2. นำ Account LG ของเรา ไปสมัครเป็น Developer [อ่านแบบละเอียด](https://webostv.developer.lge.com/develop/app-test/preparing-account/)
    
    2.1 [https://webostv.developer.lge.com/login](https://webostv.developer.lge.com/login) login เว็บนี้
    
    2.2 ไปที่แถบ CREATE ACCOUNT และกดยืนยันไปเรื่อยๆ จนเสร็จ

 3. ติดตั้ง [Geforce Experience](https://www.nvidia.com/en-us/geforce/geforce-experience/) 

# Step by step

### ล๊อค IP บน PC (ทำหรือไม่ทำก็ได้)

 1. อันนี้หาได้ทั่วไป แต่ถ้าไม่อยากหา -> [Youtube](https://www.youtube.com/watch?v=j2YjWZ3WAOk)

### ล๊อค IP บน LG TV (ทำหรือไม่ทำก็ได้)

 1. Setting -> Network -> กดที่ชื่อ wifi (กรณีนี้ผมใช้ Wifi คนใช้ LAN ก็น่าจะหน้าตาคล้ายๆกัน)
 
 2. กดไปหน้า Other Network
 
 3. กด Advance Wi-Fi Setting
 
 4. เลื่อนลงมาล่างสุดกด Edit
 
 5. เอาติ๊ก Set Automatically ออก
 
 6. แก้ IP address เป็นอะไรก็ได้ ที่ว่างใน Network NetworkID + ตั้ง host id เอง (กรณีผมคือ 192.168.1.59 ซึ่ง 192.168.1 คือ network id ส่วน 59 คือ host id) (ถ้าอยากแก้ DNS ตามผมด้วยก็ได้ เป็น 1.1.1.1)
 
 7. เลื่อนมาล่างสุด กด Connect
 
 8. เช็คว่ากลมๆ สีเขียวด้านบน มัน connect ได้ไหม
 
 9. เสร็จสิ้น

## มาเริ่มกันเลย

### ติดตั้ง Dev app บน LG TV

[เพิ่มเติม](https://webostv.developer.lge.com/develop/app-test/using-devmode-app/)

 1. login ด้วย LG account ที่สมัครเป็น developer ข้างต้น
 
 2. ค้นหา app ที่ชื่อ Developer Mode
 
 3. ติดตั้งแล้ว เปิด app

 4. login ด้วย email และ password ของ lg account
 
 5. เปิด Dev Mode Status เป็น on และ restart tv
 
 4. เปิด Key server เป็น on
 
 5. เปิดหน้าจอของ app นี้ทิ้งไว้แล้วไปหัวข้อถัดไป

### ติดตั้ง dev manager บน PC
 
 1. Download เวอร์ชั่นล่าสุด [Easy tool to manage developer mode](https://github.com/webosbrew/dev-manager-desktop/releases) หรือ [คลิ๊กที่นี่](https://github.com/webosbrew/dev-manager-desktop/releases/download/v1.8.2/webos-dev-manager.1.8.2.exe)
 
 2. เปิดโปรแกรม ไม่จำเป็นต้องติดตั้ง หากเปิดครั้งแรกแล้วมีหน้าต่าง แจ้งเตือนความปลอดภัยของ windows ให้กด more info และกด Run anyway
 
 3. เปิดโปรแกรมมา กด Add device
 
 4. กรอก host address และ Passphrase ที่แสดงบนจอ TV และกดปุ่ม add (หากปุ่ม add กดไม่ได้ ให้ปิดเปิดแอพใหม่ ทั้ง tv และในคอม ทำซ้ำ จนกว่าจะได้ และเช็คให้แน่ใจว่า Key server บนทีวีได้เปิดแล้ว)
 
 5. มาที่หัวข้อ App แล้ว ไปที่ Tap Available แล้วหา app ชื่อ Moonlight แล้วกด Install

 6. จะเห็น app Moonlight ขึ้นมาบน TV เป็นอันเสร็จสิ้น

### เชื่อมต่อ Moonlight เข้า Geforce experience
 
 1. เปิด Geforce experience กด setting (รูปเฟืองขวาบน)
 
 2. ไปที่ Tap SHIELD
 
 3. เปิด GAMESTREAM
 
 4. เปิด App Moonlight บน TV

 5. กด Add computer

 6. พิม IP ของ เครื่อง PC แล้วกด OK

 7. ชื่อ PC จะเด้ง ขึ้นมา

 8. ไปที่ Setting แล้วเลือก Tab Basic setting ตั้งค่า resolution กับ FPS ตามต้องการ (ขึ้นอยู่กับ TV และ ความแรง PC)

 9. เสร็จสิ้นเล่นเกมได้
