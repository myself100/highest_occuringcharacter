# highest_occuringcharacter

package elclipse;
import java.util.*;
public class highest_occuringcharacter {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		String s="Harshisthebestcoder";
		char y[]=s.toCharArray();
		int size=y.length;
		Map<Character,Integer> map=new LinkedHashMap<>();            //using lindked map data structure
		int i=0;
		while(i<size) {
			if(map.containsKey(y[i])==false) {
				map.put(y[i],1);
			}else {
				int old=map.get(y[i]);                                    ////replacing the value
				int newv=old+1;
				map.put(y[i],newv);
			}
			i++;
		}
		Set<Map.Entry<Character,Integer>> lmap= map.entrySet();
		char maxkey=' ';
		int maxval=1;
		for(Map.Entry<Character,Integer>data:lmap) {
			if(data.getValue()>maxval) {
				maxval=data.getValue();
				maxkey=data.getKey();
			}
		}
		System.out.print(maxval + " "+ maxkey);
	}

}

//// time complexity O(N)
