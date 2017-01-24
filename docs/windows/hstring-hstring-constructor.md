---
title: "HString::HString 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::HString"
dev_langs: 
  - "C++"
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::HString 생성자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HString 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### 매개 변수  
 `hstr`  
 HSTRING 핸들  
  
 `other`  
 기존 HString 개체  
  
## 설명  
 첫 번째 생성자는 비어 있는 새 HString 개체를 초기화 합니다.  
  
 두 번째 생성자는 새 HString 개체의 기존 값을 `other` 매개 변수를 삭제 한 다음의 `other` 매개 변수를 초기화 합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HString 클래스](../windows/hstring-class.md)