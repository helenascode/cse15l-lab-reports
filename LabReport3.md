Helena Phamova - **CSE 15L Lab Report 3**

---

**PART 1**
The method with a bug that I chose:
``
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length - 1; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
``

My failure-inducing test input:

``

``



---

**PART 2**

