---
title: "FtmBase::UnmarshalInterface 메서드 | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::UnmarshalInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnmarshalInterface 메서드"
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::UnmarshalInterface 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

새로 생성된 프록시를 초기화하고 해당 프록시에 대한 인터페이스 포인터를 반환합니다.  
  
## 구문  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### 매개 변수  
 `pStm`  
 인터페이스 포인터는 마샬링되지 않는 스트림에 대한 포인터입니다.  
  
 `riid`  
 마샬링되지 않는 인터페이스의 식별자를 참조합니다.  
  
 `ppv`  
 이 작업이 완료되면, 요청된 인터페이스 포인터를 받을 포인터 변수의 주소 `riid`입니다.  이 작업이 성공할 경우, `ppv` 는 마샬링되지 않은 인터페이스의 요청되 인터페이스 포인터를 포함합니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면, 지원 또는 E\_FAIL  
  
## 요구 사항  
 **헤더:**  ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)