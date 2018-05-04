---
title: 부동 소수점 보조 프로세서 및 호출 규칙 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46cf9c937453894ed37ad434ad94609d0744be24
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>부동 소수점 보조 프로세서 및 호출 규칙
부동 유지 해야 하는 경우를 작성 하는 어셈블리 루틴은 부동 소수점 보조 프로세서 반환 하지 않으면 보조 프로세서 스택을 정리 하 고 소수점 제어 단어는 **float** 또는 **double** 값 (함수가 st (0)에서 반환 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [호출 규칙](../cpp/calling-conventions.md)