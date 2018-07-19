---
title: 컴파일러 오류 C3385 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3385
dev_langs:
- C++
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1949e2836c6677f6aec2597743142b6f7e87cf5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248775"
---
# <a name="compiler-error-c3385"></a>컴파일러 오류 C3385
'class::function': DllImport 사용자 지정 특성을 가진 함수는 클래스의 인스턴스를 반환할 수 없습니다.  
  
 `DllImport` 특성으로 지정된 .dll 파일에 있는 것으로 정의된 함수는 클래스의 인스턴스를 반환할 수 없습니다.  
  
 다음 샘플에서는 C3385를 생성합니다.  
  
```  
// C3385.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
struct SomeStruct1 {};  
  
public ref struct Wrap {  
   [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ]  
   static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385  
};  
```  
