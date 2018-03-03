---
title: "수학 오류 M6111 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 204df0df4855fd2628a96ac326dd39c0d65151e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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