---
title: "CSimpleRow 클래스 | Microsoft Docs"
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
  - "CSimpleRow"
  - "ATL::CSimpleRow"
  - "ATL.CSimpleRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleRow 클래스"
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleRow 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[RowseImpl](../../data/oledb/irowsetimpl-class.md) 클래스에서 사용되는 행 처리기 위한 기본 구현체를 제공합니다.  
  
## 구문  
  
```  
class CSimpleRow  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[AddRefRow](../../data/oledb/csimplerow-addrefrow.md)|기존 행 핸들에 참조 횟수를 추가합니다.|  
|[비교](../../data/oledb/csimplerow-compare.md)|동일한 행 인스턴스를 참조하는지 여부를 확인하기 위해 두 개의 행 을 비교합니다.|  
|[CSimpleRow](../../data/oledb/csimplerow-csimplerow.md)|생성자입니다.|  
|[ReleaseRow](../../data/oledb/csimplerow-releaserow.md)|행을 해제합니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_dwRef](../../data/oledb/csimplerow-m-dwref.md)|기존 행 핸들에 참조 횟수 입니다.|  
|[m\_iRowset](../../data/oledb/csimplerow-m-irowset.md)|커서를 나타내는 행 집합에 대한 인덱스입니다.|  
  
## 설명  
 행 핸들은 논리적 결과 행에 대한 고유 태그입니다.  `IRowsetImpl` 는 [IRowsetImpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) 에서 요청 된 모든 행에 대해 새 `CSimpleRow` 를 생성합니다.  `IRowsetImpl` 에 대한 기본 템플릿 인수일 때 `CSimpleRow` 는 행 핸들의 고유한 구현으로 대체합니다.  이 클래스를 대체하는 것에 대한 요청은 **LONG** 형식의 단일 매개 변수를 받아들이는 생성자를 제공하는 클래스 대체를 가집니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)