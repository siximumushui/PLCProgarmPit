# PLCProgarmPit
Step on the hole
1、在使用FB或者FC功能块时，FB块有可保持型的数据，FC块没有，下一个扫描周期对应的变量会重置，可保持性数据下周期不会重置  
  注意：在变量定义设置的【保持】是指在断电后保不保持数据，而不是在下一个周期保不保持  
2、TEMP数值无法像M点或Q点一样保持上一个周期的数值；TEMP需要在每个扫描周期有一个明确的赋值，即先赋值（写），再使用（读写）  
  解决方式，FB可使用STAT静态变量；FC可使用M区或全局DB地址。  
3、FB块和FC块使用--|P|--：扫描操作数的信号上升沿 时，信号状态存储的边沿存储器位不能使用M点，否则可能会出现上面的操作数值修改了  
  但是下面的操作数无法保存上一个扫描周期的值  
4、在使用IW，MW、QW之类的多点位变量时，要注意不要使用对应的变量点，例如IW10，会用到  

