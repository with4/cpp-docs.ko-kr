---
title: 심각한 오류 C1021 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1021
dev_langs:
- C++
helpviewer_keywords:
- C1021
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06ec8f9aeca3b88b1c14c8dddfc625aae0b185d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1021"></a>심각한 오류 C1021
'string' 전처리기 명령이 잘못되었습니다.  
  
 `string` 은 유효하지 않은 [전처리기 지시문](../../preprocessor/preprocessor-directives.md)입니다. 오류를 해결하려면 `string`에 대해 올바른 전처리기 이름을 사용합니다.  
  
 다음 샘플에서는 C1021을 생성합니다.  
  
```  
// C1021.cpp  
#BadPreProcName    // C1021 delete line  
```