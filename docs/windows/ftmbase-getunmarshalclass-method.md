---
title: "FtmBase::GetUnmarshalClass 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetUnmarshalClass 메서드"
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::GetUnmarshalClass 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM 해당 프록시에 대한 코드를 포함하는 DLL을 찾기 위해 사용하는 CLSID를 가져옵니다.  COM 프록시의 초기화되지 않은 인스턴스를 만들고, 이 DLL을 로드 합니다.  
  
## 구문  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### 매개 변수  
 `riid`  
 마샬링될 인터페이스의 식별자를 참조합니다.  
  
 `pv`  
 마샬링하기 위한 인터페이스에 대한 포인터; 호출자가 원하는 인터페이스 포인터가 없는 경우 NULL이 될 수 있습니다.  
  
 `dwDestContext`  
 지정된 인터페이스는 마샬링되지 않은 대상 컨텍스트.  
  
 하나 이상의 MSHCTX 열거형 값을 지정합니다.  
  
 역마샬링은 현재 프로세스 \(MSHCTX\_INPROC\)의 다른 아파트 또는 \(MSHCTX\_LOCAL\)는 현재 프로세스와 같은 컴퓨터의 다른 프로세스에서 발생할 수 있습니다.  
  
 `pvDestContext`  
 나중에 사용하도록 예약되어 있습니다. NULL이어야 합니다.  
  
 `mshlflags`  
 이 작업이 완료될 때 클라이언트 프로세스에서 프록시를 만드는 데 사용할 수 있는 CLSID에 대한 포인터입니다.  
  
 `pCid`  
  
## 반환 값  
 삽입할 수 있으면 S\_OK 이고 그렇지 않으면 S\_FALUSE입니다.  
  
## 요구 사항  
 **헤더:**  ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)