---
title: "CRestrictions::Open | Microsoft Docs"
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
  - "CRestrictions.Open"
  - "ATL::CRestrictions::Open"
  - "ATL.CRestrictions.Open"
  - "CRestrictions::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open 메서드"
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRestrictions::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자가 제공한 제한에 따라 설정 하는 결과를 반환 합니다.  
  
## 구문  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true  
);  
```  
  
#### 매개 변수  
 `session`  
 \[in\] 기존 데이터 원본에 연결 하는 세션 개체를 지정 합니다.  
  
 *lpszParam*  
 \[in\] 스키마 행 집합에 제한 사항을 지정합니다.  
  
 `bBind`  
 \[in\] 열 맵을 자동으로 바인딩할 것인지 지정 합니다.  열 맵을 자동적으로 바인딩하게 하는 기본 값은 **true** 입니다.  `bBind` 를 **false** 로 설정하는 것은 열 맵의 자동 바인딩을 막습니다. 그렇게 하여 직접 바인딩할 수 있습니다. \(수동 바인딩은 OLAP 사용자에게 특정 관심 영역입니다.\)  
  
## 반환 값  
 정규 `HRESULT` 값 중 하나 입니다.  
  
## 설명  
 스키마 행 집합에 최대 7 개의 제한을 지정할 수 있습니다.  
  
 스키마 행 집합에 정의 된 제한에 대한 정보는 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)를 참조하십시오.  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)   
 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)