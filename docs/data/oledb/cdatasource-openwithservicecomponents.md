---
title: "CDataSource::OpenWithServiceComponents | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource::OpenWithServiceComponents"
  - "OpenWithServiceComponents"
  - "CDataSource.OpenWithServiceComponents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenWithServiceComponents 메서드"
ms.assetid: 49c1d037-36ae-4fde-8e54-ced623abe1a9
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::OpenWithServiceComponents
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

oledb32.dll에서 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다.  
  
## 구문  
  
```  
  
        HRESULT OpenWithServiceComponents (  
   const CLSID clsid,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1   
);  
HRESULT OpenWithServiceComponents (  
   LPCSTR szProgID,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1   
);  
```  
  
#### 매개 변수  
 `clsid`  
 \[in\] 데이터 공급자의 **CLSID**입니다.  
  
 `szProgID`  
 \[in\] 데이터 공급자의 프로그램 ID입니다.  
  
 `pPropset`  
 \[in\] 설정할 속성 및 값을 포함하는 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체의 배열에 대한 포인터입니다.  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]의 *OLE DB 프로그래머 참조*에서 [속성 집합 및 속성 그룹](https://msdn.microsoft.com/en-us/library/ms713696.aspx)을 참조하세요.  데이터 원본 개체가 초기화되면 속성은 데이터 원본 속성 그룹에 속해야 합니다.  동일한 속성이 `pPropset`에 두 번 이상 지정되면 사용되는 값은 공급자별로 다릅니다.  `ulPropSets`가 0이면 이 매개 변수는 무시됩니다.  
  
 `ulPropSets`  
 \[in\] *pPropSet* 인수로 전달된 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체 수입니다.  이 값이 0이면 공급자가 `pPropset`을 무시합니다.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 설명  
 이 메서드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다.  자세한 내용은 OLE DB 프로그래머 참조\([http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)\)의 "OLE DB 서비스"를 참조하세요.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)