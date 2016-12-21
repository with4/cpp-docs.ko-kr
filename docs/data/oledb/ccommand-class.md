---
title: "CCommand 클래스 | Microsoft Docs"
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
  - "ATL::CCommand"
  - "CCommand"
  - "ATL.CCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCommand 클래스"
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명령을 설정하고 실행하는 메소드를 제공합니다.  
  
## 구문  
  
```  
template <  
   class TAccessor = CNoAccessor,  
   template < typename T > class TRowset = CRowset,  
   class TMultiple = CNoMultipleResults   
>  
class CCommand :   
   public CAccessorRowset <  
      TAccessor,   
      TRowset   
   >,  
   public CCommandBase,  
   public TMultiple  
```  
  
#### 매개 변수  
 `TAccessor`  
 명령이 사용하기를 원하는 접근자 클래스의 형식\(`CDynamicParameterAccessor`, `CDynamicStringAccessor`, 또는 `CEnumeratorAccessor`와 같은\) 입니다.  기본값은 클래스가 매개 변수나 출력 열을 지원하지 않도록 지정하는 `CNoAccessor` 입니다  
  
 `TRowset`  
 명령이 사용하기를 원하는 행집합 클래스의 형식\(`CArrayRowset` 또는 `CNoRowset` 와 같은\) 입니다.  기본값은 `CRowset`입니다.  
  
 `TMultiple`  
 여러 결과를 반환할 수 있는 OLE DB 명령을 사용하려면 [CMultipleResults](../../data/oledb/cmultipleresults-class.md) 를 지정하십시오.  그렇지 않으면, [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md) 를 사용하십시오.  자세한 내용은, [IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx) 를 참조하십시오.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[닫기](../../data/oledb/ccommand-close.md)|현재 명령을 닫습니다.|  
|[GetNextResult](../../data/oledb/ccommand-getnextresult.md)|다양한 결과를 설정 할 때, 다음 결과를 불러옵니다.|  
|[를 엽니다.](../../data/oledb/ccommand-open.md)|실행 하고 필요에 따라 명령에 바인딩합니다.|  
  
### 상속 된 메서드  
  
|||  
|-|-|  
|[Create](../../data/oledb/ccommand-create.md)|지정된 된 세션에 대한 새 명령을 만들고 명령 텍스트를 설정 합니다.|  
|[CreateCommand](../../data/oledb/ccommand-createcommand.md)|새 명령을 만듭니다.|  
|[GetParameterInfo](../../data/oledb/ccommand-getparameterinfo.md)|명령의 매개 변수, 이름 및 형식 목록을 가져옵니다.|  
|[Prepare](../../data/oledb/ccommand-prepare.md)|유효성을 검사 하고 현재 명령을 최적화 합니다.|  
|[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)|필요한 경우 매개 변수 접근자를 해제 한 다음 명령을 해제 합니다.|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|각 명령 매개 변수의 기본 형식을 지정합니다.|  
|[Unprepare](../../data/oledb/ccommand-unprepare.md)|현재 명령 실행 계획을 삭제합니다.|  
  
## 설명  
 매개 변수 기반 작업을 수행하거나 명령을 실행할 때 이 클래스를 사용합니다.  단일 행 집합을 열기만 하려면 [CTable](../../data/oledb/ctable-class.md) 를 사용하십시오.  
  
 접근자 클래스를 사용 하는 매개 변수 및 데이터를 바인딩하는 방법을 결정 합니다.  
  
 Jet용 OLE DB 공급자는 저장 프로시저를 지원하지 않으므로 Jet용 OLE DB 공급자로 저장 프로시저를 사용할 수 없습니다. 쿼리 문자열에는 상수만 사용할 수 있습니다.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)