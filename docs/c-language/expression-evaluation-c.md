---
title: 식 계산 (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c250cba9e26d82ba129a842b61006783d13f6e3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382730"
---
# <a name="expression-evaluation-c"></a>식 계산 (C)
할당, 단항 증가, 단항 감소 또는 함수 호출을 포함하는 식의 계산에 따른 결과(의도하지 않은 결과)가 생길 수 있습니다. "시퀀스 위치"에 도달하면 시퀀스 위치 뒤에 오는 모든 항목을 계산하기 전에 의도하지 않은 결과를 포함하여 시퀀스 위치 앞에 오는 모든 항목이 평가됩니다.  
  
 "의도하지 않은 결과"는 식을 계산하여 생기는 변경 내용입니다. 식을 계산하여 변수 값이 변경될 때마다 의도하지 않은 결과가 생깁니다. 모든 할당 연산에는 의도하지 않은 결과가 따릅니다. 외부에 표시되는 항목의 값을 변경할 경우 직접 할당에 의해 또는 포인터를 통한 간접 할당에 의해 함수 호출에 의도하지 않은 결과가 생길 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [피연산자 및 식](../c-language/operands-and-expressions.md)