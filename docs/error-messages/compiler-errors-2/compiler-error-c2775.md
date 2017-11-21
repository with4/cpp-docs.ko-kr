---
title: "컴파일러 오류 C2775 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2775
dev_langs: C++
helpviewer_keywords: C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 823b6886e87a6c5d1a6aaedd7ab8e9b3ad67adb0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2775"></a>컴파일러 오류 C2775
'identifier':이 속성을 통해 연결 된 'get' 메서드가 없습니다  
  
 으로 선언 된 데이터 멤버는 [속성](../../cpp/property-cpp.md) 확장된 특성에 없는 `get` 함수를 지정 하지만 해당 값을 검색 하는 데 식이 하려고 합니다.  
  
 다음 샘플에서는 C2775 오류가 생성 됩니다.  
  
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