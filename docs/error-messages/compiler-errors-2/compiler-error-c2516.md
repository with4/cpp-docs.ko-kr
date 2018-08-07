---
title: 컴파일러 오류 C2516 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2516
dev_langs:
- C++
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e8a23eda6aa263cdfbf0ef7b4fb777f4158dd06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226514"
---
# <a name="compiler-error-c2516"></a>컴파일러 오류 C2516
'name': 올바른 기본 클래스가 아닙니다.  
  
 에 정의 된 형식 이름에서 파생 된 클래스는 `typedef` 문.  
  
 다음 샘플에서는 C2516 오류가 생성 됩니다.  
  
```  
// C2516.cpp  
typedef unsigned long ulong;  
class C : public ulong {}; // C2516  
```