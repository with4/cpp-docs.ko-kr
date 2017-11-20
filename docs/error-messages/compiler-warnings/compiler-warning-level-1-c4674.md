---
title: "컴파일러 경고 (수준 1) C4674 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4674
dev_langs: C++
helpviewer_keywords: C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43d34279ded00851962008837d0bf6cd76eaff7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4674"></a>컴파일러 경고(수준 1) C4674
'method'는 'static'으로 선언해야 하며 하나의 매개 변수만 가져야 합니다.  
  
변환 연산자의 서명이 잘못되었습니다. 메서드는 사용자 정의 변환으로 간주되지 않습니다. 연산자 정의에 대 한 자세한 내용은 참조 하십시오. [사용자 정의 연산자 (C + + /cli CLI)](../../dotnet/user-defined-operators-cpp-cli.md) 및 [사용자 정의 변환 (C + + /cli CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4674를 생성합니다.  
  
```  
// C4674.cpp  
// compile with: /clr /WX /W1 /LD  
ref class G {  
   int op_Implicit(int i) {   // C4674  
      return 0;  
   }  
};  
```  
