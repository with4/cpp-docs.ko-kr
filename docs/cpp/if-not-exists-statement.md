---
title: "__if_not_exists 문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__if_not_exists"
  - "__if_not_exists_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_not_exists 키워드[C++]"
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __if_not_exists 문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`__if_not_exists` 문은 지정된 식별자가 있는지 여부를 테스트합니다.  식별자가 없는 경우 지정된 문 블록이 실행됩니다.  
  
## 구문  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`identifier`|존재 여부를 테스트할 식별자입니다.|  
|`statements`|`identifier`가 존재하지 않는 경우 실행할 하나 이상의 문입니다.|  
  
## 설명  
  
> [!CAUTION]
>  가장 안정적인 결과를 얻으려면 다음 제약 조건에서 `__if_not_exists` 문을 사용합니다.  
  
-   템플릿이 아니라 단순 형식에만 `__if_not_exists` 문을 적용합니다.  
  
-   클래스 내부 또는 외부 모두에서 `__if_not_exists` 문을 식별자에 적용합니다.  지역 변수에 `__if_not_exists` 문을 적용하지 마십시오.  
  
-   `__if_not_exists` 문은 함수의 본문에서만 사용합니다.  함수 본문 외부에서 `__if_not_exists` 문은 완전히 정의된 형식만 테스트할 수 있습니다.  
  
-   오버로드된 함수에 대해 테스트할 때 특정 양식의 오버로드를 테스트할 수 없습니다.  
  
 `__if_not_exists` 문에 대한 보수는 [\_\_if\_exists](../cpp/if-exists-statement.md) 문입니다.  
  
## 예제  
 `__if_not_exists`를 사용하는 방법에 대한 예제는 [\_\_if\_exists 문](../cpp/if-exists-statement.md)를 참조하십시오.  
  
## 참고 항목  
 [선택문](../cpp/selection-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [\_\_if\_exists 문](../cpp/if-exists-statement.md)