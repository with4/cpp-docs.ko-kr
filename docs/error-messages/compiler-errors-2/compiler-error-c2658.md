---
title: "컴파일러 오류 C2658 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2658
dev_langs:
- C++
helpviewer_keywords:
- C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80e7644e949c3d3c605568d820296bbe8310deed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2658"></a>컴파일러 오류 C2658
'member': 익명 구조체/공용 구조체에 재정의  
  
 두 개의 익명 구조체 또는 공용 구조체 멤버 선언을 같은 식별자를 가진 했지만 다른 형식이 포함 되어 있습니다. 아래 [/Za](../../build/reference/za-ze-disable-language-extensions.md), 같은 식별자와 형식 멤버에 대해이 오류를 발생 하기도 합니다.  
  
 다음 샘플에서는 C2658 오류가 생성 됩니다.  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```