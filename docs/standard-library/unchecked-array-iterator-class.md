---
title: "unchecked_array_iterator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unchecked_array_iterator"
  - "stdext::unchecked_array_iterator"
dev_langs: 
  - "C++"
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unchecked_array_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`unchecked_array_iterator` 클래스를 사용하여 확인되지 않은 반복기에 배열 또는 포인터를 래핑할 수 있습니다  이러한 경고를 전역적으로 해제하는 대신 이 클래스를 원시 포인터 또는 배열에 대한 래퍼로 목적에 따라 사용하여\([make\_unchecked\_array\_iterator](../Topic/make_unchecked_array_iterator.md) 함수 사용\) 확인되지 않은 포인터 경고를 관리합니다.  가능한 경우 이 클래스의 확인된 버전 [checked\_array\_iterator](../standard-library/checked-array-iterator-class.md)를 선택합니다.  
  
> [!NOTE]
>  이 클래스는 표준 C\+\+ 라이브러리의 Microsoft 확장입니다.  이 함수를 사용하여 구현한 코드는 이 Microsoft 확장을 지원하지 않는 C\+\+ 표준 빌드 환경으로 이식할 수 없습니다.  
  
## 구문  
  
```  
template <class Iterator>  
    class unchecked_array_iterator;  
```  
  
## 설명  
 이 클래스는 [stdext](../standard-library/stdext-namespace.md) 네임스페이스에 정의됩니다.  
  
 [checked\_array\_iterator 클래스](../standard-library/checked-array-iterator-class.md)의 확인되지 않은 버전이므로 동일한 오버로드와 멤버를 모두 지원합니다.  확인된 반복기 기능에 대한 자세한 내용 및 코드 예제는 [Checked Iterators](../standard-library/checked-iterators.md)를 참조하십시오.  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<iterator\>](../standard-library/iterator.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)