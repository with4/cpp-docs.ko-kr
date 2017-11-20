---
title: "컴파일러 오류 C3418 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3418
dev_langs: C++
helpviewer_keywords: C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0ae644c17a39e574984dc8bb0689955fd1bef2be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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