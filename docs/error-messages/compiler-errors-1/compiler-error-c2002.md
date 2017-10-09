---
title: "컴파일러 오류 C2002 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d8f6fc5983a462850581f69ca32dd7c305f9e847
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2002"></a>컴파일러 오류 C2002
잘못 된 와이드 문자 상수  
  
 멀티 바이트 문자 상수 올바르지 않습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  와이드 문자 상수는 예상 보다 더 많은 바이트를 포함 합니다.  
  
2.  표준 헤더 STDDEF.h 포함 되지 않습니다.  
  
3.  와이드 문자는 일반 문자열 리터럴을 연결할 수 없습니다.  
  
4.  와이드 문자 상수 뒤에 야 문자 'L':  
  
    ```  
    L'mbconst'  
    ```  
  
5.  전처리기 지시문의 텍스트 인수는 Microsoft c + +에서는 ASCII 이어야 합니다. 예를 들어 지시문 `#pragma message(L"string")`, 사용할 수 없습니다.
