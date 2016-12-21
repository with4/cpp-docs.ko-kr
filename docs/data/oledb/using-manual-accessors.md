---
title: "수동 접근자 사용 | Microsoft Docs"
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
  - "접근자[C++], 수동"
  - "명령 처리, OLE DB 템플릿"
  - "수동 접근자"
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 수동 접근자 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

알 수 없는 명령을 처리해야 하는 경우 다음과 같은 네 가지 작업을 수행해야 합니다.  
  
-   매개 변수 결정  
  
-   명령 실행  
  
-   출력 열 결정  
  
-   반환 행 집합이 여러 개인지 확인  
  
 OLE DB 소비자 템플릿으로 이 작업을 수행하려면, `CManualAccessor` 클래스를 사용하여 다음 단계를 수행하십시오.  
  
1.  템플릿 매개 변수로 `CManualAccessor`를 사용하여 `CCommand` 개체를 엽니다.  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  **IDBSchemaRowset** 인터페이스에 대한 세션을 쿼리하고 프로시저 매개 변수 행 집합을 사용합니다.  **IDBSchemaRowset** 인터페이스를 사용할 수 없는 경우, `ICommandWithParameters` 인터페이스를 쿼리합니다.  `GetParameterInfo`를 호출하여 정보를 얻습니다.  두 인터페이스 모두 사용할 수 없는 경우, 매개 변수가 없다고 가정할 수 있습니다.  
  
3.  각각의 매개 변수에 대해 `AddParameterEntry`를 호출하여 매개 변수를 추가하고 설정합니다.  
  
4.  행 집합을 열지만, 바인딩 매개 변수를 **false**로 설정합니다.  
  
5.  `GetColumnInfo`를 호출하여 출력 열을 검색합니다.  `AddBindEntry`를 사용하여 출력 열을 바인딩에 추가합니다.  
  
6.  `GetNextResult`를 호출하여 더 많은 행 집합을 사용할 수 있는지 확인합니다.  단계 2에서 단계 5까지 반복합니다.  
  
 수동 접근자에 대한 예제를 보려면 [DBVIEWER](http://msdn.microsoft.com/ko-kr/07620f99-c347-4d09-9ebc-2459e8049832) 샘플에서 **CDBListView::CallProcedure**를 참조하십시오.  
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)