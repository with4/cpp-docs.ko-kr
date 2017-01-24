---
title: "collate 클래스 | Microsoft Docs"
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
  - "std::collate"
  - "locale/std::collate"
  - "std.collate"
  - "collate"
  - "Collate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collate 클래스"
ms.assetid: 92168798-9628-4a2e-be6e-fa62dcd4d6a6
caps.latest.revision: 18
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# collate 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자열 내 문자의 정렬 및 그룹화, 문자열 간의 비교, 문자열 해싱을 제어하는 로캘 패싯으로 사용할 수 있는 개체를 설명하는 템플릿 클래스입니다.  
  
## 구문  
  
```  
template <class CharType >  
   class collate : public locale::facet;  
```  
  
#### 매개 변수  
 `CharType`  
 문자를 인코딩하기 위해 프로그램 내 사용하는 형식  
  
## 설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다.  처음에 저장된 값에 액세스를 시도하면**id**에 고유한 양수 값이 저장됩니다. 일부 언어에서는 문자가 그룹화되고 단일 문자로 취급되며, 다른 언어에서는 개별 문자가 두 문자인 것처럼 취급됩니다.  collate 클래스에서 제공하는 데이터 정렬 서비스는 이러한 경우를 정렬하는 방법을 제공합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[collate](../Topic/collate::collate.md)|문자열 정렬 규칙을 처리할 로캘 패싯으로 사용할 `collate` 클래스 개체의 생성자입니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[char\_type](../Topic/collate::char_type.md)|`CharType` 형식의 문자를 설명하는 형식입니다.|  
|[string\_type](../Topic/collate::string_type.md)|`CharType` 형식의 문자가 포함된 `basic_string` 형식의 문자열을 설명하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[compare](../Topic/collate::compare.md)|패싯별 규칙에 따라 두 문자 시퀀스의 같음 또는 동등성을 비교합니다.|  
|[do\_compare](../Topic/collate::do_compare.md)|패싯별 규칙에 따라 두 문자 시퀀스를 비교하기 위해 가상 함수를 호출하여 두 문자 시퀀스의 같음 또는 동등성을 비교합니다.|  
|[do\_hash](../Topic/collate::do_hash.md)|패싯별 규칙에 따라 시퀀스의 해시 값을 확인하기 위해 가상 함수를 호출합니다.|  
|[do\_transform](../Topic/collate::do_transform.md)|가상 함수를 호출하여 문자 시퀀스를 로캘에서 문자열로 변환하고 동일한 로캘에서 유사한 방식으로 변환된 다른 문자 시퀀스와 사전순으로 비교하는 데 사용합니다.|  
|[hash](../Topic/collate::hash.md)|패싯별 규칙에 따라 시퀀스의 해시 값을 확인합니다.|  
|[변환\(Transform\)](../Topic/collate::transform.md)|문자 시퀀스를 로캘에서 문자열로 변환하고 동일한 로캘에서 유사한 방식으로 변환된 다른 문자 시퀀스와 사전순으로 비교하는 데 사용합니다.|  
  
## 요구 사항  
 **헤더:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<locale\>](../standard-library/locale.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)