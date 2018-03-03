---
title: "컴파일러 오류 C3763 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3763
dev_langs:
- C++
helpviewer_keywords:
- C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a299d6caafc0c6cc4349a602a4849d05cad7015d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3763"></a>컴파일러 오류 C3763
'type': 'retval' 및 'out' 데이터 포인터 형식에만 나타날 수 있습니다  
  
 [아웃](../../windows/out-cpp.md) 또는 [retval](../../windows/retval.md) 특성 형식 포인터의 매개 변수에 사용할 수 있습니다. 특성을 제거 하거나 형식 포인터의 매개 변수를 확인 합니다.  
  
 다음 샘플에서는 C3763 오류가 생성 됩니다.  
  
```  
// C3763.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atlcom.h>  
  
[ module(name=test) ];  
  
[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IF84 : IDispatch  
{  
   [id(0x00000002)]HRESULT m2([out]unsigned char);  
};  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]  
class CF84 : public IF84  
{   // C3763  
public:  
   HRESULT __stdcall m2(unsigned char i)  
   {  
      return S_OK;  
   }  
};  
  
int main()  
{  
}  
```