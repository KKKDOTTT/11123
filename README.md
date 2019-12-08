# 11123综合性实验 学生选课系统
==========
实验目的
--------
1、总结查找之前的选课系统<br>
2、使用GUI编写代码创建出一个操作界面<br>
3、编写调用不同类实现系统<br>
4、保存数据并读取数据<br>
5、异常处理<br>

实验内容
--------
一、代码中类的种类<br>
属性实例：人员（编号、姓名、性别....）<br>
         任课教师（编号、姓名、性别、所授课程....）<br>
         学生（编号、姓名、性别、所选课程....）<br>
         课程信息（编号、课程名称、上课地点、时间、授课教师....）<br>
         
实验步骤
-------
1、用GUI方法打开创建的窗口，并输入信息，若报错，运用if语句运用判断<br>
2、输入学生、任课教师、教师信息<br>
3、学生选课、退课、课表查询<br>

核心代码
--------
```
setTitle("欢迎光临");
  setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
  setBounds(100, 100, 450, 300);

```
登陆界面
```
Label label = new Label("课程号: ");
  label.setFont(new Font("PLAIN", Font.BOLD | Font.ITALIC, 12));
  GridBagConstraints gbc_label = new GridBagConstraints();
  gbc_label.insets = new Insets(0, 0, 5, 5);
  gbc_label.gridx = 0;
  gbc_label.gridy = 1;
  
  ```
利用GUI创建窗口：
public class Create extends JFrame {
	private static final long serialVersionUID = 1L;
	private JPanel contentPane;
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					Create frame = new Create();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}
  设置课程:课程编号、课程名字、课程地点、课程时间等<br>
```
public Create() {
  setTitle("Create Classes");
  setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
  setBounds(100, 100, 450, 300);
  contentPane = new JPanel();
  contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
  setContentPane(contentPane);
  GridBagLayout gbl_contentPane = new GridBagLayout();
  gbl_contentPane.columnWidths = new int[]{93, 142, 164, 0};
  gbl_contentPane.rowHeights = new int[]{0, 0, 0, 0, 0, 0, 0, 0, 0};
  gbl_contentPane.columnWeights = new double[]{1.0, 0.0, 0.0, Double.MIN_VALUE};
  gbl_contentPane.rowWeights = new double[]{1.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, Double.MIN_VALUE};
  contentPane.setLayout(gbl_contentPane);
  
  Label label = new Label("Class Number: ");
  label.setFont(new Font("Calibri", Font.BOLD | Font.ITALIC, 12));
  GridBagConstraints gbc_label = new GridBagConstraints();
  gbc_label.insets = new Insets(0, 0, 5, 5);
  gbc_label.gridx = 0;
  gbc_label.gridy = 1;
  contentPane.add(label, gbc_label);
  // Create Label
  TextField textField = new TextField();
  GridBagConstraints gbc_textField = new GridBagConstraints();
  gbc_textField.fill = GridBagConstraints.BOTH;
  gbc_textField.insets = new Insets(0, 0, 5, 5);
  gbc_textField.gridx = 1;
  gbc_textField.gridy setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 450, 300);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		GridBagLayout gbl_contentPane = new GridBagLayout();
		gbl_contentPane.columnWidths = new int[]{93, 142, 164, 0};
		gbl_contentPane.rowHeights = new int[]{0, 0, 0, 0, 0, 0, 0, 0, 0};
		gbl_contentPane.columnWeights = new double[]{1.0, 0.0, 0.0, Double.MIN_VALUE};
		gbl_contentPane.rowWeights = new double[]{1.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, Double.MIN_VALUE};
		contentPane.setLayout(gbl_contentPane);		
		Label label = new Label("Class Number: ");
		label.setFont(new Font("Calibri", Font.BOLD | Font.ITALIC, 12));
		GridBagConstraints gbc_label = new GridBagConstraints();
		gbc_label.insets = new Insets(0, 0, 5, 5);
		gbc_label.gridx = 0;
		gbc_label.gridy = 1;
		contentPane.add(label, gbc_label);
		TextField textField = new TextField();
		GridBagConstraints gbc_textField = new GridBagConstraints();
		gbc_textField.fill = GridBagConstraints.BOTH;
		gbc_textField.insets = new Insets(0, 0, 5, 5);
		gbc_textField.gridx = 1;
		gbc_textField.gridy = 1;
		contentPane.add(textField, gbc_textField);
		Label label_1 = new Label("Class Name: ");
		label_1.setFont(new Font("Calibri", Font.BOLD | Font.ITALIC, 12));
		GridBagConstraints gbc_label_1 = new GridBagConstraints();
		gbc_label_1.insets = new Insets(0, 0, 5, 5);
		gbc_label_1.gridx = 0;
		gbc_label_1.gridy = 2;
		contentPane.add(label_1, gbc_label_1);		
		TextField textField_1 = new TextField();
		GridBagConstraints gbc_textField_1 = new GridBagConstraints();
		gbc_textField_1.fill = GridBagConstraints.BOTH;
		gbc_textField_1.insets = new Insets(0, 0, 5, 5);
		gbc_textField_1.gridx = 1;
		gbc_textField_1.gridy = 2;
		contentPane.add(textField_1, gbc_textField_1);		
		Label label_2 = new Label("Class Place: ");
		label_2.setFont(new Font("Cambria", Font.BOLD | Font.ITALIC, 12));
		GridBagConstraints gbc_label_2 = new GridBagConstraints();
		gbc_label_2.insets = new Insets(0, 0, 5, 5);
		gbc_label_2.gridx = 0;
		gbc_label_2.gridy = 3;
		contentPane.add(label_2, gbc_label_2);		
		TextField textField_2 = new TextField();
		GridBagConstraints gbc_textField_2 = new GridBagConstraints();
		gbc_textField_2.fill = GridBagConstraints.BOTH;
		gbc_textField_2.insets = new Insets(0, 0, 5, 5);
		gbc_textField_2.gridx = 1;
		gbc_textField_2.gridy = 3;
		contentPane.add(textField_2, gbc_textField_2);		
		Label label_3 = new Label("Class Time: ");
		label_3.setFont(new Font("Cambria", Font.BOLD | Font.ITALIC, 12));
		GridBagConstraints gbc_label_3 = new GridBagConstraints();
		gbc_label_3.insets = new Insets(0, 0, 5, 5);
		gbc_label_3.gridx = 0;
		gbc_label_3.gridy = 4;
		contentPane.add(label_3, gbc_label_3);	
		TextField textField_3 = new TextField();
		GridBagConstraints gbc_textField_3 = new GridBagConstraints();
		gbc_textField_3.fill = GridBagConstraints.BOTH;
		gbc_textField_3.insets = new Insets(0, 0, 5, 5);
		gbc_textField_3.gridx = 1;
		gbc_textField_3.gridy = 4;
		contentPane.add(textField_3, gbc_textField_3);		
		Label label_4 = new Label("Class Credit: ");
		label_4.setFont(new Font("Cambria", Font.BOLD | Font.ITALIC, 12));
		GridBagConstraints gbc_label_4 = new GridBagConstraints();
		gbc_label_4.insets = new Insets(0, 0, 5, 5);
		gbc_label_4.gridx = 0;
		gbc_label_4.gridy = 5;
		contentPane.add(label_4, gbc_label_4);	
		TextField textField_4 = new TextField();
		GridBagConstraints gbc_textField_4 = new GridBagConstraints();
		gbc_textField_4.fill = GridBagConstraints.BOTH;
		gbc_textField_4.insets = new Insets(0, 0, 5, 5);
		gbc_textField_4.gridx = 1;
		gbc_textField_4.gridy = 5;
		contentPane.add(textField_4, gbc_textField_4);		
		Label label_5 = new Label("Class Teacher: ");
		label_5.setFont(new Font("Calibri", Font.BOLD | Font.ITALIC, 12));
		GridBagConstraints gbc_label_5 = new GridBagConstraints();
		gbc_label_5.insets = new Insets(0, 0, 5, 5);
		gbc_label_5.gridx = 0;
		gbc_label_5.gridy = 6;
		contentPane.add(label_5, gbc_label_5);		
		TextField textField_5 = new TextField();
		GridBagConstraints gbc_textField_5 = new GridBagConstraints();
		gbc_textField_5.fill = GridBagConstraints.BOTH;
		gbc_textField_5.insets = new Insets(0, 0, 5, 5);
		gbc_textField_5.gridx = 1;
		gbc_textField_5.gridy = 6;
		contentPane.add(textField_5, gbc_textField_5);
		Button button = new Button("Create Lessons"); 
		button.setFont(new Font("Calibri", Font.BOLD | Font.ITALIC, 18)); 
		GridBagConstraints gbc_button = new GridBagConstraints();
		gbc_button.fill = GridBagConstraints.BOTH; 
		gbc_button.gridx = 2;
		gbc_button.gridy = 7; 
		contentPane.add(button, gbc_button);
		button.addActionListener(new ActionListener(){
			public void actionPerformed(ActionEvent e) {
				String s= textField.getText();
				String s1= textField_1.getText();
				String s2= textField_2.getText();
				String s3= textField_3.getText();
				String s4= textField_4.getText();
				String s5= textField_5.getText(); 
				String s6 = "Number: "+ s + " Name: "+ s1 +" Place: "+ s2 +" Time: " + s3 +" Credit: "+ s4 + " Teacher: "+ s5+ ";"; 
				if(textField.getText().trim().length()==0||textField_1.getText().trim().length()==0||textField_2.getText().trim().length()==0||
						textField_3.getText().trim().length()==0||textField_4.getText().trim().length()==0||textField_5.getText().trim().length()==0) {
					JOptionPane.showMessageDialog(null, "内容不能为空");
				}
				else {
			    FileWriter writer;
		        try {
		            writer = new FileWriter("C:\\Users\\Kukdo\\Desktop\\Java\\Java实验\\实验5\\classes_teachers.txt",true);
		            writer.append(s6); 
		            writer.flush();
		            writer.close();
		        } catch (IOException e1) {
实验结果
-------
https://github.com/KKKDOTTT/11123/blob/master/微信图片_20191208222239.png
https://github.com/KKKDOTTT/11123/blob/master/微信图片_20191208222255.png
https://github.com/KKKDOTTT/11123/blob/master/微信图片_20191208222310.png
感想
----
很多代码还是需要上网查或者向同学借之后再去了解消化，还属于明白思路，带是实际操作后，很多代码编写的格式还是很生疏，还需要再课余或假期多去学习
