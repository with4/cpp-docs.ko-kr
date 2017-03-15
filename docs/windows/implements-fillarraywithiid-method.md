---
title: "Implements::FillArrayWithIid 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid 메서드"
ms.assetid: b2e62e3f-0ab9-4c70-aad7-856268544f44
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Implements::FillArrayWithIid 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 배열의 요소를 현재 zeroth 템플릿 매개 변수로 지정 된 인터페이스 ID를 삽입 합니다.  
  
## 구문  
  
```  
__forceinline static void FillArrayWithIid(  
   unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### 매개 변수  
 `index`  
 이 작업에 대하여 시작 하는 배열 요소를 나타내는 인덱스입니다.  이 작업이 완료되면 `index` 는 1 씩 증가 합니다.  
  
 `iids`  
 형식 IID의 배열입니다.  
  
## 설명  
 내부 도우미 함수입니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Implements 구조체](../windows/implements-structure.md)