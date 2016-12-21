---
title: "사용할 접근자 형식 결정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "접근자[C++], 형식"
  - "행 집합[C++], 데이터 형식"
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 사용할 접근자 형식 결정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일 타임이나 런타임에 행 집합의 데이터 형식을 결정할 수 있습니다.  
  
 컴파일 타임에 데이터 형식을 결정해야 하는 경우, `CAccessor` 같은 정적 접근자를 사용합니다.  사용자는 수동으로 데이터 형식을 결정하거나 ATL OLE DB 소비자 마법사를 사용하여 데이터 형식을 결정할 수 있습니다.  
  
 런타임에 데이터 형식을 결정해야 하는 경우, 동적 접근자\(`CDynamicAccessor` 또는 그 자식 접근자\)나 수동 접근자\(`CManualAccessor`\)를 사용합니다.  이런 경우 행 집합에서 `GetColumnInfo`를 호출하여 형식을 결정할 수 있는 열 바인딩 정보를 반환할 수 있습니다.  
  
 다음 표에는 소비자 템플릿의 접근자 형식이 나열되어 있습니다.  접근자마다 장점과 단점이 있으므로,  상황에 따라 적합한 접근자를 사용해야 합니다.  
  
|접근자 클래스|바인딩|Parameter|주석|  
|-------------|---------|---------------|--------|  
|`CAccessor`|`COLUMN_ENTRY` 매크로로 사용자 레코드를 만듭니다.  매크로는 해당 레코드의 데이터 맴버를 접근자에 바인딩합니다.  행 집합이 만들어지면 열의 바인딩은 해제될 수 없습니다.|예\(**PARAM\_MAP** 매크로 엔트리 사용\).  바인딩되면 매개 변수의 바인딩은 해제될 수 없습니다.|코드의 양이 적으므로 가장 빠른 접근자입니다.|  
|`CDynamicAccessor`|자동|아니요.|행 집합에서 데이터 형식을 모르는 경우 유용합니다.|  
|`CDynamicParameterAccessor`|자동이지만 [재정의](../../data/oledb/overriding-a-dynamic-accessor.md)될 수 있습니다.|예\(공급자가 `ICommandWithParameters`를 지원하는 경우\).  매개 변수는 자동으로 바인딩됩니다.|`CDynamicAccessor`보다 느리지만 일반 저장 프로시저 호출에 유용합니다.|  
|**CDynamicStringAccessor\[A,W\]**|자동|아니요.|데이터 저장소에서 액세스되는 데이터를 문자열 데이터로 검색합니다.|  
|`CManualAccessor`|수동\(`AddBindEntry` 사용\)|수동\(`AddParameterEntry` 사용\)|매우 빠름. 매개 변수와 열은 한 번만 바인딩됩니다.  사용할 데이터 형식을 결정하십시오. 예제로 [DBViewer](http://msdn.microsoft.com/ko-kr/07620f99-c347-4d09-9ebc-2459e8049832) 샘플을 참조하십시오. `CDynamicAccessor` 또는 `CAccessor` 보다 더 많은 코드가 필요합니다.  OLE DB를 직접 호출하는 것과 유사합니다.|  
|`CXMLAccessor`|자동|아니요.|데이터 저장소에서 액세스되는 데이터를 문자열 데이터로 검색하여 형식을 XML 태그 지정 데이터로 지정합니다.|  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)