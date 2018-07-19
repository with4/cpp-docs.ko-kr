---
title: 컴파일러 경고 (수준 1) C4788 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19a43fb9d79c63637b2bff9a27661a9f848ef6dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284201"
---
# <a name="compiler-warning-level-1-c4788"></a>컴파일러 경고(수준 1) C4788
'identifier': 식별자 'number' 자로 잘렸습니다.  
  
 컴파일러는 함수 이름에 허용 된 최대 길이 제한 합니다. 앞에서 함수 이름을 일부 텍스트를 추가 하 여 작은 함수 이름을 형성 컴파일러 funclets EH/SEH 코드를 생성할 때 "__catch를 선택 예를 들어", "\__unwind", 또는 다른 문자열입니다.  
  
 결과 funclet 이름이 너무 길거나, 될 수 있으며는 컴파일러에서 잘라 고 c4788.  
  
 이 경고를 해결 하려면 원래 함수 이름을 줄이십시오. 함수가 c + + 템플릿 함수 또는 메서드의 경우 이름의 일부에 대 한 형식 정의 사용 합니다. 예를 들어:  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 으로 바꿀 수 있습니다.  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 이 경고는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴파일러에서만 발생합니다.