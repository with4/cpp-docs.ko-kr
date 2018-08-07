---
title: 컴파일러 오류 C3895 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3895
dev_langs:
- C++
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69139ed5a1b12d3159ce9fbf3b967cbc27e9264d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268395"
---
# <a name="compiler-error-c3895"></a>컴파일러 오류 C3895
'var': 형식 데이터 멤버 'volatile' 일 수 없습니다  
  
 예를 들어 데이터 멤버의 특정 종류 [리터럴](../../windows/literal-cpp-component-extensions.md) 또는 [initonly](../../dotnet/initonly-cpp-cli.md), 될 수 없습니다 [휘발성](../../cpp/volatile-cpp.md)합니다.  
  
 다음 샘플에서는 C3895 오류가 생성 됩니다.  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```