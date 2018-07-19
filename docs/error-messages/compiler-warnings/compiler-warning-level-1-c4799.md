---
title: 컴파일러 경고 (수준 1) C4799 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f888d6a941ad487ce122e46c43582e1c96525c70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282940"
---
# <a name="compiler-warning-level-1-c4799"></a>컴파일러 경고(수준 1) C4799  
  
> 함수의 끝에 EMMS 없음 '*함수*'  
  
함수에 MMX 명령이 하나 이상 있지만 없는 `EMMS` 명령입니다. 멀티미디어 명령을 사용 하는 경우는 `EMMS` 명령 또는 `_mm_empty` 내장 또한 사용 해야 MMX 코드의 끝에 멀티미디어 태그 단어의 선택을 취소 합니다.  
  
반환 하기 전에 EMMS 명령이 실행 코드에서 제대로 사용 하지 않음을 나타내는 않아 C4799 발생할 수 있습니다. 이러한 헤더에 대해 false 경고입니다. 해제할 수 있습니다 이러한 _SILENCE_IVEC_C4799 않아에서 정의 하 여 합니다. 그러나이 또한 유지 하는 컴파일러 제공 되는이 형식의 올바른 경고 유의 합니다.  
  
관련된 정보를 참조 하십시오. [Intel의 MMX 명령 집합](../../assembler/inline/intel-s-mmx-instruction-set.md)합니다.