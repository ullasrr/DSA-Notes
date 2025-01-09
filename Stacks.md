## **Operations on stacks**

```cpp
**st.push();
st.pop();
st.top();
st.size();
st.empty();**
```

## **STL for stack**

**stack<int> st;**

## **Push at bottom**

```cpp
**int main(){
    stack<int> st1;
    stack<int> st2;
    int bottom=3;
    st1.push(10);
    st1.push(20);
    st1.push(30);
    st1.push(40);
    while(st1.size()>0){
        int x=st1.top();
        st2.push(x);
        st1.pop();
    }
    st1.push(bottom);
    while(st2.size()>0){
        int y=st2.top();
        st1.push(y);
        st2.pop();
    }

    while(st1.size()> 0){
        cout<<st1.top();
        st1.pop();
        cout<<endl;
    }
    
return 0;
}**
```

## **Display reverse stack recursively**

```cpp
**void displayrev(stack<int> &st){
    if(st.size()==0) return;
    int x =st.top();
    cout<<st.top()<<endl;
    st.pop();
    displayrev(st);
    st.push(x);
}**
```

## **Display stack recursively**

```cpp
**void displayrev(stack<int> &st){
    if(st.size()==0) return;
    int x =st.top();
    st.pop();
    displayrev(st);
    st.push(x);
    cout<<x<<endl;
}**
```

## **Push at bottom recursively every element**

```cpp
**void pushAtBottom(stack<int> & st,int val){
    if(st.size()==0){
        st.push(val);
        return;
    }
    int x=st.top();
    st.pop();
    pushAtBottom(st,val);
    st.push(x);

}

void reverse(stack<int>& st){
    if(st.size()==1) return;
    int x=st.top();
    st.pop();
    reverse(st);
    pushAtBottom(st,x);
}**
```

### **Overflow → If your stack is full and you are trying to push an element this error is shown**

### **Underflow → If the stack is empty and you call the function pop and top then the underflow condition occur**

## **Array/vector implementation**

```cpp
**// stack using array 
class Stack{
public:
int arr[5];
int idx=-1;

void push(int val){
    idx++;
    arr[idx]=val;
}

void pop(){
    idx--;
}

int top(){
    return arr[idx];
}
int size(){
    return idx+1;
}

};**
```

## Linked List implementation of stacks