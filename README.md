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
  - 输入：`s1,s2,nk1,`
  - 输出：`x1,y1,z1,dm1.dl1`
- MDAC
  - 

- Backend ADC
- MOS CAP
- 同步输出电路
