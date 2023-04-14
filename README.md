# Stack_sequence
package stack;

import java.util.Scanner; 
import java.util.Stack; 
public class Stack_algo {

public static void main(String[] args) {
	// TODO Auto-generated method stub
	
	Scanner sc = new Scanner(System.in);
	
	int n = sc.nextInt(); // 수열의 크기
	int [] a = new int[n];
	
	for(int i = 0; i < a.length; i++) {
		a[i] = sc.nextInt();
	}
	
	Stack<Integer> stack = new Stack();
	StringBuffer bf = new StringBuffer();
	
	int num = 1; // 스택에 입력할 수
	boolean result = true; // 화면에 결괏값을 출력을 제어하기 위한 논리값(true : 수열생성, false: 수열생성불가)
	
	for(int i = 0; i < a.length; i++) {
		int su = a[i];
		
		if(su >= num) {
			while(su >= num) {
				stack.push(num++);
				bf.append("+ ");
			}
			stack.pop();
			bf.append("- ");
		}
		else {
			int p = stack.pop(); // pop 으로 나오는 값을 저장하는 변수방
			if(su > p) {
				System.out.println("No");
				result = false;
				break;
			}
			else {
				bf.append("- ");
				
			}
		}
	}
	if(result)System.out.println(bf);
	
	
  }
}
