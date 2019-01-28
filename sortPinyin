package testday;
import java.text.Collator;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class testPinyin {

	public static void main(String[] args) {
		List<Student> stLst = new ArrayList<>();
		
		Student a = new Student("啊戴",60);
		Student b = new Student("在王",90);
		Student c = new Student("是王",80);		
		Student d = new Student("吧萱",95);				
		
		stLst.add(a);
		stLst.add(b);
		stLst.add(c);
		stLst.add(d);	
		
		Student[] sts = new Student[]{
				new Student("小萱",95),
				new Student("小戴",60),
				new Student("小王",90),
				new Student("老王",80)
				
		}; 
		Collections.sort(stLst, new StudentComparator());
		for(Student x : stLst) {
			System.out.println(x.toString());
		}
	}
}

class Student {
	private String name;
	private double score;
	public Student(String name,double score){
		this.name = name;
		this.score = score;
	}
	public double getScore(){
		return this.score;
	}
	public String getName(){
		return this.name;
	}
	@Override
	public String toString() {
		return "姓名:"+this.name+",分数:"+this.score;
	}
}
class StudentComparator implements Comparator<Student> {
	@Override
	public int compare(Student o1,Student o2) {
		if(HanZiSortUti.compChineseWords(o1.getName(), o2.getName()) == 1) {
			System.out.println("1");
			return 1;
		}else if(HanZiSortUti.compChineseWords(o1.getName(), o2.getName()) == 0) {
			System.out.println("-1");
			return -1;
		}else {
			System.out.println("0");
			return 0;
		}
	}
}
class HanZiSortUti {
	
	private final static Comparator<Object> CHINA_COMPARE = Collator.getInstance(java.util.Locale.CHINA);
	
	public static int compChineseWords(String word1,String word2){			
		List<String> compList=new ArrayList<String>();
		compList.add(word1);
		compList.add(word2);
        //通过collections的sort方法进行排序
		Collections.sort(compList, CHINA_COMPARE);
        //自定义一个排序规则
		if(word1.equals(compList.get(0))){
			return 0;
		}else{
			return 1;
		}
	}
}
















