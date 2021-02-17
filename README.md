# GNOMESORT

import java.util.ArrayList;
import java.util.Collection;
import java.util.HashSet;
import java.util.List;
import java.util.Random;
import java.util.Set;


public class GnomeSort<E extends Comparable<? super E>> {

 
    public Collection<E> sort(Collection<E> vector) {

        int i = 1;
        List<E> result = new ArrayList<E>(vector);

        while (i < result.size()) {

            if (i == 0 || result.get(i - 1).compareTo(result.get(i))<= 0) {
                i++;
            } else {
                E temp = result.get(i - 1);

                result.set(i - 1, result.get(i));

                result.set(i, temp);
                i--;
            }
        }

        return result;
    }

  
    public static void main(String[] args) {

        GnomeSort<Integer> gnomeSort = new GnomeSort<Integer>();

        final int size = 50;

        final Random random = new Random();

        List<Integer> list = new ArrayList<Integer>(size);

        for (int i = 0; i < size; i++) {
            list.add(random.nextInt());
        }
    }
}
