# 10-bit-Cyclic-ADC-Design
The team project of course "Integrated Circuit Design" 

## 组员

* 李心阅，集成电路学院，清华大学
* 李贺悦，集成电路学院，清华大学

## 电路级设计
主要模块：
- **CLK generator**
  - 输入：`clk`
  - 输出：`f1,f2,k1,k2,s1,s2,nf1,nf2,ns1`
  - 功能：产生控制时序信号
- **MOS CAP**
  - 输入：`vrp,vrn`
  - 输出：`vl,vh,vl2,vh2`
  - 功能：分压电路，将参考电压Vref分成四份
- **subADC**
  - 输入：`s1,s2,k1,k2,vip,vin,vop1,von1,vop2,von2,vh,vl`
  - 输出：`x1,y1,z1,nx1,ny1,nz1,dm1,dl1,x2,y2,z2,nx2,ny2,nz2,dm2,dl2`
  - 功能：将输入信号Vi与参考电压Vref（0.25Vf和-0.25Vf）做比较，输出00、01、10三者之一
- **Backend ADC**
  - 输入：`vrop,vron,ns1,vcm,vl2,vh2`
  - 输出：`pq0,pq1`
  - 功能：将余量Vres加到初步粗略A/D转换的信号上，得到最终的数字信号
- **MDAC**
  - 输入：`f1,nf1,nf2,f2,k1,k2,s1,s2,x1,x2,y1,y1,z1,z2,vip,vin,vcm,vrp,vrn,lb1,lb2`
  - 输出：`vop1,von1,vop2,von2`
  - 功能：完成采样、D/A、模拟减法（Vin-VDAC=Vres）和放大，并循环
- **同步输出电路**
  - 
