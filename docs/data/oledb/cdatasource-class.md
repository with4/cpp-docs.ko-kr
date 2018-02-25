---
title: "CDataSource 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
dev_langs:
- C++
helpviewer_keywords:
- CDataSource class
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 508bbfc7551383fe1d4517d274031faef590fdb9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdatasource-class"></a>CDataSource 클래스
데이터 원본에 공급자를 통해 연결을 나타내는 OLE DB 데이터 원본 개체에 해당 합니다.  
  
## <a name="syntax"></a>구문

```cpp
class CDataSource  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[닫기](../../data/oledb/cdatasource-close.md)|연결을 닫습니다.|  
|[GetInitializationString](../../data/oledb/cdatasource-getinitializationstring.md)|현재 열려 있는 데이터 원본 초기화 문자열을 검색 합니다.|  
|[GetProperties](../../data/oledb/cdatasource-getproperties.md)|현재 연결된 된 데이터 원본에 대해 설정 된 속성의 값을 가져옵니다.|  
|[GetProperty](../../data/oledb/cdatasource-getproperty.md)|현재 연결된 된 데이터 원본에 대해 설정 하는 단일 속성의 값을 가져옵니다.|  
|[열기](../../data/oledb/cdatasource-open.md)|중 하나를 사용 하 여 공급자 (데이터 원본)에 대 한 연결을 만듭니다는 **CLSID**, **ProgID**, 또는 `CEnumerator` 호출자가 제공 하는 모니커입니다.|  
|[OpenFromFileName](../../data/oledb/cdatasource-openfromfilename.md)|사용자가 제공한 파일 이름으로 지정된 파일에서 데이터 소스를 엽니다.|  
|[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)|초기화 문자열에 의해 지정 된 데이터 소스를 엽니다.|  
|[OpenWithPromptFileName](../../data/oledb/cdatasource-openwithpromptfilename.md)|사용자를 이전에 만든된 데이터 링크 파일은 해당 데이터 원본의 열을 선택할 수 있습니다.|  
|[OpenWithServiceComponents](../../data/oledb/cdatasource-openwithservicecomponents.md)|데이터 연결 대화 상자를 사용 하 여 데이터 원본 개체를 엽니다.|  
  
## <a name="remarks"></a>설명  
 단일 연결에 대 한 하나 이상의 데이터베이스 세션을 만들 수 있습니다. 이러한 세션은 `CSession`합니다. 호출 해야 [cdatasource:: Open](../../data/oledb/cdatasource-open.md) 와 세션을 만들기 전에 연결을 열려는 `CSession::Open`합니다.  
  
 사용 하는 방법의 예제를 보려면 `CDataSource`, 참조는 [CatDB](../../visual-cpp-samples.md) 샘플.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)