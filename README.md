# java-Experiment-4
## 2020322081    白少伟
## 1. 实验内容
+ 1.通过无序号的古诗词，通过使用文件的输入流和输出流通过java中所学的方法
    来进行对每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
+ 2.允许提供输入参数，统计古诗中某个字或词出现的次数
+ 3.输入的文本来源于文本文件B读取，把处理好的结果写入到文本文件A
+ 4.考虑操作中可能出现的异常，在程序中设计异常处理程序

## 2. 实验设计

+ 1.设置Student类，通过交互式的形式输出
```
  public void toshow() {
		
		String name;							//关于学生的姓名
		int code;							//关于学生的编号
		String sexy;							//关于学生的性别
		int age;							//关于学生的年龄
		String grade;							//关于学生的班级
		String major;							//关于学生的专业
		
		Student stu=new Student();
		Scanner sc= new Scanner(System.in);
		System.out.println("姓名：");
	    name=sc.next();
		System.out.println("编号：");
	    code=sc.nextInt();
		System.out.println("性别：");
	    sexy=sc.next();
		System.out.println("年龄");
	    age=sc.nextInt();
		System.out.println("班级：");
	    grade=sc.next();
		System.out.println("专业：");
	    major=sc.next();
	    System.out.println("姓名："+name+"编号："+code+"性别："+sexy+"年龄："+age+"班级："+grade+"专业："+major);
		
	}
```
 ## 3. 核心方法
 
 1. 创建Test类通过while循环和数组的使用，可以让古诗有序从文本中输出，并且捕获异常。
  
  ```
      try (FileReader fInputStream = new FileReader("D:\\homework\\outport.txt");//读文件
			FileWriter fOutputStream  = new FileWriter("D:\\homework\\import.txt")){//重新写入文件
		   StringBuffer st=new StringBuffer();
		   char[] ch=new char[14];//设置有14个字符
		  while ((fInputStream.read(ch)) !=-1) {
		    st.append(ch, 0,7);
		    st.append("，");
		    st.append(ch, 7, 7);
		    st.append("。"+"\n");
		  }
		  System.out.println(st);
	      fOutputStream.write(new String(st));
		}catch (IOException e) {
			e.printStackTrace();
		}
		
  
  ```
  2. 通过mains类进行调用输出
  
  ```
    Student stu=new Student();
		stu.toshow();
		Test test = new Test();
		Test.txt();
```
   
  ## 4.实验截图
   
   https://github.com/baishaowei-eng/homework/tree/main/jietu
   
  ## 5.实验感想

  1. 通过这个实验中学习到了如何乱序的排版通过循环判断语句进行对古诗句的有序排版。
  2. 学会了如何获取文件中的字节流，然后在另一个文本中能够输出。
  3. 学会了人机交互式的方法来获取自己想要的内容
  4. 学会了如何通过逻辑循环语句截取字符的个数，更好的掌握了Java中所学的不足。
