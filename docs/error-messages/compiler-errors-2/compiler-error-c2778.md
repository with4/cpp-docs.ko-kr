---
title: "컴파일러 오류 C2778 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2778
dev_langs:
- C++
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d3801f7ddef23f90a76007a09fdc7a2d552b7fdb
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2778"></a>컴파일러 오류 C2778
__declspec(uuid())에 잘못 된 형식의 GUID  
  
 잘못 된 GUID에 제공 되는 [uuid](../../cpp/uuid-cpp.md) 확장된 특성입니다.  
  
 GUID에는 다음과 같은 형식의 16 진수 숫자의 문자열 이어야 합니다.  
  
```  
// C2778a.cpp  
// compile with: /c  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};  
```  
  
 `uuid` 에서 인식 하는 문자열을 허용 하는 확장 된 특성 [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589), 하거나 사용 하지 않고 중괄호로 구분 기호입니다.  
  
 다음 샘플에서는 C2778 오류가 생성 됩니다.  
  
```  
// C2778b.cpp  
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778  
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778  
```
