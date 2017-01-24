---
title: "Visual C++에서 RDO 데이터 바인딩 사용 | Microsoft Docs"
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
  - "데이터 바인딩[C++], RDO"
  - "RDO[C++], 데이터 바인딩"
  - "RDO RemoteData 컨트롤, Visual C++의 데이터 바인딩"
  - "RemoteData 컨트롤, Visual C++의 데이터 바인딩"
ms.assetid: 02b9cfe7-7bbe-4a01-b075-e28d9536ac4b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++에서 RDO 데이터 바인딩 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서 RDO 데이터 바인딩을 사용하려면 RDO RemoteData 컨트롤을 추가하고 이 컨트롤이 데이터 소스와 레코드 원본\(SQL 쿼리\)을 가리키도록 해야 합니다.  또한 RDO 데이터 바인딩 컨트롤을 추가한 다음 이 컨트롤이 RDO RemoteData 컨트롤을 가리키게 하고, RDO RemoteData 컨트롤의 레코드 원본에 바인딩할 필드를 선택해야 합니다.  
  
### Visual C\+\+에서 RDO 데이터 바인딩을 사용하려면  
  
1.  이미 구성하지 않은 경우에는 [ODBC 연결](../../data/ado-rdo/odbc-connections.md)을 구성합니다.  
  
2.  MFC 응용 프로그램 마법사를 사용하여 MFC 대화 상자 응용 프로그램이나 MFC 폼 뷰 응용 프로그램을 만듭니다.  
  
3.  대화 상자에 Microsoft RemoteData 컨트롤\(RDO RemoteData 컨트롤\)을 추가합니다\([Visual C\+\+ 응용 프로그램에 컨트롤 삽입](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md) 참조\).  
  
4.  RDO RemoteData 컨트롤이 ODBC 데이터 소스를 가리키도록 합니다.  
  
    1.  마우스 오른쪽 단추로 컨트롤을 클릭한 다음 **속성**을 클릭합니다.  
  
    2.  **컨트롤** 탭을 클릭합니다.  
  
    3.  **DataSource**를 ODBC 데이터 소스로 설정합니다.  
  
    4.  필요에 따라 ODBC 데이터 소스의 사용자 이름과 암호를 설정합니다.  데이터 소스에 사용자 이름과 암호가 필요하지 않으면 비워둡니다.  
  
    5.  **SQL** 속성에 SQL 쿼리를 입력합니다.  데이터 바인딩 컨트롤은 이 쿼리의 결과에 바인딩할 수 있습니다.  
  
5.  필요하면 다른 RDO RemoteData 컨트롤의 속성을 설정합니다.  
  
6.  데이터 바인딩 컨트롤을 추가합니다.  예를 들어, **DBGrid** 컨트롤을 추가하고 다음과 같이 데이터 소스를 설정합니다.  
  
    1.  마우스 오른쪽 단추로 DBGrid를 클릭한 다음 **속성**을 클릭합니다.  
  
    2.  **모두** 탭을 클릭합니다.  
  
    3.  **DataSource** 속성을 RDO RemoteData 컨트롤로 설정합니다.  이 속성의 드롭다운 콤보 상자를 클릭하고 RDO RemoteData 컨트롤의 ID를 찾습니다.  기본 ID 이름은 IDC\_REMOTEDATACTL1입니다.  
  
7.  테스트 모드에서 실행하려면 Ctrl\+T를 누릅니다.  데이터를 스크롤할 수 있습니다.  테스트 모드를 끝내려면 Esc 키를 누르거나 대화 상자를 닫습니다.  
  
 프로그램을 컴파일하고 실행할 경우에도 데이터를 스크롤할 수 있습니다.  
  
## 참고 항목  
 [RDO 데이터 바인딩](../../data/ado-rdo/rdo-databinding.md)   
 [Visual C\+\+에서 ActiveX 컨트롤을 사용하여 데이터 바인딩](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)