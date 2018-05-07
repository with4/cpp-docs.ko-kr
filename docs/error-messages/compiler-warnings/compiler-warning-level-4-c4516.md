---
title: 컴파일러 경고 (수준 4) C4516 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4516
dev_langs:
- C++
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5ca56734d5bd9f2ddf66732ed894d805e368664
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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