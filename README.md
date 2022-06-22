# 10-bit-Cyclic-ADC-Design
The team project of course "Integrated Circuit Design" 

## 组员

* 李心阅，集成电路学院，清华大学
* 李贺悦，集成电路学院，清华大学

## 电路级设计
- **CLK generator**
  - 输入：`clk`
  - 输出：`f1,f2,k1,k2,s1,s2,nf1,nf2,ns1`
  - 功能：产生控制时序信号
- **MOS CAP**
  - 输入：`vrp,vrn`
  - 输出：`vl,vh,vl2,vh2`
  - 功能：分压电路，将参考电压Vref从-Vref到+Vref分成8份，-vl2=vh2=0.5Vf，-vl=vh=0.25Vf
- **MDAC**
  - 输入：`f1,nf1,nf2,f2,k1,k2,s1,s2,x1,x2,y1,y1,z1,z2,vip,vin,vcm,vrp,vrn,Ib1,Ib2`
  - 输出：`vop1,von1,vop2,von2`
  - 功能：完成采样、D/A、模拟减法（Vin-VDAC=Vres）和放大，并循环
- **subADC**
  - 输入：`s1,s2,k1,k2,vip,vin,vop1,von1,vop2,von2,vh,vl`
  - 输出：`x1,y1,z1,nx1,ny1,nz1,dm1,dl1,x2,y2,z2,nx2,ny2,nz2,dm2,dl2`
  - 功能：将输入信号Vi与参考电压Vref（0.25Vf和-0.25Vf）做比较，输出00、01、10三者之一
- **Backend ADC**
  - 输入：`vop2,von2,ns1,vcm,vl2,vh2`
  - 输出：`pq0,pq1`
  - 功能：将余量Vres加到初步粗略A/D转换的信号上，得到最终的数字信号
- **输出同步电路**
  - 输入：`s1,s2,clk,dm1,dm2,dl1,dl2,pq0,pq1`
  - 输出：`m1~m8,l1~l8,Lq0,Lq1`
  - 功能：
- **输出校正电路**
  - 输入：`m1~m8,l1~l8,Lq0,Lq1`
  - 输出：`dlast1~dlast10`
  - 将输入错位相加，得到最终10-bit的输出

主要难点：**MDAC中的OTA设计**
- 输入：`ip,in,Ib,vcm,nf`
- 输出：`op,on`
- 设计：
