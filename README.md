
# 一、实验目的
  1.分析学生选课系统
  2.使用GUI窗体及其组件设计窗体界面
  3.完成学生选课过程业务逻辑编程
  4.基于文件保存并读取数据
  5.处理异常
# 二、实验要求
  ## 1.系统角色分析及类设计
  例如：学校有“人员”，分为“教师”和“学生”，教师教授“课程”，学生选择课程。定义每种角色人员的属性，及其操作方法。
属性示例：人员（编号、姓名、性别……）
         教师（编号、姓名、性别、所授课程、……）
			   学生（编号、姓名、性别、所选课程、……）
			   课程（编号、课程名称、上课地点、时间、授课教师、……）
以上属性仅为示例，同学们可以自行扩展。
  2.要求
  （1）设计GUI窗体，支持学生注册、课程新加、学生选课、学生退课、打印学生选课列表等操作。
  （2）基于事件模型对业务逻辑编程，实现在界面上支持上述操作。
  （3）针对操作过程中可能会出现的各种异常，做异常处理
  （4）基于输入/输出编程，支持学生、课程、教师等数据的读写操作。
  （5）基于Github.com提交实验，包括实验SRC源文件夹程序、README.MD实验报告文档。
三、实验思路
   1、建一个包xueshengxuanke，建立新的类Gui。然后调用We、Student和People的类对Gui编辑。
   2、使用各种窗口组件，建立可行的Gui窗口。建立各个不同的组件，对组件赋值。
   3、把组件装到容器里，在文本框中输出内容。
   4、新建一个课程文件来储存课程的信息，用户选择课程，然后再从文件中提取正确的内容，写到新建的另一个文件中。
   5、开课操作是将将用户所输入的信息储存到文件中。
四、流程图
![text](https://github.com/Echo334/Java.program/blob/master/Java%E5%AE%9E%E9%AA%8C5%E6%B5%81%E7%A8%8B%E5%9B%BE.png);
五、核心代码注释
JLabel label1;JLabel label2;JLabel label3;JLabel label4,label5;JLabel label6;
               	JLabel label7;JLabel label8;JLabel label9;JLabel label10,label11;JLabel label12;JLabel label13;//定义标签
               	JButton button1,button2;//定义按钮
               	TextArea ta1;//定义文本框 
               	JTextField t1,t2,t3,t4,t5,t6,t7,t8;//定义输入文本框 
               	CheckboxGroup cbg;
               	               	JCheckBox c1,c2,c3;               	
               	String bianhao[]={"004","005","006","007","008","009"};//设置编号
               	String score[]={"0.5","1.0","1.5","2.0","2.5","3.0",//设置学分
               			"3.5","4.0"};
               	public Gui(){
               		super("选课系统");
                  label1=new JLabel("请输入个人信息和所选课程，完成后单击确定。            ");label7=new JLabel("请输入开设的课程和信息，完成后单击确定。        ");label2=new JLabel("学生姓名：");               		label3=new JLabel("性别:");
               		cbg = new CheckboxGroup();              		label6=new JLabel("学号：");label4=new JLabel("生日：");label5=new JLabel("课程：");label11=new JLabel("上课地点：");               		                            		               
                  c1=new JCheckBox("语文");c2=new JCheckBox("数学");        c3=new JCheckBox("英语");
               		ta1=new TextArea(10,30);               		
               		button1=new JButton("确定");              		button2=new JButton("取消");              		
               		t1=new JTextField("",5);              		t2=new JTextField("",10);             		t3=new JTextField("",5);              		t4=new JTextField("",5);             		t5=new JTextField("",5);              		t6=new JTextField("",5);               		t7=new JTextField("",5);              		t8=new JTextField("",5);//定义组件
                  setBounds(600,300,625,600);//定义界面大小
               		try {UIManager.setLookAndFeel(UIManager.getSystemLookAndFeelClassName());
               		}catch(Exception e){}//设计监听器
               		c=getContentPane();	
               		c.setLayout(new FlowLayout(FlowLayout.LEFT));               		c.add(label1);               	              		c.add(label2);             		c.add(t1);
               		c.add(label3);               		             		c.add(new Checkbox("男", cbg, true));                		c.add(ne
