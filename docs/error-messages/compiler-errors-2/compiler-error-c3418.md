---
title: 컴파일러 오류 C3418 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3418
dev_langs:
- C++
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92147a636ff1b087134dd7c2d3fdbdb1398d5135
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3418"></a>컴파일러 오류 C3418
액세스 지정자 'specifier'는 지원되지 않습니다.  
  
CLR 액세스 지정자를 잘못 지정했습니다.  자세한 내용은 형식 표시 유형 및 멤버 표시 유형에서를 참조 하십시오. [하는 방법: 정의 및 소비 클래스와 구조체 (C + + CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3418을 생성합니다.  
  
```cpp  
// C3418.cpp  
// compile with: /clr /c  
ref struct m {  
internal public:   // C3418  
   void test(){}  
};  
  
ref struct n {  
internal:   // OK  
   void test(){}  
};  
```