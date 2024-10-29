# แนวทางการทำงาน LEDC Fade Example

ตัวอย่างนี้ใช้สำหรับการทำให้ LED ค่อยๆ เปลี่ยนแสงสว่างโดยการปรับค่าความสว่างขึ้นหรือลงตามช่วงเวลาที่กำหนด

## การเลือก Example IDF

![สกรีนช็อต 2024-10-29 214957](https://github.com/user-attachments/assets/31a851f3-17ed-4f9b-91cb-baf9f5fd0aa7)

1. เลือก ESP-IDF

2. เลือก show example

3. พิมพ์คำว่า led

4. เลือก ledc_fade

![สกรีนช็อต 2024-10-29 211804](https://github.com/user-attachments/assets/32a50e46-6185-44af-8a88-2fd5fd8fecd7)


5. คลิกเลือก Create project using example ledc_fade

6. เมื่อสร้างแล้วจะได้ไฟล์ทั้งหมดดังนี้

![สกรีนช็อต 2024-10-29 211927](https://github.com/user-attachments/assets/77e50b5a-2af0-4b55-993e-b35e035986e2)

## การต่อ GPIO กับ LED 

7. เลือกไฟล์ main.c

![สกรีนช็อต 2024-10-29 211947](https://github.com/user-attachments/assets/d13d5874-df14-4a58-9ab4-56cd282eaab2)

ในโค้ดมีการกำหนดการต่อ GPIO ดังนี้

|      LED           | LED 1 | LED 2 | LED 3 | LED 4 |
| --------------- | --------- | --------- | --------- | --------- |
|     ESP32       | GPIO18    | GPIO19    | GPIO4     | GPIO5     |

## Build and Flash

8. เลือก com port

9. เลือก Build Flash and Monitor

## ผลลัพท์

- Serial Moniter แสดง สถานะของ LED

  ![สกรีนช็อต 2024-10-29 211707](https://github.com/user-attachments/assets/1f30bc3e-1344-481e-8d92-6ad13d74597d)


- บนบอร์ด LED 1,2 และ LED 3,4 จะสว่างไม่เท่ากันเพราะถูกตั้งโหมดไว้แตกต่างกัน GPIO 18 และ 19 ถูกตั้งไว้ในโหมดความเร็วสูงและ GPIO 4 กับ 5 ถูกตั้งไว้ในโหมดความเร็วต่ำ

https://drive.google.com/file/d/1txO2RQeSJWQMXq-W__M3T4LyzFJNtie8/view?usp=drive_link


## การแก้ไข
- สามารถปรับระดับความสว่างของ LED ที่ต้องการได้โดยสามารถกำหนดลงในบรรทัดที่ 63
  
```
#define LEDC_TEST_FADE_TIME    (3000)
```

![สกรีนช็อต 2024-10-29 211947](https://github.com/user-attachments/assets/a4c7c528-e8af-4f8f-ba91-356b06e6d5e8)

