---
title: "FtmBase::DisconnectObject 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::DisconnectObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DisconnectObject 메서드"
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::DisconnectObject 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

개체에 대한 모든 외부 연결을 강제로 해제합니다.  개체의 서버 개체의 구현을 종료하기 전에, 이 메서드를 호출 합니다.  
  
## 구문  
  
```  
STDMETHODIMP DisconnectObject(  
   __in DWORD dwReserved  
) override;  
```  
  
#### 매개 변수  
 `dwReserved`  
 나중에 사용하도록 예약되어 있습니다. 0이어야 합니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:**  ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)