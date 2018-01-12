---
title: "컴파일러 경고 (수준 2) C4150 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4150
dev_langs: C++
helpviewer_keywords: C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09267a909ea6e4b0bedd43e6f31a31e778ffb904
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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