---
title: "컴파일러 오류 C3418 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3418
dev_langs:
- C++
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e36fa3a27a122db715f84405b0484508fb13e8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3418"></a>컴파일러 오류 C3418
액세스 지정자 'specifier'는 지원되지 않습니다.  
  
CLR 액세스 지정자를 잘못 지정했습니다.  자세한 내용은 형식 표시 유형 및 멤버 표시 유형에서를 참조 하십시오. [하는 방법: 정의 및 소비 클래스와 구조체 (C + + CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)합니다.  
  
## <a name="example"></a>예  
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