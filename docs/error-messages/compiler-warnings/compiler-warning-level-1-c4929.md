---
title: "컴파일러 경고 (수준 1) C4929 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4929
dev_langs: C++
helpviewer_keywords: C4929
ms.assetid: 95f8ab4f-4468-4caa-acd5-8f4592f03b3c
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38bfd20538db1f11ab2f7f20ab4079e9ed201bc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4929"></a>컴파일러 경고(수준 1) C4929
'file': 형식 라이브러리로 있습니다. 'embedded_idl' 한정자를 무시합니다.  
  
 Embedded_idl 특성 [#import](../../preprocessor/hash-import-directive-cpp.md) 되었으므로 공용 구조체 형식 라이브러리에 있는 형식 라이브러리에 적용할 수 없습니다. 이 경고를 해결 하려면 embedded_idl을 사용 하지 마십시오.  
  
## <a name="example"></a>예  
 다음 샘플 구성 요소를 정의 합니다.  
  
```  
// C4929a.cpp  
// compile with: /LD /link /TLBOUT:C4929a.tlb  
#include <objbase.h>  
[module(name="Test")];  
[public, switch_type(short)] typedef union _TD_UNION_TYPE   {  
   [case(24)]  
      float fM;  
   [case(25)]  
      double dMN;  
   [default]  
      int x;  
} TD_UNION_TYPE;  
  
[export, public] typedef struct _TDW_TYPE {  
   [switch_is(sU)] TD_UNION_TYPE w;  
      short sU;  
} TD_TYPE;  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f(TD_TYPE*);  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct C : I {  
   HRESULT f(TD_TYPE*) { return 0; }  
};  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4929 경고가 발생 합니다.  
  
```  
// C4929b.cpp  
// compile with: /c /W1  
#import "C4929a.tlb" embedded_idl   // C4929  
```