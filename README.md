一、实验目的
掌握字符串String及其方法的使用
掌握文件的读取/写入方法
掌握异常处理结构
二、实验内容
在某课上,学生要提交实验结果，该结果存储在一个文本文件A中。
文件A包括两部分内容：
一是学生的基本信息；
二是学生处理后的作业信息，该作业的业务逻辑内容是：利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能方法，实现如下功能：
1.每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
2.允许提供输入参数，统计古诗中某个字或词出现的次数
3.输入的文本来源于文本文件B读取，把处理好的结果写入到文本文件A
4.考虑操作中可能出现的异常，在程序中设计异常处理程序
三、实验要求
设计学生类（可利用之前的）；
采用交互式方式实例化某学生；
设计程序完成上述的业务逻辑处理，并且把“古诗处理后的输出”结果存储到学生基本信息所在的文本文件A中。
四、实验步骤
1.首先创建Student类和Test类两个类
2.在Student类里完成学生所需信息
3.Test类里利用scanner函数首先输入学生信息，然后读取文本文件长恨歌
4.使用readLine方法，一次读一行，然后在每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”之后写入到A文本里面
5.使用replace方法将字符串替换为空，然后算出出现次数
6.利用switch函数来循环选择进行查字或词语出现的次数或者选择退出程序
7.在其中加入try-catch函数来处理异常输入
五.核心代码
            FileReader fileReader = new FileReader("C:\\长恨歌.txt");
            BufferedReader bufferedReader = new BufferedReader(fileReader);
            Writer writer = new FileWriter(new File("C:\\作业.txt"));
用于读取文件内容并写一个输出文件
a:
            while (true) {
                System.out.println("输入1或者2选择查询字和词或者退出");
                Scanner in = new Scanner(System.in);
                int z = in.nextInt();
                switch (z) {
                    case 1:
                        Scanner y = new Scanner(System.in);
                        System.out.println("请输入想要查询的字:");
                        String c = y.nextLine();
                        int count = (str.length() - str.replace(c, "").length()) / c.length(); //使用replace方法将字符串替换为空，然后求长度
                        System.out.println(count);
                        break;
                    case 2:
                        System.out.println("退出");
                        break a;
                }
            }
 用switch来实现不断查询想要的字和结束查询
 String str = bufferedReader.readLine();
            String regex = "(.{7})";
            str = str.replaceAll(regex, "$1，");
            StringBuffer x = new StringBuffer(str);
            for (int  i = 15; i <289; i = i + 17) {
                x.replace(i, i + 1, "。\n");
            }
  用来分句
六、实验截图
![Image text]()
七.实验感想
1.通过这次实验我学会了如何读取文本文件和在文件中写入东西并存进一个新文件
2.这次实验巩固了构造学生类的方法
3.这次实验掌握了分词处理，对古诗词的分句有了一定的了解。
