---
title: "컴파일러 오류 C2775 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2775"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2775"
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2775
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 이 속성과 연결된 'get' 메서드는 없습니다.  
  
 [property](../../cpp/property-cpp.md) 확장 특성을 통해 선언된 데이터 멤버에는 `get` 함수가 지정되어 있지 않은데 식이 해당 값을 검색하려고 합니다.  
  
 다음 샘플에서는 C2775 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2775.cpp  
struct A {  
   __declspec(property(put=PutProp2, get=GetProp2)) int prop2;  
   int GetProp2(){return 0;}  
   void PutProp2(int){}  
  
   __declspec(property(put=PutProp)) int prop;  
   int PutProp(void){}  
  
};  
  
int main() {  
   A* pa = new A;  
   int x;  
   x = pa->prop;   // C2775  
   x = pa->prop2;  
}  
```