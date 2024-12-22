# Notes link :

https://drive.google.com/drive/folders/11aSPUTg1uJkKc1f3ABd5hylLWxwGX4JA

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

## N Stair Problem→Either one or 2 steps and their combinations

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7ee69b78-33c3-4606-8c90-189cb2753570/4dcbd6de-2f9b-4826-8def-0e308870b52c/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7ee69b78-33c3-4606-8c90-189cb2753570/88f148af-ed27-46b6-b13e-25ac54858ecd/image.png)

```cpp
int stair(int num){

    if(num==1) return 1;
    if(num==2) return 2;
    return stair(num-1)+ stair(num-2);
    
}
```

## MAZE Path Problem

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/7ee69b78-33c3-4606-8c90-189cb2753570/d99f06da-330d-449f-ace3-e2dff6b13357/image.png)