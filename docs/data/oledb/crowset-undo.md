---
title: 'Crowset:: Undo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.Undo
- ATL::CRowset<TAccessor>::Undo
- CRowset<TAccessor>::Undo
- ATL.CRowset.Undo
- ATL.CRowset<TAccessor>.Undo
- CRowset<TAccessor>.Undo
- ATL::CRowset::Undo
- CRowset::Undo
- Undo
dev_langs: C++
helpviewer_keywords: Undo method
ms.assetid: 1ccd70e2-3931-41c4-893e-a05d0e295410
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d56be5cbaf5f8c3393527c59319cdda4aca124e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetundo"></a>CRowset::Undo
이후 마지막으로 인출 된 행에 대해 변경 내용을 실행 취소 또는 [업데이트](../../data/oledb/crowset-update.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT Undo(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcRows`  
 [out] 위치에 대 한 포인터를 **실행 취소** 필요한 경우 실행 취소 하려고 시도 했습니다. 행의 수를 반환 합니다.  
  
 `phRow`  
 [out] 위치에 대 한 포인터를 **실행 취소** 필요한 경우 실행 취소 하려고 시도 했습니다. 모든 행에 핸들의 배열을 반환 합니다.  
  
 `pStatus`  
 [out] 위치에 대 한 포인터를 **실행 취소** 행 상태 값을 반환 합니다. 상태가 반환 됩니다 `pStatus` null입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하려면 선택적 인터페이스 `IRowsetUpdate`, 모든 공급자에서 지원 되지 않는 있는;의 경우이 메서드는 반환 **E_NOINTERFACE**합니다. 설정 해야 **DBPROP_IRowsetUpdate** 를 `VARIANT_TRUE` 호출 하기 전에 **열려** 테이블이 나 행 집합을 포함 하는 명령입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)