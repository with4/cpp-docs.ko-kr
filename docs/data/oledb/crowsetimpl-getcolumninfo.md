---
title: 'Crowsetimpl:: Getcolumninfo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a989b31d672c9019d2ed5e61490f4e0042ab4c47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetimplgetcolumninfo"></a>CRowsetImpl::GetColumnInfo
특정 클라이언트 요청에 대 한 열 정보를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,  
   ULONG* pcCols);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pv`  
 [in] 사용자에 대 한 포인터 `CRowsetImpl` 클래스를 파생 합니다.  
  
 `pcCols`  
 [in] 한 포인터 (출력) 수를 반환 하는 열입니다.  
  
## <a name="return-value"></a>반환 값  
 정적에 대 한 포인터 **ATLCOLUMNINFO** 구조입니다.  
  
## <a name="remarks"></a>설명  
 이 방법은 고급 재정의 합니다.  
  
 이 메서드는 특정 클라이언트 요청에 대 한 열 정보를 검색 하는 몇 가지 기본 구현 클래스에서 호출 됩니다. 이 메서드를 호출 하는는 일반적으로 `IColumnsInfoImpl`합니다. 이 메서드를 재정의 하는 경우에에서 메서드의 버전을 저장 해야 합니다 프로그램 `CRowsetImpl`-클래스를 파생 합니다. 템플릿 화할 비 클래스 메서드가 포함 될 수 있습니다, 때문에 리소스 `pv` 을 적절 한 `CRowsetImpl`-클래스를 파생 합니다.  
  
 다음 예제에서는 **GetColumnInfo의** 사용 합니다. 이 예제에서는 **CMyRowset** 는 `CRowsetImpl`-클래스를 파생 합니다. 재정의 하기 위해 `GetColumnInfo` 이 클래스의 모든 인스턴스에 대 한 배치에서 다음 메서드는 **CMyRowset** 클래스 정의:  
  
 [!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)