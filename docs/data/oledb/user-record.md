---
title: 사용자 레코드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b53410c8116f88d51734bb302026a03994e520a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338196"
---
# <a name="user-record"></a>사용자 레코드
사용자 레코드에는 행 집합의 열 데이터를 나타내는 코드 및 데이터 구조를 제공 합니다. 컴파일 타임 또는 런타임에 사용자 레코드를 만들 수 있습니다. ATL OLE DB 공급자 마법사를 사용 하 여 공급자를 만들 때 마법사는 다음과 같이 표시 됩니다 ("MyProvider"의 공급자 이름 (약식 이름)로 지정 했다고 가정) 기본 사용자 레코드를 만듭니다.  
  
```cpp  
class CWindowsFile:  
   public WIN32_FIND_DATA  
{  
public:  
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
  
};  
```  
  
 OLE DB 공급자 템플릿 클라이언트와의 상호 작용에 대 한 모든 OLE DB 세부 정보를 처리합니다. 공급자 호출을 획득 하기 위해 응답에 대 한 필요한 열 데이터는 `GetColumnInfo` 함수를 사용자 레코드에 배치 해야 합니다. 명시적으로 재정의할 수 `GetColumnInfo` 사용자 레코드에서 예를 들어 선언 하 여.h 파일에서 다음과 같이 합니다.  
  
```cpp  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 다음 코드와 동일합니다.  
  
```cpp  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 도 구현 해야 `GetColumnInfo` 사용자 레코드의.cpp 파일에 있습니다.  
  
 PROVIDER_COLUMN_MAP 매크로 만들기에 도움이 되는 `GetColumnInfo` 함수:  
  
-   BEGIN_PROVIDER_COLUMN_MAP 함수 프로토타입 및 정적 배열을 정의 `ATLCOLUMNINFO` 구조입니다.  
  
-   PROVIDER_COLUMN_ENTRY 정의 하 고 단일 초기화 `ATLCOLUMNINFO`합니다.  
  
-   END_PROVIDER_COLUMN_MAP 배열 및 함수를 닫습니다. 배열 요소 수에도 배치 합니다 *pcCols* 매개 변수입니다.  
  
 런타임 시 사용자 레코드가 만들어질 때 `GetColumnInfo` 사용 하는 *pThis* 매개 변수 행 집합 또는 명령 인스턴스에 대 한 포인터를 수신 합니다. 명령 및 행 집합을 지원 해야 합니다는 `IColumnsInfo` 인터페이스를 this이 포인터에서 열 정보를 얻을 수 있도록 합니다.  
  
 `CommandClass` 및 `RowsetClass` 명령 및 사용자 레코드를 사용 하는 행 집합입니다.  
  
 재정의 하는 방법의 자세한 예제 `GetColumnInfo` 사용자 레코드를 확인할 [소비자에 게 반환 되는 열을 동적으로 결정](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)