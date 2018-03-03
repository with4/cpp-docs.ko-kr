---
title: "컴파일러 경고 (수준 1) C4788 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e6f876dada851f46b7708ef1b34da4bae6f96dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4788"></a>컴파일러 경고(수준 1) C4788
'identifier': 식별자 'number' 자로 잘렸습니다.  
  
 컴파일러는 함수 이름에 허용 된 최대 길이 제한 합니다. 앞에서 함수 이름을 일부 텍스트를 추가 하 여 작은 함수 이름을 형성 컴파일러 funclets EH/SEH 코드를 생성할 때 "__catch를 선택 예를 들어", "\__unwind", 또는 다른 문자열입니다.  
  
 결과 funclet 이름이 너무 길거나, 될 수 있으며는 컴파일러에서 잘라 고 c4788.  
  
 이 경고를 해결 하려면 원래 함수 이름을 줄이십시오. 함수가 c + + 템플릿 함수 또는 메서드의 경우 이름의 일부에 대 한 형식 정의 사용 합니다. 예:  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 으로 바꿀 수 있습니다.  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 이 경고는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴파일러에서만 발생합니다.