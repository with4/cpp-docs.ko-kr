---
title: "CDBErrorInfo 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDBErrorInfo class
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ae65a1a04d5befdfcd22327def8f60d96c9d4cff
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo 클래스
OLE DB를 사용 하 여 OLE DB 오류 처리에 대 한 지원을 제공 [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
class CDBErrorInfo  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|오류 레코드에 포함 된 모든 오류 정보를 반환 합니다.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|호출 [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) 지정된 된 오류에 대 한 기본 정보를 반환 합니다.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|호출 [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) 를 사용자 지정 오류 개체에는 인터페이스에 대 한 포인터를 반환 합니다.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|호출 [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) 반환 하는 **IErrorInfo** 지정된 된 레코드에 대 한 인터페이스 포인터입니다.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|호출 [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) 반환할 오류 매개 변수입니다.|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|지정된 된 개체에 대 한 오류 레코드를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 사용자에 게 하나 이상의 오류 레코드를 반환합니다. 호출 [cdberrorinfo:: Geterrorrecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) 의 오류 레코드 수를 가져오려는 첫 번째입니다. 다음와 같은 함수는 액세스 중 하나를 호출 [cdberrorinfo:: Getallerrorinfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), 각 레코드에 대 한 오류 정보를 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)