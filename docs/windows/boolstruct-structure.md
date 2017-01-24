---
title: "BoolStruct 구조체 | Microsoft Docs"
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
  - "internal/Microsoft::WRL::Details::BoolStruct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BoolStruct 구조체"
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BoolStruct 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
struct BoolStruct;  
```  
  
## 설명  
 BoolStruct 구조체는 ComPtr 인터페이스 개체의 수명을 관리하고 있는지 여부를 정의 합니다.  BoolStruct에서 내부적으로 사용되는 [BoolType\(\)](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) 연산자입니다.  
  
## 멤버  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[BoolStruct::Member 데이터 멤버](../windows/boolstruct-member-data-member.md)|[ComPtr](../windows/comptr-class.md) 인지 아닌지를 지정하고, 인터페이스의 개체 수명을 관리합니다.|  
  
## 상속 계층  
 `BoolStruct`  
  
## 요구 사항  
 **헤더:**  internal.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType 연산자](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)