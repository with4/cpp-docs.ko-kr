---
title: "모호성 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 모호성 해결
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

한 형식에서 다른 한 형식으로의 명시적 변환을 수행하려면 원하는 형식 이름을 지정하여 캐스팅을 사용해야 합니다.  일부 형식 캐스팅 결과 구문이 모호해집니다.  다음 함수 스타일 형식 캐스팅이 모호합니다.  
  
```  
char *aName( String( s ) );  
```  
  
 이는 함수 선언인지, 아니면 함수 스타일 캐스트가 이니셜라이저인 개체 선언인지 여부가 명확하지 않습니다. 형식이 `String`인 인수를 하나만 사용하는 형식 **char \***를 반환하는 함수를 선언하거나 `aName` 개체를 선언하고 해당 개체를 `String` 형식으로 캐스팅되는 `s` 값으로 초기화할 수 있습니다.  
  
 선언이 올바른 함수 선언으로 간주될 수 있는 경우 해당 선언이 이와 같이 처리됩니다.  해당 선언이 함수 선인일 수 없는 경우에만, 즉 구문상으로 잘못된 경우 함수 스타일 형식 캐스트인지 여부를 확인하기 위해 문이 검사됩니다.  따라서 컴파일러는 문을 함수의 선언으로 간주하고 `s` 식별자 주위의 괄호를 무시합니다.  반면 다음  
  
```  
char *aName( (String)s );  
```  
  
 및  
  
```  
char *aName = String( s );  
```  
  
 문은 분명히 개체의 선언이며 `String` 형식에서 **char \*** 형식으로의 사용자 정의 변환이 호출되어 `aName`의 초기화를 수행합니다.  
  
## 참고 항목  
 [C\+\+ Abstract Declarators](http://msdn.microsoft.com/ko-kr/e7e18c18-0cad-4450-942b-d27e1d4dd088)