---
title: "컴파일러 오류 C2787 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2787
dev_langs:
- C++
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 71924ae6e24eba04e27ec366ef73dedc2fa65263
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2787"></a>컴파일러 오류 C2787
'identifier': GUID가이 개체와 연결 되었습니다.  
  
 [__uuidof](../../cpp/uuidof-operator.md) 연산자는 연결 된 GUID 또는 사용자 정의 형식의 개체와 사용자 정의 형식을 사용 합니다. 이 오류는 인수가 없는 GUID 가진 사용자 정의 형식인 경우 발생 합니다.  
  
 다음 샘플에서는 C2787 오류가 생성 됩니다.  
  
```  
// C2787.cpp  
#include <windows.h>  
struct F {};  
  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;  
  
int main() {  
   __uuidof(F);   // C2787  
   __uuidof(F2);   // OK  
}  
```
