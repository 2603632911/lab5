# lab5
第五次实验
##实验目的  
掌握字符串String及其方法的使用  
掌握文件的读取/写入方法  
掌握异常结构的处理  
##实验过程
创建一个学生类，下面有整型的年龄，字符串的姓名，整型的学号，字符串的性别  
创建一个gushi类，创建一个字符串输入流，读取在d盘的gushi.txt文件，再把它存到缓冲区，最后将他写入d盘的A.txt文件里
根据古诗要求，每七个字加一个逗号，十四个字加一个句号并且下一行，所以在第七个位置之后加一个逗号，第十五个字后面加一个句号，并且插入\n来换行  
##核心方法

public void setGraduate(String name, String sex,int age,int number) {  
        this.sex = sex;  
        this.age = age;  
        this.name = name;  
        this.number = number;  
    }    //创建学生的四个对象  
    
     
Student xuesheng = new Student();  
     System.out.println("输入姓名，性别，年龄，学号");  //输出学生对象
         
     
     FileReader fileReader = new FileReader("D:\\gushi.txt");//读取D盘文件
            BufferedReader bufferedReader = new BufferedReader(fileReader);//把文件存到缓冲区
            Writer writer = new FileWriter(new File("D:\\A.txt"));//将缓冲区文件写入A文件中
     
    String str = bufferedReader.readLine();
            String regex = "(.{7})";
            str = str.replaceAll(regex, "$1，");
            StringBuffer x = new StringBuffer(str);
            for (int  i = 15; i <289; i = i + 17) {
                x.replace(i, i + 1, "。\n");
            }//判断逗号和句号的位置，并且换行
##实验结果
