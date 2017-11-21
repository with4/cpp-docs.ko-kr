---
title: "식 계산기 오류 CXX0019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0019
dev_langs: C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67fbd43280ad6ffcecdf0532819cd80a0d44b479
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0019"></a>식 계산기 오류 CXX0019
잘못 된 형식 캐스팅  
  
 C 식 계산기는 작성 된 대로 형식 변환을 수행할 수 없습니다.  
  
 이 오류는 can0019와 동일 합니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  지정된 된 형식의 알려져 있습니다.  
  
2.  너무 많은 수준의 포인터 형식 발생 했습니다. 예를 들어, 유형 변환  
  
    ```  
    (char **)h_message  
    ```  
  
     C 식 계산기가 평가할 수 없습니다.