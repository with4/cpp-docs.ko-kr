---
title: "NMAKE 심각한 오류 U1099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8bf8d662960e5857686f3f8301cc8481f350d4b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE 심각한 오류 U1099
스택 오버플로  
  
 처리 중인 메이크파일이 NMAKE에서 현재 스택 할당에는 너무 복잡 합니다. NMAKE는 0x3000 (12 K)의 할당을 있습니다.  
  
 NMAKE의 스택 할당을 늘리려면 실행는 [/stack editbin](../../build/reference/stack.md) 유틸리티를 더 큰 스택 옵션:  
  
 **NMAKE /STACK:reserve editbin 합니다. EXE**  
  
 여기서 *예약* 숫자 NMAKE에서 현재 스택 할당 보다 큽니다.