---
title: 'Cdatasource:: Openwithservicecomponents | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
dev_langs:
- C++
helpviewer_keywords:
- OpenWithServiceComponents method
ms.assetid: 49c1d037-36ae-4fde-8e54-ced623abe1a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 793f1fcb22ac0c57bc1cccb375a0be24b18116ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourceopenwithservicecomponents"></a>CDataSource::OpenWithServiceComponents
oledb32.dll에서 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  


HRESULT OpenWithServiceComponents (LPCSTR szProgID,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] **CLSID** 데이터 공급자의입니다.  
  
 `szProgID`  
 [in] 데이터 공급자의 프로그램 ID입니다.  
  
 `pPropset`  
 [in] 배열에 대 한 포인터 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 속성 및 값을 설정할 수를 포함 하는 구조체입니다. 참조 [속성 집합 및 속성 그룹](https://msdn.microsoft.com/en-us/library/ms713696.aspx) 에 *OLE DB Programmer's Reference* in the Windows SDK입니다. 데이터 원본 개체가 초기화되면 속성은 데이터 원본 속성 그룹에 속해야 합니다. 동일한 속성이 `pPropset`에 두 번 이상 지정되면 사용되는 값은 공급자별로 다릅니다. `ulPropSets`가 0이면 이 매개 변수는 무시됩니다.  
  
 `ulPropSets`  
 [in] 수가 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체에 전달 된 *pPropSet* 인수입니다. 이 값이 0이면 공급자가 `pPropset`을 무시합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다. 자세한 내용은 "OLE DB 서비스" 참조에서 OLE DB 프로그래머 참조에서 [ http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)