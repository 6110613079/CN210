## รายงาน
## วิชา Computer Architecture สถาปัตยกรรมคอมพิวเตอร์
### สรุปเนื้อหา
<br>**MIPS Instruction format**

ทุกคำสั่งใน MIPS จะมีขนาด 32 bits

มี 3 ประเภท

<br>**R-Format** (ส่วนใหญ่ใช้ในการคำนวณทางตรรกศาสตร์)

|op  | rs  |  rt | rd  | shamt  | func  |
----- | ----- | ----- | ----- | ----- | ----- |

|คำสั่ง |    |
----- | ----- |
|ALU  |   alu    $rd,$rs,$rt|
|jr   |   jr     $rs|

<br>**I-Format** (ใช้ย้ายข้อมูลเปลี่ยนข้อมูล)

|op  | rs  |  rt | value or offset |
----- | ----- | ----- | ----- | 

|คำสั่ง |    |
----- | ----- |
|ALUi      |  alui  $rt,$rs,value |
|Data  Transfer    |  lw    $rt,offset($rs) |
|                  |  sw    $rt,offset($rs) |
|Branch            |  beq   $rs,$rt,offset |

<br>**J-Format** (Jumpไปทำงานที่อื่น)

|op  | absolute address |
----- | ----- | 

|คำสั่ง |    |
----- | ----- |
|Jump      |  j   address|
|Jump&Link  | jal   address|

<br>**การบ้านครั้งที่ 1**

### คำสั่ง ADD ในคอมพิวเตอร์ MIPS

ซึ่งเป็นคำสั่ง ประเภท R-Format 

หลักการทำงาน คือ $rd <- $rs + $rt (ภาษาที่มนุษย์เข้าใจ)

ตัวอย่าง

|register   | registerตัวที่   | binary |
----- | -----  | ----- |
| rs |    $3   |  00011  |
| rt |    $2   |  00010  |
| rd |    $8   |  01000  |

ทำการเขียนเป็นภาษาที่คอมพิวเตอร์เข้าใจ

|op  | rs  |  rt | rd  | shamt  | func  |
----- | ----- | ----- | ----- | ----- | ----- |
| 000000 | 00011 | 00010 | 00100 | 00000 | 100000 |

ฐาน 2 > 00000000011000100010000000100000

ฐาน 16 > 00624020

ดังนั้น คำสั่งที่ส่งให้คอมพิวเตอร์ทำการบวก $rs $rt และนำผลลัพธ์ไปเขียนที่ $rd คือ 00624020

<br>**ALU decoder**

![image](https://i.stack.imgur.com/QwYfS.gif)

เนื่องจากคำสั่งนี้เป็นประเภท R-Format จึงมีการเขียนคำสั่งเป็น 6 ส่วน
เมื่อคอมพิวเตอร์ได้รับคำสั่งนี้ ตัว decoder ที่อยู่ในคอมพิวเตอร์จะทำการแปลเป็นคำสั่ง(ดูได้จาก ตาราง ALU decoder)

6 bits แรกคือ opcode ถ้า opcode เป็น 000000 แสดงว่าเป็นประเภท R-Format

5 bits  ถัดมาคือ register rs => registerตัวที่ 3

5 bits  ถัดมาคือ register rt => registerตัวที่ 2

5 bits  ถัดมาคือ register rd => registerตัวที่ 8

5 bits  ถัดมาคือ shamt คือ shift amount ในคำสั่งนี้ไม่ได้ใช้จึงเป็น 00000

6 bits สุดท้าย คือ func เป็นตัวบอกว่าใช้คำสั่งอะไร ในที่นี้เป็น 100000 ซึ่งเป็นคำสั่ง ADD สั่งให้บวก

คอมพิวเตอร์จะทำการนำ registerตัวที่ 3 บวกกับ registerตัวที่ 2 และนำค่าที่ได้ไปเก็บที่ registerตัวที่ 8

<br>**ส่งการบ้านครั้งที่ 1**

[CLIP1](https://youtu.be/IyKyMtiQF5Q)

<br>**การบ้านครั้งที่ 2**

### อธิบายการทำงานของ CPU 

ตัวอย่าง

<br>**คำสั่งที่มนุษย์เข้าใจ**

=== JAVA Language ===

class Test{
    public static void main(String[] args){
        int a = 10;
        int b = 20;
        int c = a+b;
    }
}

=== Machine Language ===
00000000:           08400000        //j  01000000


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






