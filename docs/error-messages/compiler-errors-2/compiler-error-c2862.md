---
title: 컴파일러 오류 C2862 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2862
dev_langs:
- C++
helpviewer_keywords:
- C2862
ms.assetid: c04d8499-b799-48a1-9fb4-7902a0b0ac8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb9aac4a7c4bd43dcd4f0e688c955619133d375f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2862"></a>컴파일러 오류 C2862
'interface': 인터페이스는 공용 멤버를 하나만 사용할 수 있습니다  
  
 보호 되 고 다른 멤버 함수 에서만에서 전용 멤버를 액세스할 수 있습니다. 이러한 멤버 인터페이스에서 사용 되지 되므로 해당 멤버에 대 한 구현을 제공 하지 않을 수 있습니다.  
  
 다음 샘플에서는 C2862 생성 됩니다.  
  
```  
// C2862.cpp  
// compile with: /c  
#include <unknwn.h>  
  
[object, uuid="60719E20-EF37-11D1-978D-0000F805D73B"]  
__interface IMyInterface {  
   HRESULT mf1(void);   // OK  
protected:  
   HRESULT mf2(int *b);   // C2862  
private:  
   HRESULT mf3(int *c);   // C2862  
};  
```