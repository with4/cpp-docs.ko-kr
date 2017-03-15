---
title: "CDynamicStringAccessor 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicStringAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessor 클래스"
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDynamicStringAccessor 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터베이스 스키마\(내부 구조\)에 대해 모르더라도 데이터 소스에 액세스할 수 있습니다.  
  
## 구문  
  
```  
  
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)|지정된 열 데이터를 문자열로 검색합니다.|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|지정된 열 데이터를 문자열로 설정합니다.|  
  
## 설명  
 [CDynamicAccesso](../../data/oledb/cdynamicaccessor-class.md)는 공급자가 보고한 원시 형식으로 데이터를 요청하는 반면, `CDynamicStringAccessor`에서는 공급자가 데이터 저장소에서 액세스되는 모든 데이터를 문자열 데이터로 페치하도록 요청합니다.  특히 이것은 데이터 저장소의 내용 표시 또는 인쇄와 같이 데이터 저장소의 값을 계산할 필요가 없는 단순 작업에 적합합니다.  
  
 데이터 스토어에서 열 데이터의 원시 형식은 중요하지 않습니다. 공급자가 데이터 변환을 지원하는 동안, 그것은 문자열 형식으로 데이터를 제공할 것입니다.  공급자가 원시 데이터 형식에서 문자열로 변환을 지원하지 않으면\(일반적인 것은 아닙니다\), 요청 호출은 성공 값  **DB\_S\_ERRORSOCCURED**을 반환할 것입니다. 그리고 해당 열의 상태는 **DBSTATUS\_E\_CANTCONVERTVALUE**를 사용한 변환 문제를 나타냅니다.  
  
 `CDynamicStringAccessor` 메서드를 사용하여 열 정보를 구하십시오.  사용자는 이 열 정보를 사용하여 런타임에 동적으로 접근자를 만듭니다.  
  
 열 정보는 이 클래스에서 만들고 관리하는 버퍼에 저장됩니다.  [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)을 사용하여 버퍼에서 데이터를 가져오거나 [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)을 사용하여 버퍼에 데이터를 저장합니다.  
  
 동적 접근자 클래스 사용의 설명 및 예제를 보려면 [동적 접근자 사용](../../data/oledb/using-dynamic-accessors.md)을 참조하십시오.  
  
## 요구 사항  
 **Header**: atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessorA 클래스](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW 클래스](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CXMLAccessor 클래스](../../data/oledb/cxmlaccessor-class.md)