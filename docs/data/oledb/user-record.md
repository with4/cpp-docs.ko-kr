---
title: "사용자 레코드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 공급자, 사용자 레코드"
  - "레코드, 사용자"
  - "행 집합, 사용자 레코드"
  - "사용자 레코드"
  - "사용자 레코드, 설명"
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 사용자 레코드
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 레코드는 행 집합의 열 데이터를 나타내는 코드와 데이터 구조를 제공합니다.  사용자 레코드는 컴파일 타임이나 런타임에 만들 수 있습니다.  ATL OLE DB 공급자 마법사를 사용하여 공급자를 만들면 마법사가 다음과 같은 기본 사용자 레코드를 만듭니다. 이 경우 공급자 이름\(약식 이름\)을 "MyProvider"로 지정했다고 가정합니다.  
  
```  
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
  
 OLE DB 공급자 템플릿은 클라이언트와의 상호 작용에 관련된 모든 OLE DB 사항을 처리합니다.  공급자는 응답에 필요한 열 데이터를 얻기 위해 사용자가 사용자 레코드에 반드시 넣어야 할 함수인 `GetColumnInfo` 함수를 호출합니다.  예를 들어, 다음과 같이 이 함수를 .h 파일에 선언하여 사용자 레코드의 `GetColumnInfo`를 명시적으로 재정의할 수 있습니다.  
  
```  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 다음과 일치합니다.  
  
```  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 또한 사용자 레코드의 .cpp 파일에서 `GetColumnInfo`를 구현해야 합니다.  
  
 PROVIDER\_COLUMN\_MAP 매크로를 사용하면 `GetColumnInfo` 함수를 만드는 데 도움이 됩니다.  
  
-   BEGIN\_PROVIDER\_COLUMN\_MAP은 함수 프로토타입과 **ATLCOLUMNINFO** 구조의 정적 배열을 정의합니다.  
  
-   PROVIDER\_COLUMN\_ENTRY는 단일 **ATLCOUMNINFO**를 정의하고 초기화합니다.  
  
-   END\_PROVIDER\_COLUMN\_MAP은 배열과 함수를 닫습니다.  또한 이 함수는 `pcCols`매개 변수에 배열 요소의 개수를 배치합니다.  
  
 런타임에 사용자 레코드를 만들면 **GetColumnInfo** 가 `pThis` 매개 변수를 사용하여 행 집합이나 명령 인스턴스에 대한 포인터를 받습니다.  명령과 행 집합은 `IColumnsInfo` 인터페이스를 지원하므로 이 포인터에서 열 정보를 가져올 수 있습니다.  
  
 **CommandClass**와 **RowsetClass**는 사용자 레코드를 사용하는 명령과 행 집합입니다.  
  
 사용자 레코드에서 `GetColumnInfo`를 재정의하는 자세한 예제는 [소비자에게 반환되는 열을 동적으로 결정](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)을 참조하십시오.  
  
## 참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)