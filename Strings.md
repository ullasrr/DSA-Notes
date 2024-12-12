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