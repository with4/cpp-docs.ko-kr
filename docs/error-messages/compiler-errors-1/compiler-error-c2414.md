---
title: 컴파일러 오류 C2414 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2414
dev_langs:
- C++
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22710e0056a7dea65130a65a3ccb9c5310f1c39f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226165"
---
# <a name="compiler-error-c2414"></a>컴파일러 오류 C2414
피연산자 수가 잘못 되었습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  Opcode 사용 된 피연산자의 수를 지원 하지 않습니다. 피연산자의 정확한 수를 결정 하는 어셈블리 언어 참조 설명서를 확인 합니다.  
  
2.  최신 프로세서는 다른 개수의 피연산자를 사용 하 여 명령을 지원합니다. 조정 된 [/arch (최소 CPU 아키텍처)](../../build/reference/arch-minimum-cpu-architecture.md) 나중에 프로세서를 사용 하는 옵션입니다.