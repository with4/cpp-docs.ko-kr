---
title: "CRestrictions 클래스 | Microsoft Docs"
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
  - "ATL::CRestrictions"
  - "CRestrictions"
  - "ATL.CRestrictions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRestrictions 클래스"
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRestrictions 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제네릭 클래스는 스키마 행 집합에 대한 제한을 지정할 수 있습니다.  
  
## 구문  
  
```  
template <   
   class T,   
   short nRestrictions,   
   const GUID* pguid   
>  
class CRestrictions : public CSchemaRowset <   
   T,   
   nRestrictions   
>  
```  
  
#### 매개 변수  
 `T`  
 접근자에 대해 사용 되는 클래스입니다.  
  
 `nRestrictions`  
 스키마 행 집합에 대한 제한은 열의 수입니다.  
  
 `pguid`  
 스키마에 대한 GUID에 대한 포인터입니다.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[를 엽니다.](../../data/oledb/crestrictions-open.md)|사용자가 제공한 제한에 따라 설정 하는 결과를 반환 합니다.|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)