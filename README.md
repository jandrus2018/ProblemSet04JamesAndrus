# ProblemSet04JamesAndrus

  //Partial Testing Code
  
    	public static void main(String[] args) {
  
  		// This is the testing code for the pal method
  		String s = "KAYAK";
  		System.out.println(s + (pal(s) ? " is" : " is not") + " a palindrome.");
  
  		// this is the testing code for the factorial method
  		int f = 12;
  		System.out.println(factorial(f));
  
  		// test code to run reverseDisplay method
  		reverseDisplay(12345);
  
  		System.out.println();
  
  		// test code for decimal to binary.
  		System.out.println(decimalToBinary(10));
  	  }
	
	
//Palindrome method

	
  	  public static boolean pal(String s) {
  		s = s.toUpperCase();
  
  		int low = 0;
  		int high = s.length() - 1;
  		if (low >= high)
  			return true;
  		else if (s.charAt(low) != s.charAt(high))
  			return false;
  		else
  			return pal(s.substring(1, high));
  	  	}
  	  
 //Factorial method
  
    	public static int factorial(int n) {
  		if (n < 0) {
  			System.out.println("Only positive integers please");
  			return -1;
  		}
  		return factorial(n, 1);
  	  }
  	  private static int factorial(int n, int result) {
  		if (n <= 1) {
  			return result;
  		} else {
  			return factorial(n - 1, n * result);
  		}
  	  }
  	  
  //Reverse integer display method
  
    	public static void reverseDisplay(int n) {
  		if (n < 0) {
  			System.out.print("-");
  			reverseDisplay(-n);
  		} else if (n < 10) {
  			System.out.print(n);
  		} else {
  			System.out.print(n % 10);
  			reverseDisplay((int) n / 10);
  		}
  	  }
  	  
  //Decimal to Binary method.
  
      public static String decimalToBinary(int n) {
    	if (n < 0) {
    		return "-" + decimalToBinary(-n);
    	} else if (n == 0) {
    		return "0";
    	}
    	return decimalToBinary(n, "");
    	}
    	private static String decimalToBinary(int n, String s) {
    	if (n / 2 < 1) {
    		return '1' + s;
    	} else if (n % 2 == 0) {
    		return decimalToBinary(n / 2, '0' + s);
    	} else {
    		return decimalToBinary(n / 2, '1' + s);
    	}
    	}
    	
  //Precedes method for linked list
  
      public Item precedes(Item data) {
    	Node<Item> temp = first;
    	return precedes(data, temp);
    	}
    	private Item precedes(Item data, Node<Item> temp) {
    	if (temp == null || temp.next == null) {
    		return null;
    	} else if (temp.next.item.equals(data)) {
    		return temp.item;
    	} else {
    		return precedes(data, temp.next);
    	}
    	}
      
