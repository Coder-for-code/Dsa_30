3. https://www.interviewbit.com/problems/repeat-and-missing-number-array/

![3 1](https://user-images.githubusercontent.com/37560890/166860407-ccd6de9b-371e-4c96-84c1-1736ccb06114.jpg)
![3](https://user-images.githubusercontent.com/37560890/166860414-a6b5538d-16d0-4f24-8bbc-f8abe8c48bb6.jpg)


Solution 1: Using Count Sort
```cpp


vector<int> find_missing_repeating(vector<int> array)
{
    int n = array.size() + 1;

    vector<int> substitute(n, 0); // initializing the substitute array with 0 of size n+1.

    vector<int> ans;              // initializing the answer  array .

    for (int i = 0; i < array.size(); i++)
    {
        substitute[array[i]]++;
    }

    for (int i = 1; i <= array.size(); i++)
    {
        if (substitute[i] == 0 || substitute[i] > 1)
        {
            ans.push_back(i);
        }
    }

    return ans;
}

Time Complexity: O(N) + O(N) (as we are traversing 2 times )
Space Complexity: O(N) As we are making new substitute array


```


Solution 2: Using Maths 
```cpp


vector<int>missing_repeated_number(const vector<int> &A) 
{
    long long int len = A.size();
    long long int S = (len * (len+1) ) /2;
    long long int P = (len * (len +1) *(2*len +1) )/6;
    long long int missingNumber=0, repeating=0;
     
    for(int i=0;i<A.size(); i++)
    {
       S -= (long long int)A[i];
       P -= (long long int)A[i]*(long long int)A[i];
    }
     
    missingNumber = (S + P/S)/2;
    repeating = missingNumber - S;

    vector <int> ans;

    ans.push_back(repeating);
    ans.push_back(missingNumber);

    return ans;
}

Time Complexity: O(N) 
Space Complexity: O(1) As we are NOT USING EXTRA SPACE

```

Solution 3: XOR
```cpp

vector < int >Solution::repeatedNumber (const vector < int >&arr) 
{
    /* Will hold xor of all elements and numbers from 1 to n */
    int xor1;

    /* Will have only single set bit of xor1 */
    int set_bit_no;

    int i;
    int x = 0; // missing
    int y = 0; // repeated
    int n = arr.size();

    xor1 = arr[0];

    /* Get the xor of all array elements */
    for (i = 1; i < n; i++)
        xor1 = xor1 ^ arr[i];

    /* XOR the previous result with numbers from 1 to n */
    for (i = 1; i <= n; i++)
        xor1 = xor1 ^ i;

    /* Get the rightmost set bit in set_bit_no */
    set_bit_no = xor1 & ~(xor1 - 1);

    /* Now divide elements into two sets by comparing a rightmost set bit
       of xor1 with the bit at the same position in each element.
       Also, get XORs of two sets. The two XORs are the output elements.
       The following two for loops serve the purpose */

    for (i = 0; i < n; i++) 
    {
        if (arr[i] & set_bit_no)
            /* arr[i] belongs to first set */
            x = x ^ arr[i];

        else
            /* arr[i] belongs to second set */
            y = y ^ arr[i];
    }

    for (i = 1; i <= n; i++) 
    {
        if (i & set_bit_no)
            /* i belongs to first set */
            x = x ^ i;

        else
            /* i belongs to second set */
            y = y ^ i;
    }

    // NB! numbers can be swapped, maybe do a check ?
    int x_count = 0;
    
    for (int i=0; i<n; i++) 
    {
        if (arr[i]==x)
            x_count++;
    }
    
    if (x_count==0)
        return {y, x};
    
    return {x, y};
}

Note: This method doesn???t cause overflow, but it doesn???t tell which one occurs twice and which one is missing. We can add one more step that checks which one is missing and which one is repeating by iterating over the array. This can be easily done in O(N) time.

Time Complexity: O(N) 
Space Complexity: O(1) As we are NOT USING EXTRA SPACE
```
