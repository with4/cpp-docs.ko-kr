---
title: "CXMLAccessor::GetXMLRowData | Microsoft Docs"
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
  - "ATL::CXMLAccessor::GetXMLRowData"
  - "ATL.CXMLAccessor.GetXMLRowData"
  - "CXMLAccessor::GetXMLRowData"
  - "CXMLAccessor.GetXMLRowData"
  - "GetXMLRowData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetXMLRowData 메서드"
ms.assetid: 156b66e3-42fd-491c-8943-38cf5e36f687
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CXMLAccessor::GetXMLRowData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

행으로 XML\-형식 문자열 데이터로써 테이블의 전체 내용을 검색합니다.  
  
## 구문  
  
```  
  
      HRESULT GetXMLRowData(   
   CSimpleStringW& strOutput,   
   bool bAppend = false    
) throw( );  
```  
  
#### 매개 변수  
 `strOutput`  
 \[out\] 검색할 테이블 데이터를 포함하는 버퍼에 대한 참조입니다.  데이터 스토어의 열 이름들에 대한 XML 태그 이름들을 사용하여 문자열 데이터로써 데이터는 서식지정됩니다.  
  
 *bAppend*  
 \[in\] Boolean 값은 문자열의 출력 데이터의 끝에 추가할 것인지를 지정 하는 값입니다.  
  
## 반환 값  
 정규 `HRESULT` 값 중 하나 입니다.  
  
## 설명  
 다음은 XML에서 행 데이터를 포맷하는 방법을 보여줍니다.  `DATA` 아래 행 데이터를 나타냅니다.  원하는 행으로 이동하는 이동 메서드를 사용합니다.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CXMLAccessor 클래스](../../data/oledb/cxmlaccessor-class.md)