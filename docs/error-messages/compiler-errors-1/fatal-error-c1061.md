---
title: 심각한 오류 C1061 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1061
dev_langs:
- C++
helpviewer_keywords:
- C1061
ms.assetid: 9366c0bc-96e0-4967-aa7d-4ebf098de806
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fde2d3a076b4cf78a8104fd19719bec205828c68
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225704"
---
# <a name="fatal-error-c1061"></a>심각한 오류 C1061
컴파일러 한계 : 블록이 너무 많이 중첩되었습니다.  
  
 코드 블록의 중첩이 중첩 수준 한계인 128을 초과합니다. 이것은 32비트 및 64비트 도구 집합 모두에서 C 및 C++에 대한 컴파일러의 하드 한계입니다. 중첩 수준의 수는 범위 또는 블록을 만드는 수만큼 늘릴 수 있습니다. 예를 들어 네임스페이스, using 지시문, 전처리기 확장, 템플릿 확장, 예외 처리, 루프 구문 및 else-if 절은 모두 컴파일러로 표시되는 중첩 수준을 높입니다.  
  
 이 오류를 해결하려면 코드를 리팩터링해야 합니다. 어떤 경우든 많이 중첩된 코드는 이해하고 예측하기 어렵습니다. 중첩 수준의 수를 줄이기 위해 코드를 리팩터링하면 코드 품질을 개선하고 유지 관리를 간단하게 할 수 있습니다. 많이 중첩된 코드를 원래 컨텍스트에서 호출된 함수로 나눕니다. 블록 내에서 루프 또는 연결된 else-if 절의 수를 제한합니다.