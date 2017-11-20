---
title: "2.6.2 critical 구문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 13e9b4a8611732c7dddb81be1ca6123b725f7169
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="262-critical-construct"></a>2.6.2 critical 구문
**중요** 지시문 식별 한 번에 스레드 하나에 연결된 된 구조화 된 블록의 실행을 제한 하는 구문입니다. 구문은 **중요** 지시문은 다음과 같습니다.  
  
```  
#pragma omp critical [(name)]  new-linestructured-block  
```  
  
 선택적 *이름* 중요 영역을 식별 하는 데 사용 될 수 있습니다. 중요 한 영역을 식별 하는 데 사용 하는 식별자에는 외부 링크가 레이블, 태그, 멤버 및 일반 식별자에서 사용 하는 네임 스페이스와에서 구분 됨 네임 스페이스에 있습니다.  
  
 스레드가 다른 스레드에서 같은 이름의 중요 영역 (아무 곳 이나 프로그램)에서 실행 될 때까지 임계 영역의 시작 부분에서 대기 합니다. 모든 명명 되지 않은 **중요** 지시문 지정 되지 않은 동일한 이름에 매핑됩니다.