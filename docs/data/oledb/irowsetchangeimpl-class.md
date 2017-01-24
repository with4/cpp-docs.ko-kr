---
title: "IRowsetChangeImpl 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetChangeImpl"
  - "IRowsetChangeImpl"
  - "ATL.IRowsetChangeImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetChangeImpl 클래스"
  - "공급자, 업데이트 가능"
  - "업데이트 가능 공급자, 직접 업데이트"
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetChangeImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB 구현에서 [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) 인터페이스의 OLE DB 템플릿 구현입니다.  
  
## 구문  
  
```  
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >   
>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### 매개 변수  
 `T`  
 `IRowsetChangeImpl` 로부터 파생된 클래스입니다.  
  
 `Storage`  
 사용자 레코드  
  
 `BaseInterface`  
 `IRowsetChange` 같은, 인터페이스에 대한 기본클래스입니다.  
  
 `RowClass`  
 행 핸들에 대한 저장소 단위입니다.  
  
 `MapClass`  
 공급자로 유지되는 모든 행 핸들들에 대한 저장소 단위입니다.  
  
## 멤버  
  
### 인터페이스 메서드 \(IRowsetChange 사용\)  
  
|||  
|-|-|  
|[DeleteRows](../../data/oledb/irowsetchangeimpl-deleterows.md)|행 집합에서 행을 삭제합니다.|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|행 집합에 행을 삽입합니다.|  
|[SetData](../../data/oledb/irowsetchangeimpl-setdata.md)|하나 이상의 열에서 데이터 값을 설정합니다.|  
  
### 구현 메서드 \(콜백\)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|저장소에 데이터를 커밋하기 위해 공급자가 재정의되었습니다.|  
  
## 설명  
 이 인터페이스는 데이터 저장소에 즉시 쓰기 작업을 담당합니다. "즉시"는 최종 사용자\(소비자를 사용하는사람\)가 모두 변경할때, 이 변화가 즉시 데이터 저장소로 전송되는 것을 의미합니다.\(그리고 취소할 수 없게 됩니다.\)  
  
 `IRowsetChangeImpl` 은 OLE DB `IRowsetChange` 인터페이스를 구현하고, 이것은 기존의 행들, 제거되는 행들, 새로 추가되는 행들에서 열의 값들의 업데이트를 활성화합니다.  
  
 OLE DB 템플릿 구현은 모든 기본 메서드들을 지원합니다.\(`SetData`, `InsertRow`, 와 `DeleteRows`\)  
  
> [!IMPORTANT]
>  다음 부분은 당신의 공급자를 구현하기 전에 다음 문서를 읽어 보는 것이 좋습니다:  
  
-   [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)  
  
-   챕터 6 *OLE DB Programmer's Reference*  
  
-   UpdatePV 예제에서 어떻게 `RUpdateRowset` 클래스가 사용되는지 역시 보여줍니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)