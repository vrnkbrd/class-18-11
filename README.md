# class-18-11
Task 6kyu
My solution 
public class FrogJumping {

    public static int solution(int[] a) {
       if (a.length == 0) {
         return -1;
       }
       boolean[] visited = new boolean[a.length];
       int index = 0, count = 0;
       
       while (index >= 0 && index < a.length && !visited[index]) {
         visited[index] = true;
         index += a[index];
         count++;
       }
       return (index >= 0 && index < a.length) ? -1 : count;
    }
}
Fav sol
public class FrogJumping {
  public static int solution(int[] a) {
    if(a.length < 1) return -1;                      // get rid of that degenerate case
    boolean[] b = new boolean[a.length];
    int index = 0;                                   // where my frog woke up
    int count = 0;                                   // variable reserved for return value, counts number of jumps
    while(true) {
      if(index < 0 || index > a.length - 1) break;   // note the index being out of bound implies frog is now free
      if(b[index]) return -1;                        // if the frog has already been here it is a bad sign, surely stuck
      b[index] = true;                               // the frog makes a note to self that it has been here
      index += a[index];                             // jump
      count++;
    }
    return count;
  }
}
Task 7 kyu
sol
public class EasyWallpaper {

    public String wallpaper(double l, double w, double h) {
        if (l == 0.0 || w == 0 || h ==0){
            return "zero";
        }
        double rollArea = 5.2;
        double extra = 1.15;
        double amount = (((l * h * 2.0) + (w * h * 2.0))* extra ) / rollArea;
        String str = "";
        //rounding
        if (0.0 < amount && amount <= 1.0){
            str += "one";
        }
        else if (1.0 < amount && amount <= 2.0){
            str += "two";
        }
        else if (2.0 < amount && amount <= 3.0){
            str += "three";
        }
        else if (3.0 < amount && amount <= 4.0){
            str += "four";
        }
        else if (4.0 < amount && amount <= 5.0){
            str += "five";
        }
        else if (5.0 < amount && amount <= 6.0){
            str += "six";
        }
        else if (6.0 < amount && amount <= 7.0){
            str += "seven";
        }
        else if (7.0 < amount && amount <= 8.0){
            str += "eight";
        }
        else if (8.0 < amount && amount <= 9.0){
            str += "nine";
        }
        else if (9.0 < amount && amount <= 10.0){
            str += "ten";
        }
        else if ( 10.0< amount && amount <= 11.0){
            str += "eleven";
        }
        else if ( 11.0< amount && amount <= 12.0){
            str += "twelve";
        }
        else if ( 12.0< amount && amount <= 13.0){
            str += "thirteen";
        }
        else if ( 13.0< amount && amount <= 14.0){
            str += "fourteen";
        }
        else if ( 14.0< amount && amount <= 15.0){
            str += "fifteen";
        }
        else if ( 15.0< amount && amount <= 16.0){
            str += "sixteen";
        }
        else if ( 16.0< amount && amount <= 17.0){
            str += "seventeen";
        }
        else if ( 17.0< amount && amount <= 18.0){
            str += "eighteen";
        }
        else if ( 18.0< amount && amount <= 19.0){
            str += "nineteen";
        }
        else if ( 19.0< amount && amount <= 20.0){
            str += "twenty";
        }
        else {
            str += "zero";
        }

        //String str = String.valueOf(amount);
        return str;
    }
}
