---
title: "심각한 오류 C1026 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1026
dev_langs:
- C++
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 187cfc1a59fc40a721be09aef9e78ef36c68f66a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1026"></a>심각한 오류 C1026
파서 스택 오버플로입니다. 프로그램이 너무 복잡합니다.  
  
 프로그램을 구문 분석 하는 데 필요한 공간 컴파일러 스택 오버플로가 발생 했습니다.  
  
 식의 복잡성을 줄이려면:  
  
-   중첩을 감소 시킵니다 `for` 및 `switch` 문. 별도 함수에서 보다 강력 하 게 중첩된 문을 배치 합니다.  
  
-   쉼표 연산자 또는 함수 호출을 포함 하는 긴 식을 구분 합니다.
