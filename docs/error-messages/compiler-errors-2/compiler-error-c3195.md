---
title: "컴파일러 오류 C3195 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3195
dev_langs:
- C++
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 840aa93a7955c6eda2720da8457624e00fe97fca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3195"></a>컴파일러 오류 C3195
'operator': 예약어이므로 값 형식 또는 ref 클래스의 멤버로 사용할 수 없습니다. CLR 또는 WinRT 연산자는 'operator' 키워드를 사용하여 정의해야 합니다.  
  
컴파일러가 Managed Extensions for C++ 구문을 사용하는 연산자 정의를 발견했습니다. 연산자에 대 한 c + + 구문을 사용 해야 합니다.  
  
다음 샘플에서는 C3195 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```