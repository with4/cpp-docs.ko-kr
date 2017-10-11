---
title: "부동 소수점 값 언더플로 | Microsoft Docs"
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
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: f74624f935c9a1384c1c4992004b12c7847e9fd2
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="underflow-of-floating-point-values"></a>부동 소수점 값 언더플로
**ANSI 4.5.1** 수학 함수가 정수 식 `errno`를 언더플로 범위 오류에 대한 `ERANGE` 매크로의 값으로 설정하는지 여부  
  
 부동 소수점 언더플로는 `errno` 식을 `ERANGE`로 설정하지 않습니다. 값이 0이고 결국 언더플로로 가까워지면 값이 0으로 설정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)
