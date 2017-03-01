---
title: "컴파일러 오류 C3366 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 930114bfb06019f13b4f44cc51b72922237a62f6
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3366"></a>컴파일러 오류 C3366
'variable': 정적 데이터 멤버의 관리 되는 또는 WinRTtypes 클래스 정의 내에서 정의 되어야 합니다  
  
 WinRT 또는 .NET 클래스 또는 인터페이스의 정적 멤버를 해당 클래스 또는 인터페이스의 정의 외부에서 참조하려고 했습니다.  
  
 컴파일러는 한 번 통과한 후 메타데이터를 내보내기 위해 클래스의 전체 정의를 알아야 하며 클래스 내에서 정적 데이터 멤버가 초기화되어야 합니다.  
  
 예를 들어 다음 예제에서는 C3366 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  

