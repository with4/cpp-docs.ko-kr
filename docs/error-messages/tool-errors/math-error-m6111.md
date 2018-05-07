---
title: 수학 오류 M6111 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b03937ed442b169b960d573b44c0eb6ebca9660
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6111"></a>수학 오류 M6111
스택 언더플로  
  
 에뮬레이터 또는 8087/287/387 보조 프로세서에 스택 언더플로에서 부동 소수점 연산이 발생 했습니다.  
  
 이 오류는 종종를 호출 하 여 발생 한 `long double` 값을 반환 하지 않는 함수입니다. 예를 들어 다음이 오류가 생성 컴파일하여 실행 하면 됩니다.  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 프로그램은 139 종료 코드로 종료 됩니다.