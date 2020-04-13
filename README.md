# รายงาน
# วิชา Computer Architecture สถาปัตยกรรมคอมพิวเตอร์
## สรุปเนื้อหา
<br>**MIPS Instruction format**

ทุกคำสั่งใน MIPS จะมีขนาด 32 bits

มี 3 ประเภท

<br>**R-Format** (ส่วนใหญ่ใช้ในการคำนวณทางตรรกศาสตร์)

|op  | rs  |  rt | rd  | shamt  | func  |
----- | ----- | ----- | ----- | ----- | ----- |

|ALU  |   alu    $rd,$rs,$rt|
|jr   |   jr     $rs|

<br>**I-Format** (ใช้ย้ายข้อมูลเปลี่ยนข้อมูล)

|op  | rs  |  rt | value or offset |
----- | ----- | ----- | ----- | 

|ALUi      |  alui  $rt,$rs,value |
|Data  Transfer    |  lw    $rt,offset($rs) |
|                  |  sw    $rt,offset($rs) |
|Branch            |  beq   $rs,$rt,offset |

<br>**J-Format** (Jumpไปทำงานที่อื่น)

|op  | absolute address |
----- | ----- | 

|Jump      |  j   address|
|Jump&Link  | jal   address|

<br>**การบ้านครั้งที่ 1**

คำสั่ง ADD ในคอมพิวเตอร์ MIPS

ซึ่งเป็นคำสั่ง ประเภท R-Format 

หลักการทำงาน คือ $rd = $rs + $rt

ตัวอย่าง

|     | registerตัวที่   | binary |
----- | ----- | ----- |
| rs | $3 | 00011 |
| rt | $2 | 00010 |
| rd | $8 | 01000 |

|op  | rs  |  rt | rd  | shamt  | func  |
----- | ----- | ----- | ----- | ----- | ----- |
| 000000 | 00011 | 00010 | 00100 | 00000 | 100000 |

คำสั่งที่ส่งให้คอมพิวเตอร์ทำการบวก $rs $rt และนำผลลัพธ์ไปเขียนที่ $rd คือ

ฐาน 2 > 00000000011000100010000000100000

ฐาน 16 > 00624020

ส่งการบ้านครั้งที่ 1
[CLIP1](https://youtu.be/IyKyMtiQF5Q)

ส่งการบ้านครั้งที่ 2
[CLIP2](https://youtu.be/AhHoyF2xnng)

ส่งการบ้านครั้งที่ 3
[CLIP3](https://youtu.be/nflcyI8XoiA)

ส่งการบ้านครั้งที่ 4
[CLIP4](https://youtu.be/bEka1oMBni0)

ส่งการบ้านครั้งที่ 5
[CLIP5](https://youtu.be/tH1uvTTxsqw)

ส่งการบ้านครั้งที่ 6
[CLIP6](https://youtu.be/73PG4tqJF4I)

ส่งการบ้านครั้งที่ 7
[CLIP7]

ส่งการบ้านครั้งที่ 8
[CLIP8]






