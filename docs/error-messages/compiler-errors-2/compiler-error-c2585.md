---
title: "컴파일러 오류 C2585 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25df5237d2536f6f74226121cbeceba61a454390
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2585"></a>컴파일러 오류 C2585
'type' 명시적 변환이 모호 합니다.  
  
 형식을 변환 하 여 둘 이상의 결과 생성할 수 있습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  다중 상속 기반 클래스 또는 구조체 형식에서 변환 합니다. 변환 함수 또는 연산자 유형을 동일한 기본 클래스를 두 번 이상 상속 하는 경우 범위 결정 사용 해야 합니다 (`::`) 변환에 사용할를 상속 된 클래스 중 하나로 지정할 수 있습니다.  
  
2.  변환 연산자 및 생성자가 정의 된 동일한 변환을 수행 합니다.