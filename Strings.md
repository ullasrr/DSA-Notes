# **Substr function**

### **substr()**

### **to_string() → converts integer to strings**

## **is_It_Anagram program**

```cpp
**#include<iostream>
#include<string>
#include<algorithm>

using namespace std;

int main(){

    string s1="all";
    string s2="lla";
    sort(s1.begin(),s1.end());
    sort(s2.begin(),s2.end());
    if(s1==s2){
        cout<<"true";
    }
    else cout<<"false";

return 0;
}**
```

## **Stringstream class**

**Syntax you should remember** 

```cpp
**#include <sstream>
using namespace std;

int main()
{
    string str = "ullas is     studing";

    stringstream ss(str);
    string temp;

    while(ss>>temp){
        cout<<temp<<endl;
    }

    return 0;
}**
```

## **Given a sentence in str, return the word that is occuring most number of times in that sentence**

### **Done using string stream and vector of string**

```cpp
**string str = "ullas is a student. He is a a good";
    stringstream ss(str);
    string temp;
    vector<string> v;

    while (ss >> temp)
    {
        v.push_back(temp);
    }

    sort(v.begin(), v.end());
    int count = 1;
    int maxCount = 1;
    for (int i = 0; i < v.size(); i++)
    {

        if (v[i] == v[i - 1])
        {
            count++;
        }
        else
            count = 1;

        maxCount = max(maxCount, count);
    }
    cout << maxCount;
count=1;
cout<<endl;
    for (int i = 0; i < v.size(); i++){
        if(v[i]==v[i-1]) count++;
        else count=1;

        if(count==maxCount){
            cout<<v[i]<<endl;
        }

    }** 
```

## **Stoi → string to integer**

## **Stoll → string to long long**

# **Longest common prefix string LC 14**

```cpp
**class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        int x=strs.size();
        if(x==1) return strs[0];
        sort(strs.begin(),strs.end());
        string first=strs[0];
        string last=strs[x-1];
        int n=first.length();
        string s="";
        for(int i=0;i<n;i++){
            if(first[i]==last[i]){
                s += first[i];
            }
            else return s;
           
            
        }

return s;

        
    }  
    
};**
```