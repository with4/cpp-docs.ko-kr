---
title: "수동 접근자 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dd628baa51ec790686f185c49ff33e7c6984150f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-manual-accessors"></a>수동 접근자 사용
알 수 없는 명령을 처리할 때 작업을 수행 하는 4 가지 가지가 있습니다.  
  
-   매개 변수를 확인 합니다.  
  
-   명령 실행  
  
-   출력 열을 결정  
  
-   여러 반환 행 집합 확인  
  
 이를 위해 OLE DB 소비자 템플릿 사용는 `CManualAccessor` 클래스 및 다음이 단계를 수행 합니다.  
  
1.  열기는 `CCommand` 개체 `CManualAccessor` 템플릿 매개 변수로 합니다.  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  세션에 대 한 쿼리는 **IDBSchemaRowset** 인터페이스 및 프로시저 매개 변수 행 집합을 사용 합니다. 경우는 **IDBSchemaRowset** 인터페이스를 사용할 수 없으면에 대 한 쿼리는 `ICommandWithParameters` 인터페이스입니다. 호출 `GetParameterInfo` 정보에 대 한 합니다. 두 인터페이스 모두를 사용할 수 있는 경우 매개 변수가 없는 가정할 수 있습니다.  
  
3.  각 매개 변수에 대 한 호출 `AddParameterEntry` 하는 매개 변수를 추가 하 고 설정 합니다.  
  
4.  행 집합을 열고 바인딩 매개 변수를 설정 하지만 **false**합니다.  
  
5.  호출 `GetColumnInfo` 출력 열을 검색할 수 있습니다. 사용 하 여 `AddBindEntry` 바인딩에 출력 열을 추가 합니다.  
  
6.  호출 `GetNextResult` 행 집합이 더 이상 사용할 수 있는 되는지 확인할 수 있습니다. 2 ~ 5 단계를 반복 합니다.  
  
 수동 접근자의 예제를 보려면 **CDBListView::CallProcedure** 에 [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) 샘플.  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)