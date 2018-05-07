---
title: NMAKE 심각한 오류 U1099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7be09691de4212d07b1452ffe33725a3978fc053
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE 심각한 오류 U1099
스택 오버플로  
  
 처리 중인 메이크파일이 NMAKE에서 현재 스택 할당에는 너무 복잡 합니다. NMAKE는 0x3000 (12 K)의 할당을 있습니다.  
  
 NMAKE의 스택 할당을 늘리려면 실행는 [/stack editbin](../../build/reference/stack.md) 유틸리티를 더 큰 스택 옵션:  
  
 **NMAKE /STACK:reserve editbin 합니다. EXE**  
  
 여기서 *예약* 숫자 NMAKE에서 현재 스택 할당 보다 큽니다.