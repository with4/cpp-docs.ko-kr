---
title: "FtmBase::MarshalInterface 메서드 | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::MarshalInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MarshalInterface 메서드"
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::MarshalInterface 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일부 클라이언트 프로세스에서 프록시 개체를 초기화하는 데 필요한 데이터를 스트림으로 씁니다.  
  
## 구문  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
#### 매개 변수  
 `pStm`  
 마샬링을 하는 동안 사용할 스트림에 대한 포인터입니다.  
  
 `riid`  
 마샬링될 인터페이스의 식별자를 참조합니다.  이 인터페이스는 IUnknown 인터페이스에서 파생되어야 합니다.  
  
 `pv`  
 마샬링하기 위한 인터페이스 포인터에 대한 포인터; 호출자가 원하는 인터페이스 포인터가 없는 경우 NULL이 될 수 있습니다.  
  
 `dwDestContext`  
 지정된 인터페이스는 마샬링되지 않은 대상 컨텍스트.  
  
 하나 이상의 MSHCTX 열거형 값을 지정합니다.  
  
 역마샬링은 현재 프로세스 \(MSHCTX\_INPROC\)의 다른 아파트 또는 \(MSHCTX\_LOCAL\)는 현재 프로세스와 같은 컴퓨터의 다른 프로세스에서 발생할 수 있습니다.  
  
 `pvDestContext`  
 나중에 사용하도록 예약되어 있습니다. 0이어야 합니다.  
  
 `mshlflags`  
 마샬링될 데이터는 클라이언트 프로세스에 다시 전송 되는지 여부를 지정\-일반적인 경우\-또는 여러 클라이언트에서 검색할 수 있는 전역 테이블에 기록 합니다.  
  
## 반환 값  
 S\_OK  
 인터페이스 포인터를 성공적으로 마샬링됩니다.  
  
 E\_NOINTERFACE  
 지정한 인터페이스가 지원되지 않습니다.  
  
 STG\_E\_MEDIUMFULL  
 스트림이 꽉 찼습니다.  
  
 E\_FAIL  
 작업이 실패했습니다.  
  
## 요구 사항  
 **헤더:**  ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)