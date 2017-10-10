---
title: "컴파일러 오류 C3117 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3117
dev_langs:
- C++
helpviewer_keywords:
- C3117
ms.assetid: dceee392-d4c7-4599-b75e-7aaac7c36fdd
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7f95c5e8073f896c42eebd273ff5923778847a56
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3117"></a>컴파일러 오류 C3117
'%$S': 인터페이스는 단 하나의 기본 클래스를 하나만 사용할 수 있습니다  
  
 여러 기본 클래스에서 상속 하는 인터페이스를 선언 했습니다.  
  
 다음 샘플에서는 C3117 오류가 생성 됩니다.  
  
```  
// C3117.cpp  
#include <windows.h>  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I1  
{  
};  
  
[ object, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface I2  
{  
};  
  
[ object, uuid("00000000-0000-0000-0000-000000000003") ]  
__interface I3 : I1, I2  
{   // C3117  
};  
```
