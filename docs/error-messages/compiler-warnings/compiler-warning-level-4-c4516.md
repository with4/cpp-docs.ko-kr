---
title: "컴파일러 경고 (수준 4) C4516 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4516
dev_langs: C++
helpviewer_keywords: C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 137fe601e911b309d28281ecee7e67a88e1bb0a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4516"></a>컴파일러 경고(수준 4) C4516
'class::symbol': 액세스 선언은 사용 되지 않습니다. 멤버를 사용 하 여 선언 보다 더 효율적을 제공합니다.  
  
 ANSI c + + committee 액세스 선언이 했습니다 (없이 파생된 클래스에서 멤버의 액세스 권한을 변경 하는 [를 사용 하 여](../../cpp/using-declaration.md) 키워드)를 오래 된 상태일 수 있습니다. 액세스 선언이 c + +의 이후 버전에서 지원 되지 않을 수 있습니다.  
  
 다음 샘플에서는 C4516 오류가 생성 됩니다.  
  
```  
// C4516.cpp  
// compile with: /W4  
class A  
{  
public:  
   void x(char);  
};  
  
class B : protected A  
{  
public:  
   A::x;  // C4516 on access-declaration  
   // use the following line instead  
   // using A::x; // using-declaration, ok  
};  
  
int main()  
{  
}  
```