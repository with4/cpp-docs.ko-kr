---
title: "컴파일러 경고 (수준 1) C4683 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4683
dev_langs: C++
helpviewer_keywords: C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0a8ca498a3c95a1b37229f6ac973cf74a8e28ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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