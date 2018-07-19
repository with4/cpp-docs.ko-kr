---
title: 컴파일러 오류 C3747 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3747
dev_langs:
- C++
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ca36074f33299b1a55da0fe7b42786a05dd6c49
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264118"
---
# <a name="compiler-error-c3747"></a>컴파일러 오류 C3747
기본 형식 매개 변수 누락: 매개 변수 param  
  
 제네릭 또는 템플릿 매개 변수 기본값을 사용 하지 않는 매개 변수가가 매개 변수 목록에 나오면 안 합니다.  
  
 다음 샘플에서는 C3747 오류가 생성 됩니다.  
  
```  
// C3747.cpp  
template <class T1 = int, class T2>   // C3747  
struct MyStruct {};  
```  
  
 해결 방법:  
  
```  
// C3747b.cpp  
// compile with: /c  
template <class T1, class T2 = int>  
struct MyStruct {};  
```