# **Linked list Part 1**

## **Node Class**

## **Display and size**

## **Linked class (Display and insert at end)**

## **Insert at end**

```
**void InsertAtEnd(int val){
        Node* temp=new Node(val);
        if(size==0){
            head=tail=temp;

        }
        else{
            tail->next=temp;
            tail=temp;
        }
            size++;
    }**

```

## **Display**

```cpp
**void display(){
        Node* temp=head;
        while(temp!=NULL){
            cout<<temp->val<<" ";
            temp=temp->next;
        }
        cout<<endl;
}**
```

## **Insert at head**

```cpp
**void InsertAtHead(int val){
        Node* temp=new Node(val);
        if(size==0){
            head=tail=temp;
        }
        else{
            temp->next=head;
            head=temp;
        }
        size++;

}**
```

## **Insert at any index**

```cpp
**void Insert(int idx,int val){
    if(idx<0 || idx> size){
        cout<<"index cannot be negative "<<endl;
    }
    else if(idx==0){
        InsertAtHead(val);
        size++;
    }
    else if(idx==size){
        InsertAtEnd(val);
        size++;
    }
    else{
    Node* t=new Node(val);
    Node* temp=head;
    while(idx-1!=0){
        temp=temp->next;
        idx--;
    }
    t->next=temp->next;
    temp->next=t;

    size++;

    }
}**
```