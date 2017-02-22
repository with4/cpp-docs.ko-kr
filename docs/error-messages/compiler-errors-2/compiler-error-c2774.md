---
title: "컴파일러 오류 C2774 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2774"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2774"
ms.assetid: 10f428c6-7f49-489a-92ba-6ef978b7caaf
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2774
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 이 속성과 연결된 'put' 메서드는 없습니다.  
  
 [property](../../cpp/property-cpp.md)를 통해 선언된 데이터 멤버에는 `put` 함수가 없는데 식이 해당 값을 설정하려고 합니다.  
  
 다음 샘플에서는 C2774 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2774.cpp  
struct A {  
   __declspec(property(get=GetProp)) int prop;  
   int GetProp(void);  
  
   __declspec(property(get=GetProp2, put=PutProp2)) int prop2;  
   int GetProp2(void);  
   void PutProp2(int);  
};  
  
int main() {  
   A* pa = new A;  
   int val = 0;  
   pa->prop = val;   // C2774  
   pa->prop++;   // C2774  
}  
```