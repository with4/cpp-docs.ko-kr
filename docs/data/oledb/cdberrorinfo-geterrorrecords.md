---
title: "CDBErrorInfo::GetErrorRecords | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBErrorInfo.GetErrorRecords"
  - "ATL.CDBErrorInfo.GetErrorRecords"
  - "ATL::CDBErrorInfo::GetErrorRecords"
  - "GetErrorRecords"
  - "CDBErrorInfo::GetErrorRecords"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorRecords 메서드"
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDBErrorInfo::GetErrorRecords
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 개체에 대한 오류 레코드를 가져옵니다.  
  
## 구문  
  
```  
  
      HRESULT GetErrorRecords(   
   IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords    
) throw( );  
HRESULT GetErrorRecords(   
   ULONG* pcRecords    
) throw( );  
```  
  
#### 매개 변수  
 *pUnk*  
 \[in\] 인터페이스 오류 레코드를 가져올 개체입니다.  
  
 `iid`  
 \[in\] 오류와 관련 된 인터페이스의 IID입니다.  
  
 *pcRecords*  
 \[out\] 오류 레코드의 수 \(1부터 시작\)에 대한 포인터입니다.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 설명  
 인터페이스에서 오류 정보를 확인 하려는 경우, 함수의 첫 번째 폼을 사용 하십시오.  그렇지 않으면, 두 번째 폼을 사용 합니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)