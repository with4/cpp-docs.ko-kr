---
title: "OLE DB 공급자 템플릿 참조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.templates.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 68c741f09772c881b42dc4e4cd17de31ed107f8c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-provider-templates-reference"></a>OLE DB 공급자 템플릿 참조
클래스와 OLE DB 공급자 템플릿에 대 한 인터페이스는 다음과 같은 범주로 그룹화 할 수 있습니다. 또한 참조 자료에 대 한 정보를 포함 된 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)합니다.  
  
 다음 명명 규칙을 사용 하는 클래스: 패턴으로 라는 클래스 **IWidgetImpl** 인터페이스의 구현을 제공 하는 **IWidget**합니다.  
  
## <a name="session-classes"></a>세션 클래스  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 데이터 원본 개체에서 새 세션을 만들고 새로 만들어진된 세션의 요청 된 인터페이스를 반환 합니다. 데이터 원본 개체에 필수 인터페이스입니다.  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 속성 집합 맵에 정의 된 정적 함수를 호출 하 여 세션 속성을 구현 합니다. 세션 클래스의 속성 집합 지도 지정 해야 합니다. 세션에 대해 필수 인터페이스입니다.  
  
## <a name="rowset-classes"></a>행 집합 클래스  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 많은 구현 인터페이스의 여러 상속을 요구 하지 않고 표준 OLE DB 행 집합 구현을 제공 합니다. 구현이 제공 해야 하는 유일한 방법은 **Execute**합니다.  
  
 [CSimpleRow](../../data/oledb/csimplerow-class.md)  
 에 사용 되는 행 핸들에 대 한 기본 구현을 제공는 `IRowsetImpl` 클래스입니다. 행 핸들은 논리적으로 결과 행에 대 한 고유 태그입니다. `IRowsetImpl` 새 `CSimpleRow` 에서 요청 된 모든 행에 대 한 `IRowsetImpl::GetNextRows`합니다.  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB 공급자를 구현할 필요는 **HACCESSOR**, 하는 배열에 태그 **DBBINDING** 구조입니다. 제공 **HACCESSOR**는 주소입니다. s는 **BindType** 구조입니다. 행 집합 및 명령에 대해 필수 항목입니다.  
  
 [IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 공급자 열의 맵에 정의 된 정적 함수 대리자입니다. 행 집합 및 명령에 대해 필수 인터페이스입니다.  
  
 [IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)  
 명령에 또는 행 집합에서 형식 변환의 가용성에 대 한 정보를 제공합니다. 명령, 행 집합 및 인덱스 행 집합에 필수 항목입니다. 구현 된 **IConvertType** OLE DB에서 제공 된 변환 개체에 위임 하 여 인터페이스입니다.  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 구현 된 **IDBSchemaRowset** 인터페이스 및 템플릿 화 된 작성자 함수 `CreateSchemaRowset`합니다.  
  
 [IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)  
 페이지를 열고 단일 기본 테이블 또는 인덱스에서 모든 행을 포함 하는 행 집합을 반환 합니다. 세션 개체에 대 한 필수 인터페이스입니다.  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 OLE DB 구현 [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) 행을 삭제 하 고 새 행을 삽입의 기존 행의 열 값의 업데이트 수 있도록 하는 인터페이스입니다.  
  
 [IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)  
 이 클래스에서 상속 [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) 재정의 [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)합니다. `IRowsetCreatorImpl` 동일한 기능을 수행 `IObjectWithSite` 하지만 또한 OLE DB 속성을 사용 하면 **DBPROPCANSCROLLBACKWARDS** 및 **DBPROPCANFETCHBACKWARDS**합니다.  
  
 [IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)  
 구현 된 **IRowsetIdentity** 인터페이스를 통해 두 행의 데이터가 동일한 지 여부를 비교할 수 있습니다.  
  
 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)  
 구현을 제공는 `IRowset` 인터페이스에 기본 행 집합 인터페이스입니다.  
  
 [IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)  
 속성을 사용 하 여 행 집합 속성 구현 명령 클래스에 정의 된 지도 설정 합니다. 필수 행 집합 인터페이스입니다.  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 OLE DB 구현 [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) 인터페이스에는 행 집합에서 임의의 행을 인출 합니다. 행 집합에 OLE DB 책갈피를 지원 하려면이 클래스에서 상속 하는 행 집합을 확인 합니다.  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 구현 브로드캐스트 수신기 연결 지점에 대해 알리기 위해 함수 **IID_IRowsetNotify** 행 집합의 내용 변경 합니다. 알림을 처리 하는 소비자 구현 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) 해당 연결 지점에 등록 하십시오.  
  
 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)  
 OLE DB 구현 [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) 소비자가 변경 된 내용을 전송 지연 시킬 수 있는 인터페이스 [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) 를 데이터 소스 및 전송 하기 전에 변경 내용을 취소 합니다.  
  
## <a name="command-classes"></a>명령 클래스  
 [ICommandImpl](../../data/oledb/icommandimpl-class.md)  
 `ICommand` 인터페이스의 구현을 제공합니다. 이 인터페이스는 표시 되지 않지만 의해 처리 됩니다 **ICommandTextImpl**합니다. 명령 개체에서 필수 인터페이스입니다.  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 이 구현에서 **ICommandProperties** 인터페이스에 정의 된 정적 함수에 의해 제공 됩니다는 `BEGIN_PROPSET_MAP` 매크로입니다. 명령에서 필수 항목입니다.  
  
 [ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)  
 설정 하 고 저장 하 고, 명령 텍스트를 반환 합니다. 명령에서 필수 항목입니다.  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 세션 개체의 새 명령을 만들고 새로 만든된 명령에 요청된 된 인터페이스를 반환 합니다. 세션 개체에 대 한 선택적 인터페이스입니다.  
  
 다른 명령 클래스는 `IColumnsInfoImpl` 및 `IAccessorImpl`위의 행 집합 클래스 섹션에 설명 된 대로 합니다.  
  
## <a name="data-source-classes"></a>데이터 소스 클래스  
 [IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)  
 만들고 소비자와의 연결을 삭제 합니다. 데이터 원본 개체와 열거자에 대해 선택적 인터페이스에서 필수 인터페이스입니다.  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` 데이터 원본 개체에 대 한 필수 인터페이스 및 열거자에 대 한 선택적 인터페이스 이며 그러나는 열거자를 노출 하는 경우 **IDBInitialize**를 노출 해야 `IDBProperties` (데이터 원본에 속성).  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 데이터 원본 개체에 대 한 인터페이스 포인터를 가져옵니다. 세션에서 필수 인터페이스입니다.  
  
## <a name="other-classes"></a>다른 클래스  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 다양 한 OLE DB 속성 인터페이스에 대 한 속성 구현 (예를 들어 `IDBProperties`, **ISessionProperties**, 및 `IRowsetInfo`).  
  
 [IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 OLE DB 구현 [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) 인터페이스를 레코드를 추가 및 데이터 멤버에서 레코드를 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB 템플릿](../../data/oledb/ole-db-templates.md)