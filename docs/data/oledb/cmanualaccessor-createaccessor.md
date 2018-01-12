---
title: 'Cmanualaccessor:: Createaccessor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
dev_langs: C++
helpviewer_keywords: CreateAccessor method
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f313e6d2b13a03a91295c75d52e4e77d5dfda22b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmanualaccessorcreateaccessor"></a>CManualAccessor::CreateAccessor
Bind 구조 열에 대 한 메모리를 할당 하 고 열 데이터 멤버를 초기화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT CreateAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nBindEntries`  
 [in] 열의 수입니다. 이 수에 대 한 호출의 수와 일치 해야는 [cmanualaccessor:: Addbindentry](../../data/oledb/cmanualaccessor-addbindentry.md) 함수입니다.  
  
 `pBuffer`  
 [in] 출력 열에는 저장 되는 버퍼에 대 한 포인터입니다.  
  
 `nBufferSize`  
 [in] 버퍼의 바이트의 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
## <a name="remarks"></a>설명  
 이 함수를 호출 하기 전에 호출 된 `CManualAccessor::AddBindEntry` 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer 샘플](../../visual-cpp-samples.md)