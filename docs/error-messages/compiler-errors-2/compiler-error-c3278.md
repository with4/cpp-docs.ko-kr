---
title: "컴파일러 오류 C3278 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3278
dev_langs: C++
helpviewer_keywords: C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee3c14e1b6d306807735f8d58570089f128a1c19
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3278"></a>컴파일러 오류 C3278
인터페이스 또는 순수 메서드 'method'을(를) 런타임에 직접 호출하지 못합니다.  
  
 인터페이스 메서드 또는 순수 메서드를 호출했지만 허용되지 않습니다.  
  
 다음 샘플에서는 C3278을 생성합니다.  
  
```  
// C3278_2.cpp  
// compile with: /clr  
using namespace System;  
interface class I  
{  
   void vmf();  
};  
  
public ref class C: public I  
{  
public:  
   void vmf()  
   {  
      Console::WriteLine( "In C::vmf()" );  
      I::vmf(); // C3278  
   }  
  
};  
  
int main()  
{  
   C^ pC = gcnew C;  
   pC->vmf();  
}  
```