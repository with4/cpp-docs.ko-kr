---
title: 접근자 및 행 집합 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- accessors [C++]
- OLE DB consumer templates, rowset support
- OLE DB consumer templates, accessors
- rowsets [C++], accessing
- bulk rowsets
- CAccessorRowset class, accessor types
- single rowsets
- CArrayRowset class, accessors
- CBulkRowset class, accessors
- array rowsets
- CAccessorBase class
- CRowset class, accessors and rowsets
- accessors [C++], rowsets
- rowsets [C++], supported types
ms.assetid: edc9c8b3-1a2d-4c2d-869f-7e058c631042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 49f5415f6c75984f968b25fb709c20d80dde554f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094497"
---
# <a name="accessors-and-rowsets"></a>접근자 및 행 집합
설정 하 고 데이터를 검색 하려면 OLE DB 템플릿 사용 접근자 및 행 집합을 통해는 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) 클래스입니다. 이 클래스는 서로 다른 유형의 여러 접근자를 처리할 수 있습니다.  
  
## <a name="accessor-types"></a>접근자 형식  
 파생 되는 모든 접근자 [CAccessorBase](../../data/oledb/caccessorbase-class.md)합니다. `CAccessorBase` 매개 변수 및 열 바인딩 모두 제공합니다.  
  
 다음 그림에는 접근자 형식을 보여 줍니다.  
  
 ![접근자 형식](../../data/oledb/media/vcaccessortypes.gif "vcaccessortypes")  
접근자 클래스  
  
-   [CAccessor](../../data/oledb/caccessor-class.md) 데이터베이스 소스의 구조 디자인 타임에 알고 있는 경우이 접근자를 사용 합니다. `CAccessor` 정적으로 버퍼를 포함 하는 데이터베이스 레코드를 데이터 원본에 바인딩합니다.  
  
-   [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 디자인 타임에는 데이터베이스의 구조를 인식 하지 않는 경우이 접근자를 사용 합니다. `CDynamicAccessor` 호출 `IColumnsInfo::GetColumnInfo` 데이터베이스 열 정보를 가져옵니다. 만들고 접근자 및 버퍼를 관리 합니다.  
  
-   [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) 알 수 없는 명령 유형을 처리 하도록이 접근자를 사용 합니다. 명령을 준비할 때 `CDynamicParameterAccessor` 에서 매개 변수 정보를 얻을 수는 `ICommandWithParameters` 인터페이스, 공급자가 지 원하는 경우 `ICommandWithParameters`합니다.  
  
-   [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md), 및 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md) 데이터베이스 스키마의 모를 때 이러한 클래스를 사용 합니다. `CDynamicStringAccessorA` ANSI 문자열로; 데이터를 검색합니다. `CDynamicStringAccessorW` 유니코드 문자열으로 데이터를 검색 합니다.  
  
-   [CManualAccessor](../../data/oledb/cmanualaccessor-class.md) 이 클래스와 공급자 유형으로 변환할 수 있으면 원하는 모든 데이터 형식을 사용할 수 있습니다. 결과 열과 명령 매개 변수를 처리합니다.  
  
 다음 표에서 OLE DB 템플릿 접근자 형식에 지원이 요약 되어 있습니다.  
  
|접근자 형식|동적|매개 변수 처리|버퍼|여러 접근자|  
|-------------------|-------------|--------------------|------------|------------------------|  
|`CAccessor`|아니요|예|사용자|예|  
|`CDynamicAccessor`|예|아니요|OLE DB 템플릿|아니요|  
|`CDynamicParameterAccessor`|예|예|OLE DB 템플릿|아니요|  
|`CDynamicStringAccessor[A,W]`|예|아니요|OLE DB 템플릿|아니요|  
|`CManualAccessor`|예|예|사용자|예|  
  
## <a name="rowset-types"></a>행 집합 형식  
 OLE DB 템플릿은 지원 행 집합 (위 그림 참조)의 세 가지 종류: 행 집합을 단일 (구현한 [CRowset](../../data/oledb/crowset-class.md)), 행 집합 대량 (구현한 [CBulkRowset](../../data/oledb/cbulkrowset-class.md)), 및 배열 (구현 행 집합 여 [CArrayRowset](../../data/oledb/carrayrowset-class.md)). 단일 행 집합 인출 될 때 단일 행 핸들 `MoveNext` 라고 합니다. 대량 행 집합에는 여러 행 핸들 인출할 수 있습니다. 배열 행 집합은 배열 구문을 사용 하 여 액세스할 수 있는 행 집합입니다.  
  
 다음 그림에는 행 집합 형식을 보여 줍니다.  
  
 ![RowsetType 그래픽](../../data/oledb/media/vcrowsettypes.gif "vcrowsettypes")  
행 집합 클래스  
  
 [스키마 행 집합](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) 데이터에서 데이터를 액세스 저장 않지만 대신 액세스 메타 데이터 라고 하는 데이터 저장소에 대 한 정보입니다. 스키마 행 집합은 일반적으로 데이터베이스 구조 컴파일 타임에 알려지지 않은 고 런타임 시 구입 해야 경우에 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)