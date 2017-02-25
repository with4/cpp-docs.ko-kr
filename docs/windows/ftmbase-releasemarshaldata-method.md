---
title: "FtmBase::ReleaseMarshalData 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseMarshalData 메서드"
ms.assetid: a94f9940-183a-4fde-8504-d223f346a0a9
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::ReleaseMarshalData 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

마샬링된 데이터 패킷을 소멸시킵니다.  
  
## 구문  
  
```  
STDMETHODIMP ReleaseMarshalData(  
   __in IStream *pStm  
) override;  
```  
  
#### 매개 변수  
 `pStm`  
 제거할 데이터 패킷에 포함된 스트림에 대한 포인터입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:**  ftm.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [FtmBase 클래스](../windows/ftmbase-class.md)