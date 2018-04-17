---
title: 컴파일러 경고 (수준 1) C4124 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38588fb242b5b4167984e15d101594d1b015ec86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4124"></a>컴파일러 경고 (수준 1) C4124
__fastcall 스택 검사과 함께 효율적입니다.  
  
 `__fastcall` 스택 검사를 사용할 수 있는 키워드를 사용 했습니다.  
  
 `__fastcall` 규칙 생성 빠른 코드를 생성 하지만 느린 코드 스택 검사는 합니다. 사용 하는 경우 `__fastcall`, 스택 검사 해제는 **check_stack** pragma 또는 /Gs 합니다.  
  
 이 경고는 이러한 조건에서 선언 된 첫 번째 함수에 대해서만 발생 합니다.