---
title: "단순 소비자 만들기 | Microsoft Docs"
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
  - "OLE DB 소비자, 만들기"
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 단순 소비자 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 프로젝트 마법사와 ATL OLE DB 소비자 마법사를 사용하여 OLE DB 템플릿 소비자를 생성할 수 있습니다.  
  
#### OLE DB 소비자용 콘솔 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  프로젝트 형식 창에서 **Visual C\+\+ 프로젝트** 폴더를 클릭하고 템플릿 창에서 **Win32 프로젝트** 아이콘을 클릭합니다.  **이름** 상자에 프로젝트의 이름을 입력합니다\(예: **MyCons**\).  
  
3.  **확인**을 클릭합니다.  
  
     Win32 프로젝트 마법사가 나타납니다.  
  
4.  **응용 프로그램 설정** 창에서 **콘솔 응용 프로그램**을 선택하고 **ATL에 대한 지원 추가**를 선택합니다.  
  
5.  **마침**을 클릭하여 마법사를 닫아 프로젝트를 생성합니다.  
  
 그런 다음 ATL OLE DB 소비자 마법사를 사용하여 OLE DB 소비자 개체를 추가합니다.  
  
#### ATL OLE DB 소비자 마법사로 소비자를 만들려면  
  
1.  In Class View, right\-click the `MyCons` project.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
     **클래스 추가** 대화 상자가 나타납니다.  
  
3.  범주 창에서 **Visual C\+\+**를 클릭하고 템플릿 창에서 **ATL OLE DB 소비자** 아이콘을 클릭한 후 **열기**를 클릭합니다.  
  
     ATL OLE DB 소비자 마법사가 나타납니다.  
  
4.  **데이터 소스** 단추를 클릭합니다.  
  
     **데이터 연결 속성** 대화 상자가 나타납니다.  
  
5.  **데이터 연결 속성** 대화 상자에서 다음을 수행합니다.  
  
    -   **공급자** 탭에서 OLE DB 공급자를 지정합니다.  
  
    -   **연결** 탭에서 서버 이름, 데이터 소스에 대한 로그온 ID와 암호, 서버의 데이터베이스를 지정합니다.  
  
    > [!NOTE]
    >  **데이터 연결 속성** 대화 상자의 **암호 저장 허용** 기능을 사용하면 보안 문제가 발생할 수 있습니다.  **서버 로그온 정보 입력**에는 **Windows NT의 통합 보안 사용**과 **특정 사용자 이름 및 암호 사용**이라는 두 개의 라디오 단추가 있습니다.  
  
    > [!NOTE]
    >  **특정 사용자 이름 및 암호 사용**을 선택하면 **암호 저장 허용** 확인란을 사용하여 암호를 저장할 수 있지만 이 옵션은 안전하지 못합니다.  **Windows NT의 통합 보안 사용**을 선택하는 것이 좋습니다. 이 옵션을 선택하면 Windows NT를 사용하여 ID를 확인합니다.  
  
    > [!NOTE]
    >  Windows NT의 통합 보안을 사용할 수 없는 경우 중간 계층 응용 프로그램을 사용하여 사용자가 암호를 입력하도록 하거나 소스 코드 대신 보안 메커니즘이 적용된 위치에 암호를 저장하여 이를 보호해야 합니다.  
  
     공급자와 기타 설정을 선택한 후에는 **연결 테스트**를 클릭하여 이전 대화 상자 페이지에서 선택한 내용을 확인합니다.  If the **Results** box reports `Test connection succeeded`, click **OK** to create the data link.  
  
     **데이터베이스 개체 선택** 대화 상자가 나타납니다.  
  
6.  트리 컨트롤을 사용하여 테이블, 뷰 또는 저장 프로시저를 선택합니다.  이 과정을 위해 Northwind 데이터베이스에서 Products 테이블을 선택합니다.  
  
7.  **확인**을 클릭합니다.  이렇게 하면 ATL OLE DB 소비자 마법사가 나타납니다.  
  
8.  The wizard completes the names for `Class` and **.h file** based on the name of the table, view, or stored procedure that you selected.  필요한 경우 나중에 이들 이름을 편집할 수 있습니다.  
  
9. **특성** 확인란을 지우면 마법사는 기본 [OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md)이 아니라 [OLE DB Template 클래스](../../data/oledb/ole-db-consumer-templates-reference.md)를 사용하여 소비자 코드를 만듭니다.  
  
10. **형식** 아래에서 **명령**을 선택합니다.  
  
     마법사에서는 사용자가 **명령**을 선택한 경우 [CCommand](../../data/oledb/ccommand-class.md) 기반 소비자를 만들고, 사용자가 **테이블**을 선택한 경우 [CTable](../../data/oledb/ctable-class.md) 기반 소비자를 만듭니다.  테이블이나 명령 클래스의 이름은 선택된 개체 이름을 따서 지정되지만, 사용자가 이름을 변경할 수 있습니다.  
  
11. **지원**에서 **변경**, **삽입** 및 **삭제** 확인란을 지워진 상태로 놔 둡니다.  
  
     필요한 경우 **변경**, **삽입** 및 **삭제**를 선택하여 행 집합의 레코드를 변경, 삽입 및 삭제할 수 있습니다.  데이터 저장소에 데이터를 쓰는 데 대한 자세한 내용은 [행 집합 업데이트](../../data/oledb/updating-rowsets.md)를 참조하십시오.  
  
12. **마침**을 클릭하여 소비자를 만듭니다.  
  
 [소비자 마법사 생성 클래스](../../data/oledb/consumer-wizard-generated-classes.md)에 나타난 것처럼 마법사는 명령 클래스와 사용자 레코드 클래스를 생성합니다.  The command class will have the name that you entered in the `Class` box in the wizard \(in this case, `CProducts`\), and the user record class will have a name of the form "*ClassName*Accessor" \(in this case, `CProductsAccessor`\).  
  
> [!NOTE]
>  마법사는 다음 줄을 Products.h에 추가합니다.  
  
```  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  이 줄은 소비자 응용 프로그램이 컴파일되지 않도록 방지하고 연결 문자열에 암호가 하드 코딩되어있지 않은지 확인하도록 사용자의 주의를 환기합니다.  연결 문자열을 검사한 후에 이 줄을 코드에서 제거할 수 있습니다.  
  
## 참고 항목  
 [마법사를 사용하여 OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)