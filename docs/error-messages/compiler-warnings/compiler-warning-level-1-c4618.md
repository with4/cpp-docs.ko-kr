---
title: 컴파일러 경고 (수준 1) C4618 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4618
dev_langs:
- C++
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e53f8542983a6e15f353ff181efa280815fea9d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282524"
---
# <a name="compiler-warning-level-1-c4618"></a>컴파일러 경고(수준 1) C4618
pragma 매개 변수 포함 빈 문자열인 경우. pragma가 무시 되었습니다  
  
 Null 문자열에 대 한 인수로 지정 된 한 **#pragma**합니다.  
  
 Pragma는 인수 없이 처리 됩니다.  
  
 다음 샘플에서는 C4618 오류가 생성 됩니다.  
  
```  
// C4618.cpp  
// compile with: /W1 /LD  
#pragma code_seg("")   // C4618  
```