---
title: "문법 요약 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 755533d59b9b893da4a657db6da2ea80f13138b5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="definitions-for-the-grammar-summary"></a>문법 요약 정의
구문 정의에서 단말은 끝점입니다. 다른 확인은 가능하지 않습니다. 단말에는 예약어와 사용자 정의 식별자의 집합이 포함됩니다.  
  
비단말은 구문에서 자리 표시자입니다. 대부분 이 구문 요약의 다른 곳에서 정의되어 있습니다. 정의는 재귀적일 수 있습니다. 다음 비 단말에 정의 된는 [어휘 규칙](../cpp/lexical-conventions.md) 의 섹션은 *c + + 언어 참조*:  
  
`constant`, *constant-expression*, *identifier*, *keyword*, `operator`, `punctuator`  
  
선택적 구성 요소는 첨자 opt로 나타냅니다. 예를 들어 다음은 중괄호로 묶인 선택적 식을 나타냅니다.  
  
**{** *expression*opt **}**  
  
## <a name="see-also"></a>참고 항목  
[문법 요약(C/C++)](../preprocessor/grammar-summary-c-cpp.md)