---
title: "CDataSource::OpenWithPromptFileName | Microsoft Docs"
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
  - "CDataSource.OpenWithPromptFileName"
  - "OpenWithPromptFileName"
  - "ATL::CDataSource::OpenWithPromptFileName"
  - "ATL.CDataSource.OpenWithPromptFileName"
  - "CDataSource::OpenWithPromptFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenWithPromptFileName 메서드"
ms.assetid: 89460504-1aaf-4412-aa7b-fa5a4b39ada3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::OpenWithPromptFileName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 메서드는 사용자에게 대화 상자를 표시한 다음 사용자가 지정한 파일을 사용하여 데이터 원본을 엽니다.  
  
## 구문  
  
```  
  
        HRESULT OpenWithPromptFileName(   
   HWND hWnd = GetActiveWindow(   
   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL    
) throw( );  
```  
  
#### 매개 변수  
 `hWnd`  
 \[in\] 대화 상자의 부모가 될 창의 핸들입니다.  
  
 `dwPromptOptions`  
 \[in\] 표시할 로케이터 대화 상자의 스타일을 결정합니다.  가능한 값은 Msdasc.h를 참조하세요.  
  
 *szInitialDirectory*  
 \[in\] 로케이터 대화 상자에 표시할 초기 디렉터리입니다.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 설명  
 이 메서드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다.  자세한 내용은 OLE DB 프로그래머 참조\([http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)\)의 "OLE DB 서비스"를 참조하세요.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)