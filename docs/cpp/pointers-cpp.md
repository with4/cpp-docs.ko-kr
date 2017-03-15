---
title: "포인터 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "선언, 포인터"
  - "선언자, 포인터"
  - "포인터"
  - "포인터, 선언"
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 포인터
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

포인터는 다음 시퀀스를 사용하여 선언합니다.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator ;  
```  
  
 여기서 모든 유효한 포인터 선언자를 `declarator`에 사용할 수 있습니다.  단순한 포인터 선언자 구문은 다음과 같습니다.  
  
```  
* [cv-qualifiers] identifier [= expression]  
```  
  
 1.  선언 지정자:  
  
-   선택적 저장소 클래스 지정자.  자세한 내용은 [지정자](../cpp/specifiers.md)를 참조하십시오.  
  
-   가리키는 대상 개체의 형식에 적용되는 선택적 `const` 또는 `volatile` 키워드  
  
-   형식 지정자: 가리키는 대상 개체의 형식을 나타내는 형식의 이름  
  
 2.  선언자:  
  
-   선택적 Microsoft 전용 한정자.  자세한 내용은 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)를 참조하십시오.  
  
-   `*` 연산자  
  
-   포인터 자체에 적용되는 선택적 `const` 또는 `volatile` 키워드  
  
-   식별자입니다.  
  
-   선택적 이니셜라이저입니다.  
  
 함수 포인터의 선언자는 다음과 같습니다.  
  
```  
(* [cv-qualifiers] identifier )( argument-list ) [cv-qualifers]  
[exception specification] [= expression];  
```  
  
-   포인터 배열의 경우 구문은 다음과 같습니다.  
  
```  
* identifier [ [ constant-expression ] ]  
```  
  
-   그러나 포인터 선언자는 더 복잡해질 수 있습니다.  자세한 내용은 [선언자](http://msdn.microsoft.com/ko-kr/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)를 참조하십시오.  
  
-   여러 선언자와 해당 이니셜라이저가 단일 선언에서 선언 지정자 뒤에 쉼표로 구분된 목록으로 함께 나타날 수 있습니다.  
  
 포인터 선언의 간단한 예제는 다음과 같습니다.  
  
```  
char *pch;  
```  
  
 위의 선언은 `pch`가 `char` 형식의 개체를 가리키도록 지정합니다.  
  
 보다 복잡한 예제는 다음과 같습니다.  
  
```  
static unsigned int * const ptr;  
```  
  
 위의 선언은 `ptr`이 정적 저장 기간이 포함된 `unsigned` `int` 형식의 개체에 대한 상수 포인터임을 지정합니다.  
  
 다음 예제에서는 여러 포인터가 선언 및 초기화되는 방법을 보여 줍니다.  
  
```  
static int *p = &i, *q = &j;  
```  
  
 위의 예제에서 p 포인터와 q 포인터 모두 `int` 형식의 개체를 가리키며 각각 i 및 j 주소로 초기화됩니다.  저장소 클래스 지정자 `static`은 두 포인터에 모두 적용됩니다.  
  
## 예제  
  
```  
// pointer.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   int i = 1, j = 2; // local variables on the stack  
   int *p;  
  
   // a pointer may be assigned to "point to" the value of  
   // another variable using the & (address of) operator  
   p = & j;   
  
   // since j was on the stack, this address will be somewhere  
   // on the stack.  Pointers are printed in hex format using  
   // %p and conventionally marked with 0x.    
   printf_s("0x%p\n",  p);  
  
   // The * (indirection operator) can be read as "the value  
   // pointed to by".  
   // Since p is pointing to j, this should print "2"  
   printf_s("0x%p %d\n",  p, *p);  
  
   // changing j will change the result of the indirection  
   // operator on p.  
   j = 7;  
   printf_s("0x%p %d\n",  p, *p );  
  
   // The value of j can also be changed through the pointer  
   // by making an assignment to the dereferenced pointer  
   *p = 10;  
   printf_s("j is %d\n", j); // j is now 10  
  
   // allocate memory on the heap for an integer,  
   // initialize to 5  
   p = new int(5);  
  
   // print the pointer and the object pointed to  
   // the address will be somewhere on the heap  
   printf_s("0x%p %d\n",  p, *p);  
  
   // free the memory pointed to by p  
   delete p;  
  
   // At this point, dereferencing p with *p would trigger  
   // a runtime access violation.  
  
   // Pointer arithmetic may be done with an array declared  
   // on the stack or allocated on the heap with new.  
   // The increment operator takes into account the size   
   // of the objects pointed to.  
   p = new int[5];  
   for (i = 0; i < 5; i++, p++) {  
      *p = i * 10;  
      printf_s("0x%p %d\n", p, *p);  
   }  
  
   // A common expression seen is dereferencing in combination  
   // with increment or decrement operators, as shown here.  
   // The indirection operator * takes precedence over the   
   // increment operator ++.   
   // These are particularly useful in manipulating char arrays.  
   char s1[4] = "cat";  
   char s2[4] = "dog";  
   char* p1 = s1;  
   char* p2 = s2;  
  
   // the following is a string copy operation  
   while (*p1++ = *p2++);  
  
   // s2 was copied into s1, so now they are both equal to "dog"  
   printf_s("%s %s", s1, s2);  
}  
```  
  
  **0x0012FEC8**  
**0x0012FEC8 2**  
**0x0012FEC8 7**  
**j \= 10**  
**0x00320850 5**  
**0x00320850 0**  
**0x00320854 10**  
**0x00320858 20**  
**0x0032085C 30**  
**0x00320860 40**  
**dog dog**   
## 예제  
 다음은 데이터 구조\(이 경우에는 연결된 목록\)에서 포인터를 사용하는 방법을 보여 주는 또 다른 예제입니다.  
  
```  
// pointer_linkedlist.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct NewNode {  
   NewNode() : node(0){}  
   int i;  
   NewNode * node;  
};  
  
void WalkList(NewNode * ptr) {  
   if (ptr != 0) {  
      int i = 1;  
      while (ptr->node != 0 ) {  
         cout << "node " << i++ << " = " << ptr->i << endl;  
         ptr = ptr->node;  
      }  
      cout << "node " << i++ << " = " << ptr->i << endl;  
   }  
}  
  
void AddNode(NewNode ** ptr) {  
   NewNode * walker = 0;  
   NewNode * MyNewNode = new NewNode;  
   cout << "enter a number: " << endl;  
   cin >> MyNewNode->i;  
  
   if (*ptr == 0)  
      *ptr = MyNewNode;  
   else  {  
      walker = *ptr;  
      while (walker->node != 0)  
         walker = walker->node;  
  
      walker->node = MyNewNode;  
   }  
}  
  
int main() {  
   char ans = ' ';  
   NewNode * ptr = 0;  
   do {  
      cout << "a (add node)  d (display list)  q (quit)" << endl;  
      cin >> ans;  
      switch (ans) {  
      case 'a':  
         AddNode(&ptr);  
         break;  
      case 'd':  
         WalkList(ptr);  
         break;  
      }  
   } while (ans != 'q');  
}  
```  
  
  **`a 45 d a 789 d q`a \(add node\) d \(display list\) q \(quit\)**  
**enter a number:**   
**a \(add node\) d \(display list\) q \(quit\)**  
**node 1 \= 45**  
**a \(add node\) d \(display list\) q \(quit\)**  
**enter a number:**   
**a \(add node\) d \(display list\) q \(quit\)**  
**node 1 \= 45**  
**node 2 \= 789**  
**a \(add node\) d \(display list\) q \(quit\)**   
## 참고 항목  
 [C\+\+ Abstract Declarators](http://msdn.microsoft.com/ko-kr/e7e18c18-0cad-4450-942b-d27e1d4dd088)   
 [포인터 형식의 더하기](../misc/addition-of-pointer-types.md)   
 [간접 참조 연산자: \*](../cpp/indirection-operator-star.md)   
 [주소 연산자: &](../cpp/address-of-operator-amp.md)