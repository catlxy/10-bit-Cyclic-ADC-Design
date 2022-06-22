# 10-bit-Cyclic-ADC-Design
The team project of course "Integrated Circuit Design" 

## 组员

* 李心阅，集成电路学院，清华大学
* 李贺悦，集成电路学院，清华大学

## 电路级设计
主要模块：
- **CLK generator**
  - 输入：`clk`
  - 输出：`f1,f2,k1,k2,s1,s2,nf1,nf2,nk1,nk2,ns1,ns2`
  - 功能：产生控制时序信号
- **subADC**
  - 输入：`s1,s2,k1,k2,vip,vin,vop1,von1,vop2,von2,vh,vl`
  - 输出：`x1,y1,z1,nx1,ny1,nz1,dm1,dl1,x2,y2,z2,nx2,ny2,nz2,dm2,dl2`
  - 功能：将输入信号Vi与Vref（0.25Vf和-0.25Vf）做比较，输出00、01、10三者之一
- **Backend ADC**
  - 输入：`vop2,von2,ns1,vcm,vl2,vh2`
  - 输出：`pq0,pq1`
- MDAC
  - 


- MOS CAP
- 同步输出电路
