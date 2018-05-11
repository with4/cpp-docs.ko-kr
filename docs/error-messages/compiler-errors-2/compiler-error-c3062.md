---
title: 컴파일러 오류 C3062 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3062
dev_langs:
- C++
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da507511cb5f091d5d9432bbfeb36951e3f43c6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3062"></a>컴파일러 오류 C3062
'enum': 열거자 값이 필요 하므로 내부 형식이 'type'  
  
 열거형에는 내부 형식을 지정할 수 있습니다. 그러나 일부 형식에 각 열거자에 값을 할당 해야 합니다.  
  
 열거형에 대 한 자세한 내용은 참조 하십시오. [enum 클래스](../../windows/enum-class-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3062 오류가 생성 됩니다.  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```