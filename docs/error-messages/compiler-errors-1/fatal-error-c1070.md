---
title: 심각한 오류 C1070 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1070
dev_langs:
- C++
helpviewer_keywords:
- C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99650b93819c4bc0192d612b0f1344e1b99671d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228181"
---
# <a name="fatal-error-c1070"></a>심각한 오류 C1070
'filename' 파일에서 #if/#endif 쌍이 짝이 맞지 않습니다.  
  
 `#if`, `#ifdef`또는 `#ifndef` 지시문에 해당하는 `#endif`가 없습니다.  
  
 다음 샘플에서는 C1070을 생성합니다.  
  
```  
// C1070.cpp  
#define TEST  
  
#ifdef TEST  
  
#ifdef TEST  
#endif  
// C1070  
```  
  
 해결 방법:  
  
```  
// C1070b.cpp  
// compile with: /c  
#define TEST  
  
#ifdef TEST  
#endif  
  
#ifdef TEST  
#endif  
```