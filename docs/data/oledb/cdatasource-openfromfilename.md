---
title: "CDataSource::OpenFromFileName | Microsoft Docs"
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
  - "CDataSource::OpenFromFileName"
  - "ATL::CDataSource::OpenFromFileName"
  - "OpenFromFileName"
  - "CDataSource.OpenFromFileName"
  - "ATL.CDataSource.OpenFromFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenFromFileName 메서드"
ms.assetid: c4226de6-59da-4368-9c15-c5afab86f68b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::OpenFromFileName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자가 제공한 파일 이름으로 지정된 파일에서 데이터 소스를 엽니다.  
  
## 구문  
  
```  
  
        HRESULT OpenFromFileName(   
   LPCOLESTR szFileName    
) throw( );  
```  
  
#### 매개 변수  
 `szFileName`  
 \[in\] 일반적으로 데이터 소스 연결\(.UDL\) 파일의 이름입니다.  
  
 데이터 링크 파일\(.udl 파일\)에 대한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]에서 [데이터 링크 API 개요](https://msdn.microsoft.com/en-us/library/ms718102.aspx)를 참조하세요.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 설명  
 이 메서드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다.  자세한 내용은 OLE DB 프로그래머 참조\([http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)\)의 "OLE DB 서비스"를 참조하세요.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)