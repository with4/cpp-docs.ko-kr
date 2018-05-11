---
title: 컴파일러 오류 C2778 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2778
dev_langs:
- C++
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f8747c0f2d0434f034ac0a0b84dcce510de0e96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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