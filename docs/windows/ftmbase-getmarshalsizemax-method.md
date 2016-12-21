---
title: "FtmBase::GetMarshalSizeMax 메서드 | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMarshalSizeMax 메서드"
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::GetMarshalSizeMax 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 된 개체에서 지정된 인터페이스 포인터를 마샬링하는 데 필요한 바이트의 수에 상한을 가져옵니다.  
  
## 구문  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
#### 매개 변수  
 `riid`  
 마샬링될 인터페이스의 식별자를 참조합니다.  
  
 `pv`  
 인터페이스 포인터를 마샬링할 수 있습니다. NULL이 될 수 있습니다.  
  
 `dwDestContext`  
 지정된 인터페이스는 마샬링되지 않은 대상 컨텍스트.  
  
 하나 이상의 MSHCTX 열거형 값을 지정합니다.  
  
 현재 역마샬링은 현재 프로세스 \(MSHCTX\_INPROC\)의 다른 아파트 또는 \(MSHCTX\_LOCAL\)는 현재 프로세스와 같은 컴퓨터의 다른 프로세스에서 발생할 수 있습니다.  
  
 `pvDestContext`  
 나중에 사용하도록 예약되어 있습니다. NULL이어야 합니다.  
  
 `mshlflags`  
 마샬링될 데이터는 클라이언트 프로세스에 다시 전송되는지 여부를 플래그로 나타냅니다.\-일반적인 경우\-또는 여러 클라이언트에서 검색할 수 있는 전역 테이블에 기록 합니다.  하나 이상의 MSHLFLAGS 열거형 값을 지정합니다.  
  
 `pSize`  
 이 작업 완료시, 마샬링 스트림에 쓸 데이터 양 상한에 대한 포인터입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면, E\_NOINTERFACE 또는 E\_FAIL  
  
## 요구 사항  
 **헤더:**  ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)