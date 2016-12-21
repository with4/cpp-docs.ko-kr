---
title: "CEnumerator 클래스 | Microsoft Docs"
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
  - "CEnumerator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEnumerator 클래스"
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEnumerator 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) 인터페이스를 설명하여 모든 데이터 소스 열거자 행 집합을 반환하는 노출 하는 OLE DB 열거자 개체를 사용합니다.  
  
## 구문  
  
```  
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[Find](../../data/oledb/cenumerator-find.md)|지정  이름으로 찾고 사용할 수 있는 공급자 \(데이터 원본\)을 통해 검색합니다.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|현재 레코드에 대한  `IMoniker`  인터페이스를 검색합니다.|  
|[를 엽니다.](../../data/oledb/cenumerator-open.md)|열거자를 엽니다.|  
  
## 설명  
 이 클래스에서 간접적으로 **ISourcesRowset** 데이터를 검색할 수 있습니다.  
  
## 요구 사항  
 **Header:**atldbcli.h  
  
## 참고 항목  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)