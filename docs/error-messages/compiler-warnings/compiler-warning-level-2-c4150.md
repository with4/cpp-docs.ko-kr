---
title: 컴파일러 경고 (수준 2) C4150 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4150
dev_langs:
- C++
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3108da1b203160456e0823b4d9a3fd594b705a8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4150"></a>컴파일러 경고 (수준 2) C4150
불완전 한 형식 'type';에 대 한 포인터 삭제 소멸자가 호출 되지  
  
 **삭제** 연산자가 호출 되어 선언 되었지만 정의 되지 않은 형식을 삭제 했으므로 컴파일러는 소멸자를 찾을 수 없습니다.  
  
 다음 샘플에서는 C4150 오류가 생성 됩니다.  
  
```  
// C4150.cpp  
// compile with: /W2  
class  IncClass;  
  
void NoDestruct( IncClass* pIncClass )  
{  
   delete pIncClass;  
} // C4150, define class to resolve  
  
int main()  
{  
}  
```