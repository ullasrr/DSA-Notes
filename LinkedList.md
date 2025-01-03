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


## **Get element at any index**

```cpp
**int getAtIdx(int idx){
    if(idx<0 || idx>=size){
        cout<<"Invalid"<<endl;
        return -1;
    }
    else if(idx==0){
        return head->val;
    }
    else if(idx==size-1){
        return tail->val;
    }
    else{
        Node* temp=head;
        for(int i=1;i<=idx;i++){
            temp=temp->next;
        }
        return temp->val;
    }
}**
```

## **Limitation of Linked List → T.C is O(n)**

## **Delete at Head**

```cpp
**void deleteEleHead(){
    if(size==0) {
        cout<<"Linked List is empty"<<endl;
        return;
    }
        head=head->next;
        size--;
    
}**
```

## **Delete at Tail**

```cpp
**void delete_tail(){
    if(size==0) {
        cout<<"Linked List is empty"<<endl;
        return;
    }
    Node* temp=head;
    while(temp->next->next !=NULL){
        temp=temp->next;
    }
    temp->next=NULL;
    tail=temp;
    size--;
    return;
    
}**
```

## **Delete at any Index**

```cpp
**void delete_any_idx(int idx){
    if(idx<0 || idx>size-1){
        cout<<"invalid"<<endl;
        return;
    }
    else if(idx==0){
        deleteEleHead();
        return;
    }
    else if(idx==size){
        delete_tail();
        return;
    }
    else{
    
    Node* temp=head;
    while(idx>1){
        temp=temp->next;
        idx--;
    }
    temp->next=temp->next->next;
    size--;
    return;}
}**
```