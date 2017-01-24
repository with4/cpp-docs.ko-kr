---
title: "delete 연산자 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "delete_cpp"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete 키워드[C++]"
  - "delete 키워드[C++], 개체 할당 해제"
  - "delete 키워드[C++], 구문"
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# delete 연산자 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메모리 블록을 할당 취소합니다.  
  
## 구문  
  
```  
[::] delete cast-expression  
[::] delete [ ] cast-expression  
```  
  
## 설명  
 *cast\-expression* 인수는 [new 연산자](../cpp/new-operator-cpp.md)를 사용하여 만든 개체에 이전에 할당된 메모리 블록에 대한 포인터여야 합니다.  **delete** 연산자는 `void` 형식의 결과를 가지므로 값을 반환하지 않습니다.  예:  
  
```  
CDialog* MyDialog = new CDialog;  
// use MyDialog  
delete MyDialog;  
```  
  
 **new**로 할당되지 않은 개체에 대한 포인터에 **delete**를 사용하면 예기치 않은 결과가 제공됩니다.  그러나 값이 0인 포인터에는 **dlete**를 사용할 수 있습니다.  이 프로비전은 **new**가 실패 시 0을 반환하는 경우 실패한 **new** 작업의 결과를 삭제해도 됨을 의미합니다.  자세한 내용은 [new 및 delete 연산자](../cpp/new-and-delete-operators.md)를 참조하세요.  
  
 배열을 포함하는 기본 제공 형식에 **new** 및 **delete** 연산자를 사용할 수도 있습니다.  `pointer`가 배열을 가리키는 경우 `pointer` 앞에 빈 대괄호를 넣습니다.  
  
```  
int* set = new int[100];  
//use set[]  
delete [] set;  
```  
  
 개체에 **delete** 연산자를 사용하면 해당 메모리가 할당 취소됩니다.  개체가 삭제된 후에 포인터를 역참조하는 프로그램에서는 예기치 않은 결과나 충돌이 발생할 수 있습니다.  
  
 **delete**를 사용하여 C\+\+ 클래스 개체에 대한 메모리 할당을 취소하는 경우 개체의 메모리 할당이 취소되기 전에 개체의 소멸자가 호출됩니다\(개체에 소멸자가 있는 경우\).  
  
 **delete** 연산자에 대한 피연산자가 수정 가능한 l\-value이면 개체가 삭제된 후 해당 값이 정의되지 않습니다.  
  
## 삭제 사용  
 단일 개체와 개체의 배열에 각각 사용되는 [delete 연산자](../cpp/delete-operator-cpp.md)의 두 가지 구문 변형이 있습니다.  다음 코드에서는 두 가지 변형의 차이점을 보여 줍니다.  
  
```  
// expre_Using_delete.cpp  
struct UDType   
{  
};  
  
int main()  
{  
   // Allocate a user-defined object, UDObject, and an object  
   //  of type double on the free store using the  
   //  new operator.  
   UDType *UDObject = new UDType;  
   double *dObject = new double;  
   // Delete the two objects.  
   delete UDObject;  
   delete dObject;   
   // Allocate an array of user-defined objects on the  
   // free store using the new operator.  
   UDType (*UDArr)[7] = new UDType[5][7];  
   // Use the array syntax to delete the array of objects.  
   delete [] UDArr;  
}  
```  
  
 개체에 대해 delete의 배열 형태\(delete \[ \]\)를 사용하는 경우와 배열에 대해 delete의 비배열 형태를 사용하는 경우에는 정의되지 않은 결과가 생성됩니다.  
  
## 예제  
 **delete**를 사용하는 예를 보려면 [new 연산자](../cpp/new-operator-cpp.md)를 참조하세요.  
  
## delete 작동 방식  
 [delete 연산자](../cpp/delete-operator-cpp.md)는 [operator delete](../misc/operator-delete-function.md) 함수를 호출합니다.  
  
 클래스 형식이 아닌 개체의 경우\([class](../cpp/class-cpp.md), [struct](../cpp/struct-cpp.md) 또는 [union](../cpp/unions.md)\) 전역 delete 연산자가 호출됩니다.  클래스 형식 개체의 경우에는 삭제 식이 단항 범위 확인 연산자\(::\)로 시작되면 할당 해제 함수의 이름이 전역 범위에서 확인됩니다.  그렇지 않으면 delete 연산자가 메모리 할당을 해제하기 전에 개체에 대한 소멸자를 호출합니다\(포인터가 null이 아닌 경우\).  delete 연산자는 클래스별로 정의될 수 있습니다. 지정된 클래스에 이러한 정의가 없는 경우 전역 delete 연산자가 호출됩니다.  삭제 식을 사용하여 정적 형식이 가상 소멸자인 클래스 개체를 할당 해제하는 경우, 할당 해제 함수는 개체의 동적 형식에 대한 가상 소멸자를 통해 확인됩니다.  
  
## 참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [new 및 delete 연산자](../cpp/new-and-delete-operators.md)   
 [operator delete 함수](../misc/operator-delete-function.md)