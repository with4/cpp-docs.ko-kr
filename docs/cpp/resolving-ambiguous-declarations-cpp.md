---
title: 모호한 선언 (c + +)를 확인 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70c010cf3806581c6b77bb508f3adb68e3c230f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="resolving-ambiguous-declarations-c"></a>모호한 선언 (c + +)를 확인합니다.
한 형식에서 다른 한 형식으로의 명시적 변환을 수행하려면 원하는 형식 이름을 지정하여 캐스팅을 사용해야 합니다. 일부 형식 캐스팅 결과 구문이 모호해집니다. 다음 함수 스타일 형식 캐스팅이 모호합니다.  
  
```  
char *aName( String( s ) );  
```  
  
 함수 선언 또는 함수 스타일 이니셜라이저가로 캐스팅을 사용 하는 개체 선언을 인지 명확 하지 않습니다: 형식을 반환 하는 함수를 선언할 수 **char \***  형식의 인수 하나를 사용 하는 `String` 또는 개체를 선언할 수 `aName` 의 값으로 초기화 하 고 `s` 형식으로 캐스팅 `String`합니다.  
  
 선언이 올바른 함수 선언으로 간주될 수 있는 경우 해당 선언이 이와 같이 처리됩니다. 해당 선언이 함수 선인일 수 없는 경우에만, 즉 구문상으로 잘못된 경우 함수 스타일 형식 캐스트인지 여부를 확인하기 위해 문이 검사됩니다. 따라서 컴파일러는 문을 함수의 선언으로 간주하고 `s` 식별자 주위의 괄호를 무시합니다. 반면 다음  
  
```  
char *aName( (String)s );  
```  
  
 를 갖는  
  
```  
char *aName = String( s );  
```  
  
 분명히 개체 및 형식에서 사용자 정의 변환의 선언 `String` 입력 **char \***  의 초기화를 수행 하기 위해 호출 된 `aName`합니다.  
  
## <a name="see-also"></a>참고 항목  
 