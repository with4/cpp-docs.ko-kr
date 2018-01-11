---
title: "마법사를 사용 하지 않고 소비자 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b31f1ad51d9015c491439650060ab3cefaf3270b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>마법사를 사용하지 않고 소비자 만들기
다음 예에서는 기존 ATL 프로젝트에 OLE DB 소비자 지원을 추가 가정 합니다. MFC 응용 프로그램에 OLE DB 소비자 지원을 추가 하려는 경우 모든 지원이 필요한 만들고 응용 프로그램을 실행 하는 데 필요한 MFC 루틴을 호출 하는 MFC 응용 프로그램 마법사를 실행 해야 합니다.  
  
 ATL OLE DB 소비자 마법사를 사용 하지 않고 OLE DB 소비자 지원 추가:  
  
-   Stdafx.h 파일에 다음 추가 `#include` 문:  
  
    ```  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 프로그래밍 방식으로 소비자는 일반적으로 다음과 같은 일련의 작업을 수행합니다.  
  
-   지역 변수에 열을 바인딩하는 사용자 레코드 클래스를 만듭니다. 이 예제에서는 `CMyTableNameAccessor` 사용자 레코드 클래스는 (참조 [사용자 레코드](../../data/oledb/user-records.md)). 이 클래스는 열 지도 및 지도 매개 변수를 포함합니다. 열 지도;에 지정한 각 필드에 대 한 사용자 레코드 클래스의 데이터 멤버를 선언 합니다. 각각의 이러한 데이터 멤버에 대 한 상태 데이터 멤버 및 길이 데이터 멤버를 선언할 수도 있습니다. 자세한 내용은 참조 [마법사 생성 접근자의 필드 상태 데이터 멤버](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)합니다.  
  
    > [!NOTE]
    >  사용자 고유의 소비자를 작성 하는 경우 데이터 변수가 상태 및 길이 변수 앞와 야 합니다.  
  
-   데이터 소스 및 세션을 인스턴스화하십시오. 접근자 및 행 집합의 유형을 사용 하 고 다음 사용 하 여 행 집합을 인스턴스화할 결정 [CCommand](../../data/oledb/ccommand-class.md) 또는 [CTable](../../data/oledb/ctable-class.md):  
  
    ```  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor> >  
    ```  
  
-   호출 **CoInitialize** COM을 초기화 하려면 이 일반적으로 주 코드에 호출 됩니다. 예:  
  
    ```  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   호출 [cdatasource:: Open](../../data/oledb/cdatasource-open.md) 또는 해당 변형 중 하나입니다.  
  
-   데이터 원본에 대 한 연결, 세션을 연 후를 열 및 행 집합 초기화 (열고을 열어):  
  
    ```  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   필요에 따라 행 집합 속성 설정 사용 하 여 `CDBPropSet::AddProperty` 에 대 한 매개 변수로 전달 하 고 `rs.Open`합니다. 이 수행 되는 방법의 예를 들어 참조에서 GetRowsetProperties [소비자 마법사 생성 메서드](../../data/oledb/consumer-wizard-generated-methods.md)합니다.  
  
-   이제 데이터를 검색 하거나 조작 하는 행 집합을 사용할 수 있습니다.  
  
-   응용 프로그램이 완료 되 면, 연결, 세션 및 행 집합을 닫습니다.  
  
    ```  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     호출 하려는 명령을 사용 하는 경우 `ReleaseCommand` 후 **닫기**합니다. 코드 예제에서는 [ccommand:: Close](../../data/oledb/ccommand-close.md) 호출 하는 방법을 보여 줍니다. **닫기** 및 `ReleaseCommand`합니다.  
  
-   호출 **CoUnInitialize** COM.의 초기화를 해제 하려면 이 일반적으로 주 코드에 호출 됩니다.  
  
    ```  
    CoUninitialize();  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer.md)