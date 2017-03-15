---
title: "컴파일러 오류 C3138 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3138"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3138"
ms.assetid: 364ee9e8-9358-410e-bd35-9c4a226a3753
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3138
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : 'attribute' 인터페이스는 IDispatch에서 상속하거나 IDispatch에서 상속하는 인터페이스에서 상속해야 합니다.  
  
 [dual](../../windows/dual.md) 또는 [dispinterface](../../windows/dispinterface.md) 특성을 사용하는 인터페이스에 직접 또는 간접 기본 인터페이스로 `IDispatch`가 지정되어 있지 않습니다.  
  
 다음 예제에서는 C3138 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3138.cpp  
#include <unknwn.h>  
  
[ object, uuid("77ac9240-6e9a-11d2-97de-0000f805d73b") ]  
__interface IMyCustomInterface  
{  
   HRESULT mf1(void);  
};  
  
[ dispinterface, uuid("3536f8a0-6e9a-11d2-97de-0000f805d73b") ]  
__interface IMyDispInterface : IUnknown  
{  
   [id(1)] HRESULT mf2(void);  
};  
  
[ object, dual, uuid("34e90a10-6e9a-11d2-97de-0000f805d73b") ]  
__interface IMyDualInterface : IMyCustomInterface  // C3138 expected  
{  
   HRESULT mf3(void);  
};  
```