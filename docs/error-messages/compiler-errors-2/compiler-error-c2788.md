---
title: 컴파일러 오류 C2788 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2788
dev_langs:
- C++
helpviewer_keywords:
- C2788
ms.assetid: 8688fc5c-e652-43b4-b407-9c488c76f2db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd6843eb1f1fba77cc272361dc3dc7c688789b12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2788"></a>컴파일러 오류 C2788
'identifier':이 개체와 관련 된 둘 이상의 GUID  
  
 [__uuidof](../../cpp/uuidof-operator.md) 연산자는 연결 된 GUID 또는 사용자 정의 형식의 개체와 사용자 정의 형식을 사용 합니다. 이 오류는 인수가 개체가 여러 Guid 포함 하는 경우에 발생 합니다.  
  
 다음 샘플에서는 C2788 오류가 생성 됩니다.  
  
```  
// C2788.cpp  
#include <windows.h>  
struct __declspec(uuid("00000001-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000002-0000-0000-0000-000000000000}")) B {};  
template <class T, class U> class MyClass {};  
  
typedef MyClass<A,B> MyBadClass;  
typedef MyClass<A,A> MyGoodClass;  
  
int main() {  
   __uuidof(MyBadClass);    // C2788  
   // try the following line instead  
   __uuidof(MyGoodClass);  
}  
```