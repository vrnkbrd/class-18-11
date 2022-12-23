# class-18-11
###Task 6kyu
#### My solution 
```Java
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
```
#### Fav sol
```Java
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
```

### Task 7 kyu
DESCRIPTION:
John wants to decorate the walls of a room with wallpaper. He wants a fool-proof method for getting it right.
John knows that the rectangular room has a length of l meters, a width of w meters, a height of h meters. The standard width of the rolls he wants to buy is 52 centimeters. The length of a roll is 10 meters. He bears in mind however, that it’s best to have an extra length of wallpaper handy in case of mistakes or miscalculations so he wants to buy a length 15% greater than the one he needs.
Last time he did these calculations he got a headache, so could you help John?
Task
Your function wallpaper(l, w, h) should return as a plain English word in lower case the number of rolls he must buy.
Example:
wallpaper(4.0, 3.5, 3.0) should return "ten"
wallpaper(0.0, 3.5, 3.0) should return "zero"

#### My solution:
```Java
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
```
#### Fav solution: 
```Java
public class EasyWallpaper {
    private static String[] nbs = {"zero","one","two","three","four","five","six","seven","eight","nine","ten","eleven","twelve","thirteen","fourteen","fifteen","sixteen","seventeen","eighteen","nineteen","twenty"};
    public String wallpaper(double l, double w, double h) {
        if (l*w*h==0) return nbs[0];
        double roomM2 = 2 * (l * h) + 2 * (w * h);
        double rollM2 = 10 * .52;
        int r = (int)((roomM2 / rollM2) * 1.15 + 1);
        return nbs[r];
    }
}
```
