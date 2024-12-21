## **Factorial of a Number**

```cpp
**int fact(int num)
{
    if (num == 0 || num == 1) return 1;
    int result = num * fact(num - 1);
    return result;
}**
```

## **Sum form 1 to N**

```cpp
**void sum(int s,int n){
    if(n==0){
        cout<<s;
        return;
    }

    sum(s+n,n-1);
}**
```

## **Calculate a^b**

```cpp
**int pow(int a,int b){
    if(b==1) return a;

    return a* pow(a,b-1);
}**
```

## Fibonacci series

```cpp
**int fibo(int n){
    if(n==1) return 1;
    if(n==2) return 1;
    return fibo(n-1) + fibo(n-2);
}**
```

##