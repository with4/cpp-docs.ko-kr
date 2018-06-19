---
title: 컴파일러 경고 (수준 4) C4960 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4960
dev_langs:
- C++
helpviewer_keywords:
- C4960
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1281bc86ad363c02df5c39ed41f616a6fff1a9b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294429"
---
# <a name="compiler-warning-level-4-c4960"></a>컴파일러 경고(수준 4) C4960
'function'이 너무 커서 프로파일링할 수 없습니다.  
  
 [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)를 사용하는 경우 컴파일러에서 65,535개 명령보다 큰 함수를 포함하는 입력 모듈을 발견했습니다. 이렇게 큰 함수는 프로필 기반 최적화에 사용할 수 없습니다.  
  
 이 경고를 해결하려면 함수 크기를 줄입니다.