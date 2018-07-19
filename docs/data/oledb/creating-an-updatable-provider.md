---
title: 업데이트 가능 공급자 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbcd69168b70e8d85bf2b90c3f456f79cd1c228c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954586"
---
# <a name="creating-an-updatable-provider"></a>업데이트 가능 공급자 만들기

업데이트할 수 있는 공급자 또는 공급자를 업데이트할 수 있는 visual c + + 지원 (쓸) 데이터 저장소입니다. 이 항목에서는 OLE DB 템플릿을 사용 하 여 업데이트할 수 있는 공급자를 만드는 방법을 설명 합니다.  
  
 이 항목에서는 작업 공급자를 사용 하 여 시작 한다고 가정 합니다. 업데이트 가능 공급자 만들기에 다음과 같은 두 단계가 있습니다. 어떻게 공급자는 변경 하는 데이터 저장소를 먼저 결정 해야 합니다. 특히, 변경 내용을 즉시 수행 해야 하는 여부를 update 명령이 실행 될 때까지 지연 합니다. 섹션 "[공급자 업데이트할 수 있도록](#vchowmakingprovidersupdatable)" 변경 내용과 공급자 코드에서 작업을 수행 하는 데 필요한 설정을 설명 합니다.  
  
 그런 다음 공급자 소비자가 요청 하는 아무 것도 지원 하기 위한 모든 기능이 포함 되어 있는지 확인 해야 합니다. 소비자를 데이터 저장소를 업데이트 하려는 경우 공급자는 데이터 저장소의 데이터를 유지 하는 코드를 포함 해야 합니다. 예를 들어, 데이터 원본에 따라 이러한 작업을 수행 하는 C 런타임 라이브러리 또는 MFC를 사용할 수 있습니다. 섹션 "[데이터 원본에 쓸](#vchowwritingtothedatasource)" 데이터 원본에 쓰기를 처리 하는 방법에 설명 합니다 `NULL` 기본값 및 열 플래그 설정 합니다.  
  
> [!NOTE]
>  UpdatePV는 업데이트할 수 있는 공급자의 예시입니다. UpdatePV는 MyProv로 업데이트할 수 있는 지원과 동일합니다.  
  
##  <a name="vchowmakingprovidersupdatable"></a> 메서드를 업데이트 가능 공급자 만들기  

 핵심 공급자를 업데이트할 수 있는 공급자를 데이터 저장소 및 해당 작업을 수행 하는 공급자를 원하는 방식에 대해 수행 하려는 작업 파악 합니다. 특히 중요 한 문제는 즉시 또는 지연 된 데이터 저장소에 대 한 업데이트 되는지 (일괄 처리) update 명령이 실행 될 때까지 합니다.  
  
 상속 여부를 먼저 결정 해야 합니다 `IRowsetChangeImpl` 또는 `IRowsetUpdateImpl` 행 집합 클래스에서. 이 중에서 어떤에 따라 구현에 세 가지 방법의 기능을 영향을 받게 됩니다. `SetData`, `InsertRows`, 및 `DeleteRows`합니다.  
  
- 상속 하는 경우 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), 데이터 저장소 변경 즉시 이러한 세 가지 메서드를 호출 합니다.  
  
- 상속 하는 경우 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), 메서드를 호출 하기 전에 데이터 저장소에 변경 내용을 연기 `Update`합니다 `GetOriginalData`, 또는 `Undo`합니다. 몇 가지 변경 사항을 포함 하는 업데이트를 일괄 처리 모드 (변경 내용 일괄 처리 상당한 메모리 오버 헤드를 추가할 수 있음을 참고)에서 수행 됩니다.  
  
 사실은 `IRowsetUpdateImpl` 에서 파생 `IRowsetChangeImpl`합니다. 따라서 `IRowsetUpdateImpl` 제공 기능 뿐만 아니라 일괄 처리 기능을 변경 합니다.  
  
#### <a name="to-support-updatability-in-your-provider"></a>업데이트를 지원 하려면 공급자에서  
  
1. 행 집합 클래스에서 상속 `IRowsetChangeImpl` 또는 `IRowsetUpdateImpl`합니다. 이러한 클래스는 데이터 저장소 변경에 대 한 적절 한 인터페이스를 제공 합니다.  
  
     **IRowsetChange 추가**  
  
     추가 `IRowsetChangeImpl` 이 형식을 사용 하 여 사용자가 상속 체인을 합니다.  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     추가할 수도 `COM_INTERFACE_ENTRY(IRowsetChange)` 에 `BEGIN_COM_MAP` 행 집합 클래스에서 섹션입니다.  
  
     **IRowsetUpdate 추가**  
  
     추가 `IRowsetUpdate` 이 형식을 사용 하 여 사용자가 상속 체인을 합니다.  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  제거 해야 합니다 `IRowsetChangeImpl` 상속 체인에 줄. 앞에서 언급 한 지시문이 한 가지 예외에 대 한 코드를 포함 해야 `IRowsetChangeImpl`합니다.  
  
2.  다음을 고 COM 맵에 추가 합니다 (`BEGIN_COM_MAP ... END_COM_MAP`):  
  
    |구현 하는 경우|COM 맵에 추가|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  명령에 다음 속성 집합 맵에 추가 합니다 (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):  
  
    |구현 하는 경우|속성 집합 구조에 추가|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  사용자 속성 집합 구조의 포함 해야 다음 설정 중 모든 아래 나타나는:  
  
    ```  
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |   
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)  
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)  
  
    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)  
    ```  
  
     속성 Id 및 값을 Atldb.h에 검색 하 여 이러한 매크로 호출에 사용 되는 값을 찾을 수 있습니다 (Atldb.h 온라인 설명서와 다른 경우 Atldb.h 대체 설명서).  
  
    > [!NOTE]
    >  많은 합니다 `VARIANT_FALSE` 및 `VARIANT_TRUE` 설정은 OLE DB 템플릿에서 필요; OLE DB 사양은 읽기/쓰기 수 하지만 OLE DB 템플릿 하나의 값을 하나만 지원할 수 있습니다.  
  
     **IRowsetChangeImpl를 구현 하는 경우**  
  
     구현 하는 경우 `IRowsetChangeImpl`를 공급자에는 다음 속성을 설정 해야 합니다. 이러한 속성을 통해 인터페이스를 요청 사용 주로 `ICommandProperties::SetProperties`합니다.  
  
    - `DBPROP_IRowsetChange`: 설정 집합이 자동으로 `DBPROP_IRowsetChange`입니다.  
  
    - `DBPROP_UPDATABILITY`지원 되는 메서드를 지정 하는 비트 마스크: `IRowsetChange`: `SetData`하십시오 `DeleteRows`, 또는 `InsertRow`합니다.  
  
    - `DBPROP_CHANGEINSERTEDROWS`: 소비자를 호출할 수 있습니다 `IRowsetChange::DeleteRows` 또는 `SetData` 새로 삽입된 된 행에 대 한 합니다.  
  
    - `DBPROP_IMMOBILEROWS`: 행 집합 삽입 되거나 업데이트 된 행 순서를 바꾸지 않습니다.  
  
     **IRowsetUpdateImpl를 구현 하는 경우**  
  
     구현 하는 경우 `IRowsetUpdateImpl`를 설정 해야 다음 속성을 공급자 뿐만 아니라 모든 속성을 설정 하 `IRowsetChangeImpl` 위에 나열 된:  
  
    - `DBPROP_IRowsetUpdate`.  
  
    - `DBPROP_OWNINSERT`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    - `DBPROP_OWNUPDATEDELETE`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    - `DBPROP_OTHERINSERT`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    - `DBPROP_REMOVEDELETED`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    - `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  알림을 지 원하는 경우 해야 할 수 있습니다 다른 속성 에서도; 섹션을 참조 `IRowsetNotifyCP` 이 목록에 대 한 합니다.  
  
##  <a name="vchowwritingtothedatasource"></a> 데이터 원본에 쓰기  
 데이터 원본에서 읽기 호출을 `Execute` 함수입니다. 데이터 원본에 쓸 호출을 `FlushData` 함수입니다. (일반적인 의미에서 플러시 테이블 또는 인덱스를 디스크에 수정 내용을 저장 하는 수단입니다.)  

