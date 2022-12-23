# LinkedList-Dsa-Serise


class Main {
    Node head;
    private int size;
    
    Main(){
        
        this.size = 0;
    }
    
    
    class Node {
        String data;
        Node next;
        Node(String data){
            this.data=data;
            this.next=null;
            size++;
        }
    }
    
    //add - first , last
    public void addFirst(String data){
        Node newNode = new Node(data);
        if(head == null){
            head = newNode;
            return;
        }
        size++;
        newNode.next = head;
        head = newNode;
    }
    
    public void addLast(String data){
        Node newNode = new Node(data);
        if(head == null){
            head = newNode;
            return;
        }
        size++;
        
        Node currNode = head;
        while(currNode.next != null){
            currNode = currNode.next;
        }
        currNode.next = newNode;
    }
       
       // print list 
      public void  printlist(){
          if(head == null){
              return;
               
          }
          Node currNode = head;
          while(currNode != null){
              System.out.print(currNode.data+"-> ");
              currNode = currNode.next;
          }
          System.out.println("null");
           
      }
    
    // delete first
    public void deleteFirst(){
        if(head == null){
            System.out.println("The List is Empty");
            return;
        }
        size--;
        head = head.next;
    }
    
    // deleteLast;
    public void deleteLast(){
      if(head == null){
            System.out.println("The List is Empty");
            return; 
        }
        size--;
        if(head.next== null){
            head = null;
            return;
        }
        
        Node SecondLast = head;
        Node lastNode = head.next;
         while(lastNode.next !=null){
             lastNode = lastNode.next;
             SecondLast = SecondLast.next;
         }
         SecondLast.next = null;
    }
    
    //size 
    public int  getsize(){
        return size;
    }
    
    public static void main(String args[]){
        Main list = new Main();
        list.addFirst("a");
        list.addFirst("b");
        list.printlist();
        
          list.addFirst("c");
          list.addFirst("d");
        
        list.deleteFirst();
         list.printlist();
        
        list.deleteLast();
         list.printlist(); 
         
        System.out.println(list.getsize());
          
        
    }
}
