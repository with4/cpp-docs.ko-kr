---
title: 컴파일러 오류 C3633 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3633
dev_langs:
- C++
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 341123f51a065cc8dcd43425f65b21edaf00abbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3633"></a>컴파일러 오류 C3633
'member' 관리 되는 'type'의 멤버로 정의할 수 없습니다.  
  
CLR 참조 클래스 데이터 멤버는 비-POD c + + 형식이 될 수 없습니다.  POD 네이티브 형식은 CLR 형식에만 인스턴스화할 수 있습니다.  예를 들어 복사 생성자 또는 대입 연산자는 POD 형식을 포함할 수 없습니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3633 오류가 발생 합니다.  
  
```  
// C3633.cpp  
// compile with: /clr /c  
#pragma warning( disable : 4368 )  
  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
ref class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```  
