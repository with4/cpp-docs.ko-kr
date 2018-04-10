---
title: 유추 규칙의 우선 순위 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7374da0541fc66464947af5a7b2ea7ea7b5c1d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-inference-rules"></a>유추 규칙의 우선 순위
NMAKE 유추 규칙 정의 된 경우 곱하기, 우선 순위가 가장 높은 정의 사용 합니다. 다음 목록은 내림차순으로 최고 우선 순위를 나타냅니다.  
  
1.  메이크파일;에 정의 된 유추 규칙 이후 정의 우선 순위를 가집니다.  
  
2.  Tools.ini;에 정의 된 유추 규칙 이후 정의 우선 순위를 가집니다.  
  
3.  미리 정의 된 규칙입니다.  
  
## <a name="see-also"></a>참고 항목  
 [유추 규칙](../build/inference-rules.md)