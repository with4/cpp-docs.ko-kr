---
title: "식 계산 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 21b78b659b4d4cd8f3bb5db849b3c64a5f66f971
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="expression-evaluation-c"></a>식 계산 (C)
할당, 단항 증가, 단항 감소 또는 함수 호출을 포함하는 식의 계산에 따른 결과(의도하지 않은 결과)가 생길 수 있습니다. "시퀀스 위치"에 도달하면 시퀀스 위치 뒤에 오는 모든 항목을 계산하기 전에 의도하지 않은 결과를 포함하여 시퀀스 위치 앞에 오는 모든 항목이 평가됩니다.  
  
 "의도하지 않은 결과"는 식을 계산하여 생기는 변경 내용입니다. 식을 계산하여 변수 값이 변경될 때마다 의도하지 않은 결과가 생깁니다. 모든 할당 연산에는 의도하지 않은 결과가 따릅니다. 외부에 표시되는 항목의 값을 변경할 경우 직접 할당에 의해 또는 포인터를 통한 간접 할당에 의해 함수 호출에 의도하지 않은 결과가 생길 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [피연산자 및 식](../c-language/operands-and-expressions.md)
