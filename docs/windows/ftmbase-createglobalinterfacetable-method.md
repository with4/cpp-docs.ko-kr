---
title: "FtmBase::CreateGlobalInterfaceTable 메서드 | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateGlobalInterfaceTable 메서드"
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::CreateGlobalInterfaceTable 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

전역 인터페이스 테이블 \(GIT\)를 만듭니다.  
  
## 구문  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
#### 매개 변수  
 `git`  
 이 작업 완료 시 전역 인터페이스 테이블에 대한 포인터입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 설명  
 자세한 내용은 MSDN Library에서 "COM 참조" 항목의 "COM 인터페이스" 하위의 "IGlobalInterfaceTable" 항목을 참조 하십시오.  
  
## 요구 사항  
 **헤더:**  ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)