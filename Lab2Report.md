# Lab 2 Report
## Part 1
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    ArrayList<String> allStrings = new ArrayList<String>();
    String temp = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return temp;
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    allStrings.add(parameters[1]);
                    temp += parameters[1] + "\n";
                    return temp;
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
![Image](/LabReport2Image1.png)
![Image](/LabReport2Image2.png)
1. For the first screenshot, the string `Hello` is added in to the String `temp` using code from lines 15 - 22. The query in the URI matches the parameter. It eventually returns `temp` which includes the String `Hello`. For the second screenshot, it also uses the line 15 - 22 but it adds `how are you` to `temp`. The reason that it displays as it own lines is becuase I used `String.format()` method along with `\n` to make sure each input has its own line.
2. With regards to the values in the method, when a new input is entered, it affects the String that is been inputed which is `parameters[1]`. The String value of `parammeters[1]` is also different depending on the input. URI is different depending on the action that takes place. The URI either ends with `/` or `add-message?s=`. 
3. The values change base on the request because I used an if-else statement to match each request to a specific action. If the URI ends with `\`, it only displays the current contents in `temp`. However, if it adds with `add-messages?s=`, then it would add the input into `temp` and display `temp` after changes were made. 
## Part 2
1. A failiure-inducing input for the buggy program (JUnit test)
```
@Test
  public void testReverseInPlaceError () {
    int[] input1 = {1, 2, 3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3, 2, 1}, input1);
  }
```
2. A input that doesn't induce a failure for the buggy program (JUnit test)
```
@Test 
   public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```
3. Output of the running test for the method `reverseInPlace(int[] arr)` in `ArrayExamples.java`. 
Pass `testReversedInPlace()`:
![Image](/LabReport2Image4.png)
Error `testReversedInPlaceError()`:
![Image](/LabReport2Image3.png)
4. Before and After

**Code (Before)**
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
**Code (After)**
```
static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i ++) {
      temp[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i ++) {
      arr[i] = temp[arr.length - i - 1];
    }
  }
```
5. The fix addresses the issue because the bug that causes the symptom to appear is because the original code doesn' account for that fact that when it transfer the integer from the original index to the new index, it erases the original number that were in the new index. Since it doesn't keep tract of that the original numbers in their respective index, it wouldn't be able to reverse the order of the array. In the new code, the program create a new array to keep track of the original integer in their original index and flip it onto the original array. Therefore, it wouldn't have the issue of "forgetting" the original integer in each index". 
## Part 3
I learned how to better use JUnit for debugging. At first I had trouble to understand how to use JUnit and how to interpret the outputs of JUnit testings. I also learned how to GitHub and how to use GitHub to finish assignments for CSE15L. Finally, I learned how to create a basic search engine and create an URI. 
