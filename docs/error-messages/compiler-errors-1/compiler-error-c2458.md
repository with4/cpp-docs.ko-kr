---
title: 컴파일러 오류 C2458 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2458
dev_langs:
- C++
helpviewer_keywords:
- C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0822c12e109cd5a89a8e1050197367b12a24efa9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196768"
---
# <a name="compiler-error-c2458"></a>컴파일러 오류 C2458
'identifier': 정의 내에 재정의가  
  
 클래스, 구조체, 공용 구조체 또는 열거형 자체 선언에서 다시 정의 됩니다.  
  
 다음 샘플에서는 C2458 오류가 생성 됩니다.  
  
```  
// C2458.cpp  
class C {  
   enum i { C };   // C2458  
};  
```