---
title: 컴파일러 경고 (수준 1) C4683 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 418bf25d565c616d5bc4aaf58361c4f28df298ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285345"
---
# <a name="compiler-warning-level-1-c4683"></a>컴파일러 경고(수준 1) C4683
**'**   
 ***함수* ': 이벤트 소스에 'out'-여러 이벤트 처리기를 후크 하는 경우 주의 해야 합니다; 매개 변수**  
  
 둘 이상의 이벤트 싱크를 COM 이벤트 소스를 수신 하는 경우 out 매개 변수 값 무시 될 수 있습니다.  
  
 다음과 같은 상황에서 메모리 누수가 발생 하는지 고려해 야 합니다.  
  
1.  메서드에 out 매개 변수는 내부적으로 할당 된 예를 들어 BSTR 변수가 경우 *입니다.  
  
2.  이벤트에는 여러 명의 처리기 하는 경우 (멀티 캐스트 이벤트는)  
  
 누수 원인은 out 매개 변수는 둘 이상의 처리기에 의해 설정 하지만 마지막 처리기가 호출 사이트에 반환 됩니다.  
  
 다음 샘플에서는 C4683 오류가 생성 됩니다.  
  
```  
// C4683.cpp  
// compile with: /W1 /LD  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="xx") ];  
  
[ object ]  
__interface I {  
   HRESULT f([out] int* pi);  
   // try the following line instead  
   // HRESULT f(int* pi);  
};  
  
[ coclass, event_source(com) ]  
struct E {  
   __event __interface I;   // C4683  
};  
```